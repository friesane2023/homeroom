# Homeroom — setting up multi-device sync (Firebase)

Homeroom works fully offline with zero setup — open `index.html` and go.
This doc is only for the optional extra: **multi-device sync**, so the
same family's data shows up the same way on every phone/tablet/laptop
instead of staying local to whichever device entered it.

Sync runs on [Firebase](https://firebase.google.com) (Google's), using
your own free Firebase project — not a shared service, and not anything
this repo's maintainer can see or touch. You'll need a Google account.
Nothing here is secret or sensitive to keep private except the one
password you create in step 3.

---

## 1. Create a Firebase project

1. Go to [console.firebase.google.com](https://console.firebase.google.com)
   and click **Add project**.
2. Name it anything (e.g. `my-family-homeroom`) — the name is cosmetic,
   it just becomes part of some auto-generated IDs. Google Analytics isn't
   needed; skip/decline it if asked.

## 2. Turn on the Realtime Database

1. In the left sidebar: **Build → Realtime Database → Create Database**.
2. Pick any region (closest to you is fine — it doesn't need to match
   where your family actually lives).
3. Start in **locked mode** — you'll set the real rules in step 4.

## 3. Turn on sign-in and create one shared family login

1. **Build → Authentication → Get started**.
2. Under **Sign-in method**, enable **Email/Password**.
3. Go to the **Users** tab → **Add user**. Use one email + password for
   the whole family (not one account per person) — this is the login
   every device signs in with, in Setup → Data → Multi-device sync.
   Pick a password you're comfortable sharing with your kids, since
   they'll type it in on their own devices.

## 4. Set the database's security rules

**Build → Realtime Database → Rules**, replace whatever's there with:

```json
{
  "rules": {
    "homeroom": {
      ".read": "auth != null",
      ".write": "auth != null"
    }
  }
}
```

This means: only someone signed in (with the login from step 3) can read
or write the family's data — nobody else, including anonymous visitors,
can touch it. Click **Publish**.

## 5. Get your project's config and paste it into `index.html`

1. Click the **gear icon → Project settings**, scroll to **Your apps**,
   click the **`</>`  (Web)** icon to register a new web app (any
   nickname; you don't need Firebase Hosting checked here).
2. It'll show a `firebaseConfig` object like this:

   ```js
   const firebaseConfig = {
     apiKey: "...",
     authDomain: "...",
     databaseURL: "...",
     projectId: "...",
     storageBucket: "...",
     messagingSenderId: "...",
     appId: "..."
   };
   ```
3. Open `index.html`, find the placeholder `FIREBASE_CONFIG` block near
   the top of the `<script>` (search for `FIREBASE_CONFIG`), and replace
   each `"YOUR_..."` placeholder value with the matching real value from
   your project.

These values are meant to be public/embedded in client-side code, the
same way this file's Google Fonts links are — they're not a secret by
themselves. What actually protects your data is the sign-in requirement
plus the rules from step 4, not hiding these.

## 6. Try it

1. Open `index.html` in a browser (any of the normal ways — see
   `GETTING-STARTED.md`).
2. **Setup → Data → Multi-device sync** → sign in with the email/password
   from step 3.
3. Enter something, then open the same file on a second device, sign in
   the same way, and confirm it shows up there too.

---

## Optional: Firebase Hosting, for phones/tablets

A phone or tablet generally can't open a local `index.html` file the way
a laptop can, and some mobile browsers restrict the storage sign-in
depends on unless the page is served over a real `https://` origin.
**Firebase Hosting** (same project, no separate account) solves this —
a free, real `https://` URL you can visit from any device.

1. Install the CLI once: `npm install -g firebase-tools`, then
   `firebase login`.
2. In this project's folder: `firebase init hosting` and follow the
   prompts (pick the project you created above; when it asks for a public
   directory, point it at a folder containing your `index.html`).
3. `firebase deploy --only hosting` — it prints a URL like
   `https://your-project-id.web.app`. Visit that on the phone/tablet,
   sign in the same way as step 6 above.

You don't need this at all if every device is a laptop/Chromebook that
can just open the file directly.

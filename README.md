# Owen's Return

A responsive event landing page for Owen's return celebration.

## Publish
The site is deployed with GitHub Pages from the `main` branch:
https://carsonmmm.github.io/owen-return/

## Configure shared RSVPs (Firebase)

The page now uses Firebase Authentication (anonymous sign-in) and Cloud Firestore for shared RSVPs, live headcounts, guest messages, event details, and host controls. GitHub Pages itself does not provide a database.

1. Create a Firebase project at https://console.firebase.google.com/.
2. In **Build → Authentication → Sign-in method**, enable **Anonymous**.
3. In **Build → Firestore Database**, create a database.
4. In **Project settings → General → Your apps**, register a Web app and copy its Firebase config into `firebase-config.js`. Replace every `PASTE_...` placeholder.
5. In Firestore **Rules**, publish the contents of `firestore.rules`.
6. To grant host controls, sign in to the published site once. In Firebase Console → Firestore → Data, create a collection named `admins` and a document whose ID is that host browser's Firebase anonymous UID. The UID is available in the browser console with:
   `firebase.auth().currentUser.uid`
   Only create admin documents for trusted hosts. Keep the same browser profile for host access.
7. Refresh the site. Guests can RSVP from their own browser; each browser has its own RSVP record.

### Security notes
- Guests can read the guest list and create/update only their own RSVP.
- Only an admin document grants host controls and permission to edit event details or remove other RSVPs.
- Admin documents can only be created manually in the Firebase Console; the public website cannot grant admin access.
- Do not put service-account keys or other private credentials in this repository. Firebase web config is public by design; Firestore rules enforce access.

Until a Firebase project is configured and the rules are published, the RSVP form remains disabled and no guest information is collected.

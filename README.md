# Absze Outreach Workspace

A static front-end workspace for the Absze team. It has an email/password sign-in screen for Mohamed Ahnaf, Jeeva, and Lalu. Employees can start and end work sessions and see their attendance for the day.

## Local prototype sign-in

With `firebase-config.js` left blank, the app uses prototype sign-in. Password hashes and password changes are kept in that browser only; they do not sync to another computer. This mode is for previewing the workflow, not protecting real data on a public site.

## Enable shared sign-in and team data

1. Create a Firebase project and Realtime Database. Enable Email/Password under Firebase Authentication, and add your Vercel domain to its authorized domains.
2. Create the three team accounts in Firebase Authentication using their Absze email addresses. Use the temporary passwords shared separately, then ask each person to change their password in Settings.
3. Copy the Firebase web app config into `firebase-config.js`, including `apiKey`, `projectId`, and the Realtime Database URL. This client config is public; never put a service account key in this project.
4. Apply `database.rules.json` in the Realtime Database Rules page. Reads and writes require a signed-in Firebase account.
5. Deploy this folder to Vercel and share the link.

The app only permits the three listed team emails through its sign-in screen. Imported source files are not uploaded; extracted prospect records and import history sync through Firebase.

## Local preview

Open `index.html` or serve this folder locally. Firebase sign-in and shared data require an internet connection and Firebase setup.

## Repository hygiene

`.gitignore` excludes Vercel state, dependency folders, and spreadsheet exports. Do not commit exports or source lead lists.

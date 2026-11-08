MY INFO HOME TRACKER — EMAIL/PASSWORD + GOOGLE FIREBASE VERSION

Files to upload to the ROOT of your existing GitHub Pages repository:
- index.html
- manifest.webmanifest
- sw.js
- logo.png
- icon-192.png
- icon-512.png
- README.txt (optional)

FIREBASE SETUP (one-time)
1. Open Firebase Console > Authentication > Sign-in method.
2. Enable Email/Password and save. This is required for email/password accounts.
3. Google provider may remain enabled as an optional sign-in method.
4. Authentication > Settings > Authorized domains: make sure your GitHub Pages hostname is listed (for example, username.github.io).
5. Firestore rules must allow only the signed-in user to access users/{userId}/videos/{videoId}, with request.auth != null and request.auth.uid == userId.

USING THE TRACKER
- Create account: enter an email and a password of at least 6 characters, then tap Create account.
- Returning user: enter the same email/password and tap Sign in.
- Forgot password: enter your email and tap Forgot password? to receive a reset link.
- Google sign-in remains available as an alternative.
- Each Firebase account has its own private video collection. Other users cannot see your records.

DEPLOY
1. Extract this ZIP.
2. In your existing GitHub repository, replace the old app files with these files.
3. Commit directly to main and wait for GitHub Pages to deploy.
4. Open your existing tracker URL. If an old version remains cached, close the installed app, open the URL in Chrome, refresh, then reopen the app.

DATA SAFETY
Keep your existing Firebase project and Firestore data. Do not delete the project. Export a JSON backup occasionally. Firebase web config is client-side configuration, not a service-account private key. Firestore security rules—not hiding the config—protect user records.

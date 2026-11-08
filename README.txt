MY INFO HOME TRACKER — FIREBASE VERSION

Files:
- index.html
- manifest.webmanifest
- sw.js
- logo.png
- icon-192.png
- icon-512.png

Deploy all files to the ROOT of your existing GitHub Pages repository.

Firebase project:
- Project ID: my-info-home-tracker1
- Authentication: Google provider enabled
- Firestore collection path: users/{userId}/videos/{videoId}
- Firestore rules must match that path and restrict access to request.auth.uid == userId.

IMPORTANT FIRST DEPLOY:
1. In Firebase Console > Authentication > Settings > Authorized domains, add your exact GitHub Pages hostname, for example YOUR_GITHUB_USERNAME.github.io (hostname only, no https or path).
2. Make sure Google sign-in provider is enabled and a support email is selected.
3. Confirm Firestore rules are published.
4. Deploy all files to GitHub Pages, replacing the old files.
5. Open the GitHub Pages URL online and sign in with the Google account you intend to use.
6. On first sign-in, existing local tracker records are copied to Firestore if that account's cloud collection is empty. If cloud records already exist, cloud records become the device's current list.
7. Keep the JSON export as an additional backup.

Privacy/security:
- The Firebase web config is client-side configuration, not a service-account private key.
- Firestore security rules enforce per-user access.
- Do not publish service-account private keys.
- Consider restricting the Firebase API key in Google Cloud Console to your GitHub Pages HTTP referrer and the Firebase APIs this app uses.

Offline:
- Firestore persistent local cache is enabled. After signing in online at least once, cached data can be viewed offline and offline writes are queued for sync when connectivity returns.
- Do not clear site data while offline if there are pending changes.

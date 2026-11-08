# ITU FIELD OPS 2026 — going live

The site is hosted on GitHub Pages under your domain. Data and sign-in use Firebase on the free Spark plan.
No staff data is kept in this repository. The PM imports the Excel file from inside the app after signing in.

## 1. Firebase (one time)
1. Go to console.firebase.google.com and add a project.
2. In Build > Authentication > Sign-in method, enable **Email/Password**.
3. In Build > Firestore Database, create a database in production mode.
4. In Firestore > Rules, paste `firestore.rules`. Replace `PM_EMAIL_HERE` with the PM's email, then click Publish.
5. In Project settings > Your apps, add a Web app and copy its `firebaseConfig` into `config.js`.
6. In Authentication > Settings > Authorized domains, add your domain, for example `ops.example.com`.

## 2. GitHub Pages
1. Push this folder to the repository root.
2. In Settings > Pages, set Source to `main`, folder `/ (root)`.
3. Set Custom domain to your domain. This creates the `CNAME` file.
4. At your domain registrar, add a CNAME record from your subdomain (for example `ops`) to `<github-user>.github.io`.
5. Tick "Enforce HTTPS" when it becomes available.

## 3. First day
1. The PM signs in with "First time? Create password", using the email in `config.js`.
2. In Data & import, upload the staff Excel file and confirm.
3. In Data & import > Supervisor accounts, enter each supervisor's email.
4. Each supervisor opens the site and uses "First time? Create password" with that email. They see only their own team, and can only record attendance for today.
5. In Staff & assignment, filter Role = Marshal and Assignment = Not assigned. Select marshals, choose supervisor, department and shift, then Apply.

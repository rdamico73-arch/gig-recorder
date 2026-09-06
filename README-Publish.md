# Publishing the Gig Recorder website (GitHub Pages)

Two pages Apple requires before submission live in this folder:

- `privacy.html` – Privacy Policy URL (App Store Connect > App Information; also linked from Settings > About in the app)
- `index.html` – Support URL (App Store Connect > App Information)

## Before you publish: one edit

Both files contain `REPLACE-ME@example.com` (three places total). Replace it with the
support address you want public. Do not use your work address. A free option is a
dedicated mailbox such as `gigrecorder.support@gmail.com` or `hello@` on a domain you own.

## Publish (about 10 minutes)

1. Sign in at https://github.com (create a free account if needed).
2. New repository: name it `gigrecorder`, Public, no README. Create.
3. On the empty repo page, click "uploading an existing file" and drag in
   `index.html` and `privacy.html` from this folder. Commit.
4. Repo > Settings > Pages. Under "Build and deployment" set Source = Deploy from a
   branch, Branch = `main`, folder `/ (root)`. Save.
5. Wait one or two minutes, then reload the Pages settings. It shows your site URL:
   `https://<your-github-username>.github.io/gigrecorder/`
6. Open both pages to confirm:
   - `https://<username>.github.io/gigrecorder/` (support)
   - `https://<username>.github.io/gigrecorder/privacy.html` (privacy)

## Wire the URLs in

1. `SetRecorder/AppConfig.swift`: replace the two `REPLACE-ME` strings with the real
   URLs. The Settings > About links appear automatically once the placeholder is gone.
   Rebuild and bump the build number before uploading.
2. App Store Connect > your app > App Information:
   - Privacy Policy URL = the `privacy.html` URL
   - Support URL = the support URL
   Marketing URL is optional; the support page works there too.
3. App Store Connect > App Privacy: keep "Data Not Collected". The policy page says
   the same thing, and the in-app `PrivacyInfo.xcprivacy` declares no collected data.

## Later

- Custom domain (optional): Settings > Pages > Custom domain, then add a CNAME at your
  registrar. Update `AppConfig.swift` and App Store Connect if the URL changes.
- Any time the app starts collecting data (crash reports, analytics), update
  `privacy.html`, the App Privacy label, and Settings text in the same release.

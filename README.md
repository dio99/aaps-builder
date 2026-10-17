# AAPS Builder

Build your own [AAPS](https://github.com/nightscout/AndroidAPS) app in GitHub. Nothing to install, no terminal.

> **No fork needed.** You do not need to fork AndroidAPS. The source code is downloaded from
> [nightscout/AndroidAPS](https://github.com/nightscout/AndroidAPS) at every build.

## 👉 New here?

Start with the setup page. It walks you through everything:

**[https://dio99.github.io/aaps-builder/](https://dio99.github.io/aaps-builder/)**

## 🔧 Already have your own copy?

These buttons always open **this** repository, whatever you named it:

| | |
|---|---|
| 🔑 **[Add your key](../../settings/secrets/actions/new)** | Name: `KEYSTORE_SET` · Secret: the long code from the setup page |
| ▶️ **[Build AAPS](../../actions/workflows/build.yml)** | Run workflow → Run workflow |
| 📦 **[My builds](../../actions)** | Open a finished build → tap **📱 Download AAPS** |

> **On a phone, use the web browser (Chrome), not the GitHub app.** The app cannot show or download your builds.
> In the app, open the build, tap the **share icon** (top right) → **Copy link**, then open Chrome and paste the link
> in the address bar. To stop GitHub links opening in the app: Android Settings → Apps →
> GitHub → Open by default → turn off **Open supported links**.

**New AAPS version?** Press **Build AAPS** → **Run workflow** again. `latest` always builds the newest release.

**📧 E-mail when a build is done (optional):** by default GitHub only e-mails you when a build fails. To also get an
e-mail when it succeeds: open [github.com/settings/notifications](https://github.com/settings/notifications) →
**System → Actions** → untick **"Only notify for failed workflows"**.

**Updates:** your repository is fully self-contained: no code from anywhere else ever runs with your key. If an
update of AAPS Builder is ever required, you get an issue (and an e-mail) in your repository. See
[Updating your copy](#-updating-your-copy).

## 🔄 Updating your copy

Do this when you get an **"AAPS Builder update available"** issue. Your copy does not change by itself, so you copy
one file. It takes 2 minutes. Use a **web browser**, on a computer if you can: the GitHub app cannot do this.

1. Open the new file: **https://github.com/dio99/aaps-builder/blob/main/.github/workflows/build.yml**
2. Click the **copy icon** ⧉ ("Copy raw file") at the top right of the file.
   *On a phone:* open the plain-text version instead:
   **https://raw.githubusercontent.com/dio99/aaps-builder/main/.github/workflows/build.yml**,
   press and hold the text → **Select all** → **Copy**.
3. Open **your own** repository → **Code** → folder `.github` → `workflows` → `build.yml`.
4. Click the **pencil** ✏️ (Edit this file) at the top right.
5. Click in the text and select everything (**Ctrl+A**; on a phone: press and hold → **Select all**), then paste
   (**Ctrl+V** / **Paste**). The old text must be completely replaced.
6. Click the green **Commit changes…** button, then **Commit changes** again.
7. Close the issue. Your secret `KEYSTORE_SET` and everything else stay as they were.

To check: run **Build AAPS** once. The step *Check for builder updates* should say "up to date".

**Version 2:** automatic weekly builds were removed at the request of the AAPS developers. You always start a build
yourself. Until you have updated, you can stop the automatic builds right away without editing any file:
Settings → Secrets and variables → Actions → **Variables** → **New repository variable**: name `AUTO_BUILD`,
value `false`.

## ⚠️ Before every update

1. AAPS → Maintenance → **Export settings**
2. Copy the exported file **off the phone** (Google Drive, Dropbox…), together with the APK files. Keep several older
   exports.

[How to export settings](https://androidaps.readthedocs.io/en/latest/Maintenance/ExportImportSettings.html) ·
[AAPS FAQ: how to organize backups](https://androidaps.readthedocs.io/en/latest/UsefulLinks/FAQ.html#how-to-organize-my-backups)

## Why a private repository?

Everything a build produces is visible to anyone who can see the repository. A **private** repository keeps
your APK for your eyes only. The workflow refuses to run in a public repository unless the APKs go to
Google Drive instead. Private repositories get 2000 free GitHub Actions minutes per month; one build takes
about 15–30 minutes.

## Secrets

| Secret | Required | What |
|---|---|---|
| `KEYSTORE_SET` | yes | Keystore and passwords in one value, created by the setup page |
| `GDRIVE_OAUTH2` | no | Also upload the APKs to Google Drive (folder `AAPS/<version>`), see the AAPS documentation |

## Privacy

The setup page runs entirely in your browser. Your keystore and passwords are never sent anywhere, except into
the GitHub secret you paste them into yourself.

## License

This project is open-source software licensed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.

### Key Terms
* **Copyleft:** Any modifications or derivative works must also be open-sourced under the AGPL-3.0.
* **Network Trigger:** If you run a modified version of this software on a server and let users interact with it over a network, you must make your modified source code available to those users.

For the full license text, please see the [LICENSE](LICENSE) file.

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

**New AAPS version?** Nothing to do. Once a week (Monday night) your repository checks nightscout and builds a new
version automatically. Already built versions are never built again. You can always build by hand with **Build AAPS**.

Turn off automatic builds: Settings → Secrets and variables → Actions → Variables → `AUTO_BUILD` = `false`.

**📧 E-mail when a build is done (optional):** by default GitHub only e-mails you when a build fails. To also get an
e-mail when it succeeds: open [github.com/settings/notifications](https://github.com/settings/notifications) →
**System → Actions** → untick **"Only notify for failed workflows"**.

**Updates:** your repository is fully self-contained: no code from anywhere else ever runs with your key. If an
update of AAPS Builder is ever required, you get an issue (and an e-mail) in your repository with 2-minute update
instructions.

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

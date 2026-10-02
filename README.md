# AAPS Builder

Build your own [AAPS](https://github.com/nightscout/AndroidAPS) app in GitHub. Nothing to install, no terminal.

**👉 Start here: the setup page** (`https://<owner>.github.io/aaps-builder/`)

The setup page walks you through everything:

1. **Create your private build repository**: one click, from this template.
2. **Your signing key**: pick your existing keystore, or create a new one in the browser.
3. **Paste one secret** (`KEYSTORE_SET`) into your repository.
4. **Build**: Actions → *Build AAPS* → *Run workflow*.
5. **Install**: download the APK from the finished build.

New AAPS version? Just repeat step 4. `latest` always builds the newest release.

## Why a private repository?

Everything a build produces is visible to anyone who can see the repository. A **private** repository keeps
your APK for your eyes only. The workflow refuses to run in a public repository unless the APKs go to
Google Drive instead.

Private repositories get 2000 free GitHub Actions minutes per month. One build takes about 30–60 minutes.

## Secrets

| Secret | Required | What |
|---|---|---|
| `KEYSTORE_SET` | yes | Keystore and passwords in one value, created by the setup page |
| `GDRIVE_OAUTH2` | no | Also upload the APKs to Google Drive (folder `AAPS/<version>`), see the AAPS documentation |

## Privacy

The setup page runs entirely in your browser. Your keystore and passwords are never sent anywhere, except into
the GitHub secret you paste them into yourself.

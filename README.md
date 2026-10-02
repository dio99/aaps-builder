# AAPS Builder

Build your own [AAPS](https://github.com/nightscout/AndroidAPS) app in GitHub. Nothing to install, no terminal.
Bygg din egen AAPS-app i GitHub. Inget att installera, ingen terminal.

## 👉 New here? / Ny här?

Start with the setup page. It walks you through everything:
Börja med inställningssidan. Den guidar dig genom allt:

**https://dio99.github.io/aaps-builder/**

## 🔧 Already have your own copy? / Har du redan en egen kopia?

These buttons always open **this** repository, whatever you named it:
Knapparna öppnar alltid **det här** repot, oavsett vad det heter:

| | |
|---|---|
| 🔑 **[Add your key / Lägg till din nyckel](../../settings/secrets/actions/new)** | Name: `KEYSTORE_SET` · Secret: from the setup page / från inställningssidan |
| ▶️ **[Build AAPS / Bygg AAPS](../../actions/workflows/build.yml)** | Run workflow → Run workflow |
| 📦 **[My builds / Mina byggen](../../actions)** | Open a finished build → Artifacts → download / ladda ner |

New AAPS version? Just press **Build AAPS** again. `latest` always builds the newest release.
Ny AAPS-version? Tryck bara **Bygg AAPS** igen. `latest` bygger alltid den senaste versionen.

## Why a private repository? / Varför ett privat repo?

Everything a build produces is visible to anyone who can see the repository. A **private** repository keeps
your APK for your eyes only. The workflow refuses to run in a public repository unless the APKs go to
Google Drive instead. Private repositories get 2000 free GitHub Actions minutes per month; one build takes
about 30–60 minutes.

## Secrets

| Secret | Required | What |
|---|---|---|
| `KEYSTORE_SET` | yes | Keystore and passwords in one value, created by the setup page |
| `GDRIVE_OAUTH2` | no | Also upload the APKs to Google Drive (folder `AAPS/<version>`), see the AAPS documentation |

## Privacy

The setup page runs entirely in your browser. Your keystore and passwords are never sent anywhere, except into
the GitHub secret you paste them into yourself.

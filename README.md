# AAPS Builder

Build your own [AAPS](https://github.com/nightscout/AndroidAPS) app in GitHub. Nothing to install, no terminal.
Bygg din egen AAPS-app i GitHub. Inget att installera, ingen terminal.

> **No fork needed / Ingen fork behövs.** You do not need to fork AndroidAPS. The source code is downloaded from
> [nightscout/AndroidAPS](https://github.com/nightscout/AndroidAPS) at every build. / Du behöver inte forka
> AndroidAPS. Koden hämtas från nightscout vid varje bygge.

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

**New AAPS version?** Nothing to do. Every night your repository checks nightscout and builds a new version
automatically. Already built versions are never built again. You can always build by hand with **Build AAPS**.
**Ny AAPS-version?** Inget att göra. Varje natt kollar ditt repo nightscout och bygger en ny version automatiskt.
Redan byggda versioner byggs aldrig om. Du kan alltid bygga för hand med **Bygg AAPS**.

Turn off automatic builds / Stäng av automatiska byggen: Settings → Secrets and variables → Actions → Variables →
`AUTO_BUILD` = `false`.

**Updates / Uppdateringar:** your repository is fully self-contained: no code from anywhere else ever runs with
your key. When a new version of AAPS Builder is released, you get an issue (and an e-mail) in your repository with
2-minute update instructions. / Ditt repo är helt fristående: ingen kod utifrån kör någonsin med din nyckel. När en ny
version av AAPS Builder släpps får du ett ärende (och ett mejl) i ditt repo med instruktioner för att uppdatera.

## ⚠️ Before every update / Före varje uppdatering

1. AAPS → Maintenance → **Export settings** / Underhåll → **Exportera inställningar**
2. Copy the exported file **off the phone** (Google Drive, Dropbox…), together with the APK files. Keep several older
   exports. / Kopiera filen **utanför telefonen** (Google Drive, Dropbox…) tillsammans med APK-filerna. Spara flera
   äldre exporter.

[How to export settings](https://androidaps.readthedocs.io/en/latest/Maintenance/ExportImportSettings.html) ·
[AAPS FAQ: how to organize backups](https://androidaps.readthedocs.io/en/latest/UsefulLinks/FAQ.html#how-to-organize-my-backups)

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

# Privacy Policy

**Wingman** — Effective Date: 2025-01-01

---

## Summary

Wingman is designed as a **local-first** application. When you use only local
AI and local transcription, your audio, transcripts, and coaching data stay
on your Mac. If you enable optional cloud providers in Settings, only the
data needed for those features is sent to the providers you choose.

---

## What Data We Collect

**We collect nothing.**

Wingman does not connect to any remote server operated by us, does not
create accounts, and does not transmit any usage analytics or telemetry.

---

## What Stays on Your Device

All of the following are stored **only** on your Mac, in the directory you
choose (default: `~/Library/Application Support/com.getwingman/` on macOS,
or the project `data/` folder when running from source):

| Data | Where |
|---|---|
| Audio during live sessions | Processed in RAM; not written to disk for the main capture path |
| Practice mode recordings | Temporary WAV files used only for transcription; deleted after use |
| Transcripts | `sessions/<date>/` under the app data directory |
| AI coaching suggestions | `sessions/<date>/` |
| Session summaries & action items | `sessions/<date>/` |
| Your HR documents (CV, job descriptions) | `knowledge_base/` + `chroma_db/` |
| App settings | `.env` in the app support directory or project directory |

---

## Third-Party Services Used Locally

Wingman optionally uses these **locally-running** services:

| Service | Purpose | Network? |
|---|---|---|
| [Ollama](https://ollama.com) | Runs the LLM (e.g. Mistral) on your Mac | Local only (`localhost:11434`) |
| [mlx-whisper](https://github.com/ml-explore/mlx-examples) | Speech-to-text on Apple Silicon | Local only |
| [openai-whisper](https://github.com/openai/whisper) | Speech-to-text on Intel Mac | Local only |
| [ChromaDB](https://www.trychroma.com) | Vector database for document search | Local only |

None of these services send your data to the cloud when used through Wingman.

---

## Optional Cloud Integrations

You may optionally connect Wingman to third-party services. **If you use these,
your transcript text, summaries, or other content may be sent to the
corresponding provider.** Only enable them if you accept their privacy policies.

### LLM providers (OpenAI, Anthropic, Gemini, Groq, OpenRouter)
If you set an API key in Settings and choose a cloud LLM provider, your
session transcripts and prompts are sent to that provider to generate
coaching suggestions, summaries, and feedback. Use the local "Ollama" provider
to keep all LLM processing on your Mac.

### Transcription (OpenAI, Groq, Deepgram)
If you choose a cloud transcription provider in Settings, audio or audio-derived
data may be sent to that provider for speech-to-text. Use "Local" transcription
to keep transcription on your Mac.

### Notion
If you configure a Notion token (`NOTION_TOKEN` in Settings), Wingman
will export session summaries to your Notion workspace using Notion's official
API. The data sent is limited to:
- Session title and date
- Meeting summary text
- Action items extracted from the session

No audio or full transcripts are sent to Notion.
Notion's own [Privacy Policy](https://www.notion.so/Privacy-Policy-3468d120cf614d4c9014c09f6adc9091)
governs how they handle your data.

### DuckDuckGo (Practice Mode only)
The Practice Interview feature can search for publicly available information
about companies and job roles using DuckDuckGo's web search API. Queries are
sent to DuckDuckGo's servers. DuckDuckGo does not build user profiles or track
searches. See [DuckDuckGo's Privacy Policy](https://duckduckgo.com/privacy).

---

## Microphone & Accessibility Permissions

macOS will prompt you to grant:

- **Microphone** — required to capture your voice (and, in non–App Store builds,
  system audio when using BlackHole). Wingman only captures when you start a
  session.
- **Accessibility** (non–App Store builds only) — used to detect when a
  supported video-call app (Google Meet, Teams, WhatsApp) is in the foreground
  so sessions can start automatically. Not used in the Mac App Store edition,
  where you start sessions manually.

Permissions are granted through macOS System Settings and can be revoked at any time.

---

## Recording consent

You are responsible for complying with local laws on recording conversations.
By using Wingman to capture or transcribe a call, you confirm that you have
the right to do so (e.g. you are a participant and the jurisdiction allows
one-party consent, or you have obtained consent from all parties). See
[TERMS.md](TERMS.md) for more on responsible use.

---

## Data Deletion

Because all data is stored locally, you control it completely:

- **In the app:** Use History to delete individual sessions, or Settings →
  Data & storage to clear all sessions or the knowledge base.
- **On disk:** Delete the app data folder (e.g. `~/Library/Application Support/com.getwingman/`)
  to remove everything.

---

## Children's Privacy

Wingman is not directed at children under 13 and does not knowingly
collect any information from children.

---

## Changes to This Policy

If this policy changes materially, the updated file will be included in the
next software release. You can always find the current version in the
application bundle or at the project repository.

---

## Contact

For privacy questions, open an issue on the project repository.

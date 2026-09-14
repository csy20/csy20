<div align="center">

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=24&pause=1200&color=00F707&center=true&vCenter=true&width=640&lines=hii+I+am+~csy20;Backend+%26+Applied+ML;speech-relay+%C2%B7+2505ms+e2e)](https://github.com/csy20/speech-relay)

# Chitresh Yadav

**Backend & Applied ML Engineer** — streaming speech systems, measured latency, backends that actually run.

[![Portfolio](https://img.shields.io/badge/portfolio-csy20.me-00F707?style=flat-square&logo=vercel&logoColor=white)](https://csy20.me)
[![Resume](https://img.shields.io/badge/resume-csy20__resume.pdf-00F707?style=flat-square&logo=adobeacrobatreader&logoColor=white)](https://github.com/csy20/csy20/blob/main/csy20_resume.pdf)
[![LinkedIn](https://img.shields.io/badge/linkedin-csy20-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/csy20/)
[![GitHub](https://img.shields.io/badge/github-csy20-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/csy20)
[![X](https://img.shields.io/badge/x-@the__csy20-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/the__csy20)
[![Email](https://img.shields.io/badge/email-chitreshy20@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:chitreshy20@gmail.com)

B.Tech — Computer Science and Business Systems, SSTC Bhilai · May 2026  
Open to **SDE-1 / Backend / Applied ML**.

</div>

I like work you can measure and ship. Streaming ASR → MT → TTS over WebRTC with hop-level latency. Queue-backed workers in Docker Compose. Flutter on the Play Store, not just in a repo.

Currently: LoRA fine-tuning Whisper for Hindi–English code-mixed ASR, then serving it from a Rust ONNX runtime.

---

## Featured — [speech-relay](https://github.com/csy20/speech-relay)

Real-time **speech-to-speech translation**. Live mic audio in, translated speech out, over WebRTC — not a wav-in / wav-out demo.

<div align="center">
  <a href="https://github.com/csy20/speech-relay">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=csy20&repo=speech-relay&theme=github_dark&hide_border=true&title_color=00F707&icon_color=00F707&text_color=c9d1d9&bg_color=0D1117" alt="speech-relay GitHub card"/>
  </a>
</div>

<p align="center">
  <img src="./assets/speech-relay.svg" alt="speech-relay pipeline: mic → WebRTC → Silero VAD → faster-whisper ASR → IndicTrans2 MT → TTS → N listeners" />
</p>

`faster-whisper` · IndicTrans2 / OPUS-MT · Coqui / edge-tts · aiortc · Silero-VAD · ONNX Runtime · asyncio

| Hop | mean | p50 | p95 |
|-----|------|-----|-----|
| ASR | 707 ms | 706 ms | 798 ms |
| MT | 579 ms | 570 ms | 766 ms |
| TTS | 1218 ms | 1203 ms | 1437 ms |
| **E2E** | **2505 ms** | **2580 ms** | **2934 ms** |

- Built a streaming ASR → MT → TTS service that returns live EN→HI audio over WebRTC, instrumented **per hop** (n = 11, CPU, `faster-whisper tiny/int8`).
- Replaced fixed-window flushing with **Silero-VAD** segmentation and tuned buffers — **23.6%** lower end-to-end latency versus the fixed-window path.
- One **shared ASR stream** fans out to N listeners with independent translation targets — **1.56×** parallel efficiency at 2 listeners (Hindi + Spanish).
- Quantized ASR/TTS with ONNX Runtime fp16/int8 (**up to 11.3%** faster) and added a **WER/CER + latency** eval harness.

**[code](https://github.com/csy20/speech-relay)** · **[eval numbers](https://github.com/csy20/speech-relay/blob/main/eval/results.md)** · **[demo notes](https://github.com/csy20/speech-relay/blob/main/DEMO.md)**

---

## Selected work

Same set as [csy20_resume.pdf](https://github.com/csy20/csy20/blob/main/csy20_resume.pdf).

**[speech-relay-rust](https://github.com/csy20/speech-relay-rust)** — Indic code-mixed ASR + Rust serving  
`Whisper` · LoRA / PEFT · PyTorch · ONNX · Rust (`ort`) · MUCS / OpenSLR-104

Data pipeline over MUCS Hindi–English speech (16 kHz resample, Devanagari + Latin filter, train/val/test). LoRA on Whisper decoder attention (`q/k/v/out`) so mid-utterance language switches stick. Serving path: merge LoRA → export encoder/decoder to ONNX → int8 → inference from a Rust `ort` service, outside Python.

**[MediaPipe AI](https://github.com/csy20/mediapipe-ai)** — distributed media pipeline  
`React` · Express · Python workers · Redis · PostgreSQL · MinIO · Docker Compose · Whisper · BART

Five-container system: React client → Express REST gateway → Redis job queue → Python workers (transcription + summarization) → PostgreSQL metadata + MinIO object storage. Async job polling, structured logging, S3-compatible uploads up to 500 MB so workers scale independently of the API.

**[router-agent](https://github.com/csy20/router-agent)** — token-efficient LLM router · AMD Hackathon ACT II  
`Python` · Docker · Ollama · Fireworks API · OpenTelemetry / SigNoz

Hybrid router that classifies tasks (math, NER, summarization, code, QA) with **zero-token** heuristics, then escalates to a local 1.5B LLM or at most **one** paid API call. Classify → local → API stages traced with OpenTelemetry into SigNoz; shipped as a Docker service with schema validation.

**[ByteWise](https://play.google.com/store/apps/details?id=com.csy20.bytewise)** — Flutter learning app · [Play Store](https://play.google.com/store/apps/details?id=com.csy20.bytewise)  
`Flutter` · Riverpod · GoRouter · Drift / SQLite · Google Sign-In · Material 3

Shipped to Google Play. 788+ lessons across DSA, system design, and six languages. Offline-first two-tier cache (in-memory + Drift) so startup I/O stays cheap.

Also shipping: **[contribute-pulse](https://csy20.me/contribute-pulse/)** — live board of OSS repos that will actually notice a PR · **[Nen](https://github.com/csy20/nen)** — Flutter music player with a real-time GLSL visualiser (Play Store closed testing).

---

## Stack

<p>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white" alt="Rust"/>
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript"/>
<img src="https://img.shields.io/badge/Dart-0175C2?style=flat-square&logo=dart&logoColor=white" alt="Dart"/>
<img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white" alt="SQL"/>
</p>

<p>
<img src="https://img.shields.io/badge/faster--whisper-111111?style=flat-square" alt="faster-whisper"/>
<img src="https://img.shields.io/badge/ONNX%20Runtime-005CED?style=flat-square&logo=onnx&logoColor=white" alt="ONNX Runtime"/>
<img src="https://img.shields.io/badge/WebRTC-333333?style=flat-square&logo=webrtc&logoColor=white" alt="WebRTC"/>
<img src="https://img.shields.io/badge/LoRA%20%2F%20PEFT-FF6F00?style=flat-square" alt="LoRA / PEFT"/>
<img src="https://img.shields.io/badge/OpenTelemetry-000000?style=flat-square&logo=opentelemetry&logoColor=white" alt="OpenTelemetry"/>
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI"/>
<img src="https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white" alt="Express"/>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" alt="Redis"/>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker"/>
<img src="https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white" alt="Flutter"/>
<img src="https://img.shields.io/badge/GCP-4285F4?style=flat-square&logo=googlecloud&logoColor=white" alt="GCP"/>
</p>

Speech / ML — faster-whisper (CTranslate2), Silero-VAD, IndicTrans2 / OPUS-MT, Coqui / edge-tts, LoRA / PEFT, ONNX quantization, WER/CER harnesses, LLM routing

Backend — FastAPI, Express, WebRTC (aiortc), asyncio, Redis queues, PostgreSQL, SQLite, MongoDB, MinIO / S3

Infra — Docker Compose, GitHub Actions, OpenTelemetry / SigNoz, GCP (Cloud Run, Cloud Storage, Firebase), Linux

Mobile — Flutter, Riverpod, Drift / SQLite, GLSL

---

<div align="center">
  <img src="https://raw.githubusercontent.com/csy20/csy20/main/assets/stats.svg" alt="csy20 GitHub stats" width="420" />
  <img src="https://raw.githubusercontent.com/csy20/csy20/main/assets/langs.svg" alt="Top languages" width="300" />
</div>

---

<div align="center">

[![GitHub](https://img.shields.io/badge/github-csy20-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/csy20)
[![LinkedIn](https://img.shields.io/badge/linkedin-csy20-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/csy20/)
[![X](https://img.shields.io/badge/-@the__csy20-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/the__csy20)
[![Instagram](https://img.shields.io/badge/-@the__csy20-E4405F?style=flat-square&logo=instagram&logoColor=white)](https://www.instagram.com/the__csy20/)
[![YouTube](https://img.shields.io/badge/-emt__edits-FF0000?style=flat-square&logo=youtube&logoColor=white)](https://www.youtube.com/@emt__edits20)
[![Buy me a coffee](https://img.shields.io/badge/-buy%20me%20a%20coffee-FFDD00?style=flat-square&logo=buymeacoffee&logoColor=black)](https://coff.ee/the__csy20)

**[csy20.me](https://csy20.me)** · **[resume (csy20_resume.pdf)](https://github.com/csy20/csy20/blob/main/csy20_resume.pdf)** · **[speech-relay](https://github.com/csy20/speech-relay)**

</div>

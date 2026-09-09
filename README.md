<div align="center">

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=26&pause=1200&color=00F707&center=true&vCenter=true&width=560&lines=hii+I+am+~csy20;real-time+speech+systems;Flutter+apps+that+ship)](https://csy20.me)

# Chitresh Yadav

CS graduate building **real-time speech systems** and shipping **Flutter apps** people can actually install.

[![Portfolio](https://img.shields.io/badge/portfolio-csy20.me-00F707?style=flat-square&logo=vercel&logoColor=white)](https://csy20.me)
[![LinkedIn](https://img.shields.io/badge/linkedin-csy20-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/csy20/)
[![X](https://img.shields.io/badge/x-@the__csy20-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/the__csy20)
[![Email](https://img.shields.io/badge/email-chitreshy20@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:chitreshy20@gmail.com)

</div>

I like work you can measure and ship. Streaming ASR → MT → TTS over WebRTC with hop-level latency. Flutter on the Play Store, not just in a repo. Backends that run in Docker Compose, not in a screenshot.

Currently: LoRA fine-tuning Whisper for Hindi–English code-mixed ASR, then serving it from a Rust ONNX runtime.

B.Tech — Computer Science and Business Systems, SSTC Bhilai · graduated April 2026.

---

## Selected work

**[speech-relay](https://github.com/csy20/speech-relay)** — real-time speech-to-speech translation  
`faster-whisper` · IndicTrans2 / OPUS-MT · Coqui / edge-tts · aiortc · ONNX Runtime

Live EN→HI audio over WebRTC. **2505 ms mean / 2580 ms p50** end-to-end, instrumented per hop. Silero-VAD vs fixed-window flushing cut latency **23.6%**. One shared ASR stream fans out to N listeners with independent translation targets (**1.56×** parallel efficiency at 2). ONNX fp16/int8 benches up to **11.3%** faster, plus a WER/CER harness.

**[speech-relay-rust](https://github.com/csy20/speech-relay-rust)** — Indic code-mixed ASR + Rust inference  
`Whisper` · LoRA / PEFT · ONNX Runtime · Rust (`ort`) · MUCS

Two-part systems project: LoRA on Whisper for Hindi–English code-mixed speech (MUCS / OpenSLR-104), then an ONNX export path into a Rust inference runtime. In progress.

**[MediaPipe AI](https://github.com/csy20/mediapipe-ai)** — distributed media pipeline  
`React` · Express · Python · Redis · PostgreSQL · MinIO · Docker Compose

Five-container setup: Whisper transcription + BART summarization behind a queue, with an Express gateway, structured logging, and async job polling.

**[ByteWise](https://play.google.com/store/apps/details?id=com.csy20.bytewise)** — Flutter learning app · [Play Store](https://play.google.com/store/apps/details?id=com.csy20.bytewise)  
`Flutter` · Riverpod · GoRouter · Drift / SQLite · Google Sign-In · Material 3

Shipped to Google Play. 788+ lessons across DSA, system design, and six languages. Offline-first two-tier cache (in-memory + Drift) so startup I/O stays cheap.

**[Nen](https://github.com/csy20/nen)** — Flutter music player · Play Store (closed testing)  
`Flutter` · just_audio · Riverpod · GLSL · CustomPainter

Full-featured player with a real-time GLSL audio visualiser on a Flutter canvas. Handled APK signing and a staged Play Console rollout.

---

## Stack

<p>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white" alt="Rust"/>
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript"/>
<img src="https://img.shields.io/badge/Dart-0175C2?style=flat-square&logo=dart&logoColor=white" alt="Dart"/>
<img src="https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++"/>
</p>

<p>
<img src="https://img.shields.io/badge/faster--whisper-111111?style=flat-square" alt="faster-whisper"/>
<img src="https://img.shields.io/badge/ONNX%20Runtime-005CED?style=flat-square&logo=onnx&logoColor=white" alt="ONNX Runtime"/>
<img src="https://img.shields.io/badge/WebRTC-333333?style=flat-square&logo=webrtc&logoColor=white" alt="WebRTC"/>
<img src="https://img.shields.io/badge/LoRA%20%2F%20PEFT-FF6F00?style=flat-square" alt="LoRA / PEFT"/>
<img src="https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white" alt="Flutter"/>
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI"/>
<img src="https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white" alt="Express"/>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" alt="Redis"/>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker"/>
<img src="https://img.shields.io/badge/GCP-4285F4?style=flat-square&logo=googlecloud&logoColor=white" alt="GCP"/>
<img src="https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black" alt="Firebase"/>
</p>

Speech / ML — faster-whisper (CTranslate2), Silero-VAD, IndicTrans2 / OPUS-MT, Coqui / edge-tts, ONNX quantization, asyncio streaming, WER/CER harnesses

Mobile — Flutter, Riverpod, Provider, BLoC, Drift / SQLite, GLSL

Backend & data — FastAPI, Express, PostgreSQL, SQLite, Firestore, MongoDB, Redis

Infra — GCP (Cloud Run, Cloud Storage, Firebase), Docker Compose, GitHub Actions

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

**[csy20.me](https://csy20.me)** · [resume](https://drive.google.com/uc?export=download&id=1FvyG1rvcAQxYL9OQWI6UtF6zX7-lsmAN)

</div>

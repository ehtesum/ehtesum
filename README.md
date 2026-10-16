# Ehtesum-Ul-Islam

**Software Engineer & Systems Researcher**  
Specializing in High-Throughput Backend Systems, Network Protocol Engineering, and Applied AI.

[Portfolio & CV](https://ehtesum.github.io/portfolio_web/) • [LinkedIn](https://linkedin.com/in/ehtesum-ul-islam-01274a166/) • [Email](mailto:ehtesumulislam@gmail.com) • Lappeenranta / Helsinki, Finland

---

## About Me

I build resilient backend services, high-throughput network daemons, and privacy-respecting AI tools. My work sits at the intersection of systems programming (C++, Python, Linux), cloud infrastructure, and practical machine learning. 

- **M.Sc. in Software Engineering & Digital Transformation** — LUT University, Finland *(Dec 2025)*
- **B.Sc. in Computer Science & Engineering** — North South University, Bangladesh *(2021)*
- **Engineering Philosophy**: DRY & KISS. I prioritize deterministic performance, explicit error boundaries, and zero-telemetry offline capabilities over unnecessary SaaS dependencies.

---

## 1. Backend & Systems Infrastructure

### [5G NR PDCP Reordering Engine (5G_reorder)](https://github.com/ehtesum/5G_reorder)
*C++17 • POSIX Sockets • 3GPP TS 38.323 • Multi-threaded Systems*
- A high-performance user-space networking engine implementing 3GPP 5G New Radio PDCP sequence reordering over raw UDP.
- Decouples high-rate asynchronous socket ingestion from packet ordering via a bounded, thread-safe queue (`std::mutex` + `std::condition_variable`).
- Resolves packet loss and out-of-order arrivals using sliding-window state tracking (`RX_NEXT`, `RX_DELIV`, `RX_REORD`) with a dedicated `t-Reordering` timer gap flush thread.

### [LinkPreviewAPI](https://github.com/ehtesum/link_preview_api)
*FastAPI • Python 3.13 • Redis • SSRF Security Shield • Async HTTPX*
- Low-latency URL metadata and OpenGraph scraping microservice responding in < 40 ms.
- Features a zero-trust **SSRF security shield** that resolves destination hostnames and inspects target IPs before HTTP execution, blocking loopback addresses, RFC 1918 private subnets, and AWS/GCP cloud metadata endpoints (`169.254.169.254`).
- Multi-tier caching with Redis and automatic in-memory fallback, memory-bounded 1 MB response streaming, and fallback parsing (`og:*` ➔ `twitter:*` ➔ standard HTML tags). Includes a 33-test automated test suite.

### [ServerMonitor](https://github.com/ehtesum/server_monitor)
*Python • Docker Engine API • systemd • Linux Observability*
- Ultralight (< 15 MB RAM) single-node VPS, Docker container, and TLS certificate watchdog daemon designed as a zero-bloat alternative to heavy 500MB+ Prometheus/Grafana stacks on modest cloud droplets.
- Auto-discovers Docker containers via local unix sockets (`/var/run/docker.sock`), traps ungraceful exits and OOM crashes, and embeds the last 10 lines of stderr in real-time alerts.
- Two-way Telegram bot commands (`/status`, `/restart <container>`) with strict chat-ID gating, alert cooldown throttling, and cross-platform metric sampling.

### [InvoiceManager](https://github.com/ehtesum/invoice_manager)
*Django 5 / 6 • Python • SQLite / PostgreSQL • Celery • WeasyPrint*
- Self-hosted billing, time-tracking, and client management platform built to eliminate recurring SaaS accounting fees for independent contractors.
- Dynamic invoice calculation with zero-penny-drift integer cent math, custom tax rates, and discount boundary capping.
- Secure, passwordless UUIDv4 client portals (`/portal/<uuid>/`) featuring automated read receipts (`SENT` ➔ `VIEWED`) and asynchronous background overdue payment reminders.

### [Graphics Reverse Benchmarks](https://github.com/ehtesum/graphics_reverse)
*C++ • GPU Architecture • Micro-benchmarking*
- Silicon-level micro-benchmarks measuring warp divergence penalties, shared memory bank conflicts, and multi-level cache line latency across modern graphics architectures.

---

## 2. AI & Applied Machine Learning Systems

### [LocalForge AI](https://github.com/ehtesum/localforge_ai_code)
*Python • Quantized LLMs • llama.cpp / Ollama • VS Code Extension*
- Private, air-gapped developer copilot server and companion editor extension.
- Executes local quantized models (Qwen, DeepSeek, Llama) with AST-aware context injection. Zero telemetry, zero external network traffic, and full privacy for sensitive codebases.

### [Kantho Voice Model](https://github.com/ehtesum/kantho_voice_model)
*PyTorch • Neural TTS • Voice Cloning • Audio DSP*
- Zero-shot Bengali voice cloning and speech synthesis architecture.
- Handles phonetic Banglish transliteration, prosody extraction, and pitch contour preservation across diverse regional accents.

### [WiFiWallSense (WiFiDensePose)](https://github.com/ehtesum/wifidensepose_wifi)
*Python • RF Signal Processing • 802.11 CSI • NumPy / SciPy*
- Device-free, camera-free human presence and motion detection using raw 802.11 Wi-Fi Channel State Information (CSI).
- Analyzes subcarrier phase shifts and amplitude variance across OFDM channels to detect micro-movements and room occupancy through solid walls.

### [Multimodal KG Reasoning (SEAL)](https://github.com/ehtesum/seal_with_kg_no_hallucination)
*Knowledge Graphs • RDF / SPARQL • Multi-Agent Systems • LLMs*
- Architecture designed to suppress LLM hallucinations by anchoring generative inference to structured Knowledge Graph facts and cross-agent consensus verification.

### [OmniWrite Pro (GrammarFix)](https://github.com/ehtesum/grammer_fix)
*Python • Desktop GUI • NLP • AST Analysis*
- Local desktop writing assistant featuring offline AST-based grammar linting, style analysis, and localized semantic originality checking.

---

## 3. Distributed Web, Mobile & Security Tools

### [FileShare](https://github.com/ehtesum/file_share)
*WebRTC DataChannels • Vanilla JavaScript • Node.js WebSocket Signaling*
- Zero-cloud, browser-to-browser P2P file and text transfer over local Wi-Fi.
- Streams files directly device-to-device at full router speed (50–100 MB/s) with 64 KB binary chunking, active backpressure control (`bufferedAmountLow`), and DTLS/SCTP encryption.

### [BillSplitter](https://github.com/ehtesum/bill_splitter)
*React 18 • TypeScript • Tailwind CSS • Vite*
- Offline group expense calculator with zero logins and zero database dependencies.
- Implements a greedy bipartite graph algorithm to collapse tangled multi-party debts down to the minimal number of direct transfers.
- Encodes the full group ledger directly into the URL hash (`#data=...`) or renders it as a scannable QR code for instant offline peer synchronization.

### [VaultX](https://github.com/ehtesum/vaultx_pswrd_mngr_andrd)
*Kotlin • Jetpack Compose • Android Keystore • AES-256-GCM*
- Hardware-backed, zero-network Android credential safe.
- Encrypts vault records using keys generated inside the Android hardware Secure Element / StrongBox, supporting biometric authentication and automated clipboard clearing.

### [SubTracker](https://github.com/ehtesum/sub_tracker)
*Kotlin • Jetpack Compose • Room SQLite • AlarmManager*
- Privacy-first offline Android subscription manager.
- Features exact alarm renewal reminders at 09:00 AM, free trial expiration guards, and normalized monthly/yearly spending forecasts with zero network permissions.

### [GhostTrace](https://github.com/ehtesum/ghosttrace_delete_from_internet)
*Python • OSINT Reconnaissance • Privacy Engineering*
- Digital footprint reconnaissance scanner querying 180+ public web endpoints to map account exposure, paired with automated GDPR/CCPA Article 17 right-to-erasure request generators.

### [TexFlow](https://github.com/ehtesum/texflow_oveleaf_type_thing)
*JavaScript • CodeMirror • WebAssembly TeX Engine*
- Lightweight, offline browser-based LaTeX editor and Overleaf alternative with split-pane editing, live syntax highlighting, and client-side PDF rendering.

---

## Publications & Academic Research

- **"Low-Cost Heart Rate Sensor and Mental Stress Detection Using Machine Learning"**  
  *5th International Conference on Trends in Electronics and Informatics (ICOEI 2021)*  
  IEEE Xplore • [DOI: 10.1109/ICOEI51242.2021.9452873](https://doi.org/10.1109/ICOEI51242.2021.9452873)

- **"Empirical Investigation of DevSecOps Practices, Automation, and Security Pipeline Integration in Cloud Infrastructure"**  
  *M.Sc. Thesis, LUT University (Dec 2025)*  
  Focus on automated vulnerability remediation, CI/CD pipeline security gates, and infrastructure reliability across cloud architectures.

---

## Technical Stack & Competencies

| Domain | Technologies & Standards |
| :--- | :--- |
| **Backend & Systems** | C++17/20, Python 3.13, Django, FastAPI, Node.js, POSIX Concurrency, REST, Redis |
| **Networking & Protocols** | 3GPP 5G NR (PDCP TS 38.323, RLC AM, GTP-U), WebRTC DataChannels, UDP/TCP Sockets, TLS, Wireshark |
| **AI & Machine Learning** | PyTorch, HuggingFace Transformers, Quantized LLM Inference (llama.cpp, Ollama), Knowledge Graphs, Audio DSP |
| **Mobile & Security** | Kotlin, Jetpack Compose, Room SQLite, Android Keystore (AES-256-GCM), SSRF Defense, AST Linting |
| **DevOps & Cloud** | Linux, Docker, Docker Compose, systemd, Kubernetes, GitHub Actions CI/CD, Microsoft Azure |

---

## Contact

- **Email**: [ehtesumulislam@gmail.com](mailto:ehtesumulislam@gmail.com)
- **LinkedIn**: [linkedin.com/in/ehtesum-ul-islam-01274a166](https://linkedin.com/in/ehtesum-ul-islam-01274a166/)
- **Web Portfolio**: [ehtesum.github.io/portfolio_web](https://ehtesum.github.io/portfolio_web/)

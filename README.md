# Ehtesum-Ul-Islam

**Software Engineer & Systems Researcher**  
Specializing in High-Throughput Backend Systems, Network Protocol Engineering, and Reliable AI Architectures.

[Portfolio & CV](https://ehtesum.github.io/portfolio_web/) • [LinkedIn](https://linkedin.com/in/ehtesum-ul-islam-01274a166/) • [Email](mailto:ehtesumulislam@gmail.com) • Finland

---

## About Me

I build resilient backend services, high-throughput protocol engines, and calibrated AI architectures. My work focuses on deterministic systems engineering (C++, Python, Linux), cloud security, and reliable machine learning where model hallucination or uncalibrated failure carries real-world cost.

- **M.Sc. in Software Engineering & Digital Transformation** — LUT University, Finland *(Dec 2025)*
- **B.Sc. in Computer Science & Engineering** — North South University, Bangladesh *(2021)*
- **Core Engineering Principles**: DRY & KISS. I prioritize deterministic performance, explicit error boundaries, and zero-telemetry offline capabilities over unnecessary SaaS dependencies.

---

## Featured Projects (5 Core Contributions)

### 1. [5G NR PDCP Reordering Engine (5G_reorder)](https://github.com/ehtesum/5G_reorder)
*Backend & Protocol Engineering • C++17 • POSIX Sockets • 3GPP TS 38.323*

A lightweight, high-performance user-space networking daemon implementing 3GPP 5G New Radio PDCP sequence reordering over raw UDP.
- **Architecture**: Decouples high-rate asynchronous socket ingestion from packet ordering via a bounded, thread-safe queue (`std::mutex` + `std::condition_variable`).
- **Sliding-Window State Machine**: Tracks sequence frontiers (`RX_NEXT`, `RX_DELIV`, `RX_REORD`) and resolves packet loss or network jitter using a dedicated, low-jitter `t-Reordering` timer flush thread.
- **Zero-Copy Serialization**: Parses 12-bit and 18-bit PDCP Sequence Numbers with minimal memory reallocation.

---

### 2. [LinkPreviewAPI](https://github.com/ehtesum/link_preview_api)
*Backend Microservices & Cloud Security • FastAPI • Python 3.13 • Redis*

A high-throughput URL preview and OpenGraph enrichment microservice responding in < 40 ms, engineered to defeat SSRF attacks.
- **Zero-Trust SSRF Shield**: Resolves destination hostnames and inspects underlying IPv4/IPv6 addresses before making outbound network calls. Automatically blocks RFC 1918 private subnets (`10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`), loopbacks, and AWS/GCP cloud metadata endpoints (`169.254.169.254`).
- **Resource Bounds & Caching**: Enforces a strict 5.0s timeout and 1 MB body truncation to prevent RAM exhaustion. Integrates Redis caching (with in-memory dictionary fallback) for sub-1ms repeat lookups.
- **Automated Test Coverage**: 33 passing test suites covering 20+ SSRF bypass attack vectors, malformed HTML resilience, and throughput benchmarks.

---

### 3. [Diagnostic-Guided Deliberation Framework (dgd-framework)](https://github.com/ehtesum/dgd-framework)
*AI Reasoning & Test-Time Compute • Information Theory • Python • PyTorch*

An information-theoretic controller that steers Large Language Model test-time reasoning under competing hypothesis conditions (e.g. differential diagnosis, complex software root-cause analysis).
- **Expected Diagnostic Value (EDV)**: Dynamically computes conditional mutual information $I(H; Y \mid C, a_t)$ to distinguish discriminative reasoning actions from self-reinforcing confirmatory rationalization loops.
- **Falsification Sentinels**: Detects when generation trajectories enter low-entropy confirmation basins and injects targeted falsification sentinels to evaluate counter-hypotheses before final commitment.
- **Empirical Validation**: Benchmarked across 13,546 trials on DC-Bench (Clinical Medicine, Formal Logic, Software Systems), cutting reasoning token consumption by 11.3% while elevating diagnostic accuracy to 77.4% and reducing latency from 1.66s to 1.00s across Mistral-NeMo (12B), Qwen-2.5 (27B), and GPT-OSS.

---

### 4. [Calibrated 5-Agent Architecture for VDU (MACT_multimodel)](https://github.com/ehtesum/MACT_multimodel)
*Multimodal AI & Multi-Agent Systems • Vision-Language Models • Calibration*

A closed-loop 5-agent architecture that overcomes layout hallucinations, shortcut reasoning, and uncalibrated confidence in multi-page Visual Document Understanding (VDU).
- **Role-Specialized Closed Loop**: Decouples document reasoning into Context Filtering ($A_{\mathrm{ctx}}$), Structured Planning ($A_{\mathrm{plan}}$), Tool Execution ($A_{\mathrm{exe}}$ with OCR/Table/Chart tools), Layout-Loss Cross-Verification ($A_{\mathrm{ver}}$), and Calibrated Decision Fusion ($A_{\mathrm{dec}}$).
- **Calibrated Safe Abstention**: Dynamically computes fused confidence scores $C_{\mathrm{fused}}$ against rigorous confidence thresholds ($\theta_{\mathrm{high}}=0.90, \theta_{\mathrm{med}}=0.65$), outputting an explicit abstention token ($\bot$) when visual evidence is insufficient.
- **Empirical Benchmarks**: Evaluated across 44,175 benchmark trials (DocVQA, ChartQA, TableBench, MMLongBench-Doc). Achieves 92.4% ANLS on DocVQA and slashes Expected Calibration Error (ECE) from 0.1480 down to 0.0142.

---

### 5. [Knowledge-Graph–Grounded SEAL (seal_with_kg_no_hallucination)](https://github.com/ehtesum/seal_with_kg_no_hallucination)
*Neuro-Symbolic AI & Hallucination Mitigation • RDF Graphs • SPARQL • PyTorch*

A hallucination-suppressed dialogue architecture that couples Selective Abstention Learning (SEAL) with a dynamic RDF Knowledge Graph for safety-critical interactions (e.g. mental health consultation).
- **Dynamic Entity Linking**: Ingests unstructured user dialogue, extracts clinical symptoms, and links entities to an active RDF semantic knowledge graph.
- **SEAL Abstention Gate**: Evaluates inferred disorder subgraphs against empirical confidence margins. If the knowledge graph cannot verify the inference, the gate triggers selective abstention (`[REJ]`), preventing models from generating ungrounded or hazardous advice.
- **Implementation**: Fully reproducible neuro-symbolic pipeline with PyTorch LoRA adapters, SPARQL graph query engines, and automated safety evaluation scripts.

---

## Other Notable Engineering Projects

| Project | Domain | Tech Stack | Overview |
| :--- | :--- | :--- | :--- |
| **[ServerMonitor](https://github.com/ehtesum/server_monitor)** | DevOps | Python, Docker API, systemd | < 15 MB RAM single-node VPS, Docker container, and TLS certificate watchdog with two-way Telegram bot commands. |
| **[FileShare](https://github.com/ehtesum/file_share)** | WebRTC / P2P | Vanilla JS, WebRTC, Node.js | Zero-cloud, browser-to-browser P2P file and text transfer over local Wi-Fi with 64 KB backpressure chunking (50–100 MB/s). |
| **[BillSplitter](https://github.com/ehtesum/bill_splitter)** | Web App | React 18, TypeScript, Tailwind | Offline group expense calculator with greedy bipartite debt minimization (O(V+E)) and zero-backend URL hash / QR sync. |
| **[VaultX](https://github.com/ehtesum/vaultx_pswrd_mngr_andrd)** | Mobile / Security | Kotlin, Jetpack Compose, Keystore | Offline Android password manager using AES-256-GCM backed by hardware StrongBox / Secure Element enclaves. |
| **[SubTracker](https://github.com/ehtesum/sub_tracker)** | Android | Kotlin, Jetpack Compose, Room | Privacy-first offline subscription manager with exact `AlarmManager` renewal alerts and normalized spend forecasting. |
| **[WiFiWallSense](https://github.com/ehtesum/wifidensepose_wifi)** | RF Sensing | Python, 802.11 CSI, NumPy/SciPy | Device-free passive motion and presence detection analyzing raw Wi-Fi OFDM subcarrier variance through solid walls. |
| **[InvoiceManager](https://github.com/ehtesum/invoice_manager)** | Full-Stack | Django 5, PostgreSQL, Celery | Self-hosted freelance invoicing platform with passwordless UUIDv4 portals, zero-drift math, and auto-reminders. |
| **[GhostTrace](https://github.com/ehtesum/ghosttrace_delete_from_internet)** | OSINT / Privacy | Python, Asyncio | Digital footprint reconnaissance scanning 180+ endpoints with automated GDPR/CCPA Article 17 erasure requests. |

---

## Academic Publications & Research

- **"Low-Cost Heart Rate Sensor and Mental Stress Detection Using Machine Learning"**  
  *5th International Conference on Trends in Electronics and Informatics (ICOEI 2021)*  
  IEEE Xplore • [DOI: 10.1109/ICOEI51242.2021.9452873](https://doi.org/10.1109/ICOEI51242.2021.9452873)

- **"Empirical Investigation of DevSecOps Practices, Automation, and Security Pipeline Integration in Cloud Infrastructure"**  
  *M.Sc. Thesis, LUT University (Dec 2025)*  
  Research on automated vulnerability analysis, CI/CD security gating, container hardening, and cloud reliability engineering.

---

## Technical Stack & Competencies

| Category | Technologies & Tools |
| :--- | :--- |
| **Languages** | C++ (C++17/20), Python 3.13, Kotlin, TypeScript, SQL, Bash |
| **Backend & Systems** | POSIX Concurrency (`std::mutex`, pthreads), FastAPI, Django, Node.js, Redis, Zero-Trust Architecture |
| **Networking & Protocols** | 3GPP 5G NR (PDCP TS 38.323, RLC AM, GTP-U), WebRTC DataChannels, UDP/TCP Sockets, TLS Handshakes |
| **AI & Machine Learning** | PyTorch, HuggingFace Transformers, Quantized LLM Inference, Knowledge Graphs (RDF/SPARQL), Vision-Language Models |
| **Cloud & DevOps** | Linux, Docker, Docker Compose, systemd, Kubernetes, GitHub Actions CI/CD, Microsoft Azure |

---

## Contact

- **Email**: [ehtesumulislam@gmail.com](mailto:ehtesumulislam@gmail.com)
- **LinkedIn**: [linkedin.com/in/ehtesum-ul-islam-01274a166](https://linkedin.com/in/ehtesum-ul-islam-01274a166/)
- **Web Portfolio**: [ehtesum.github.io/portfolio_web](https://ehtesum.github.io/portfolio_web/)

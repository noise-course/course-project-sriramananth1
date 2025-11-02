# Project Title

Extending NetML’s Flow2Features: Temporal and Rate-Based Video Streaming Inference

---

## Project Participants

| First Name | Last Name | cnet ID | Project Role |
|-------------|------------|----------|----------------|
| Johnston | Liu | johnstonliu | Low level design and implementation |
| Sriram | Ananthakrishnan | srirama1 | Data collection and analysis |
| Leon | Luo | leonluo | Feature engineering and evaluation |

---

## Project Description

Existing network feature extraction libraries like NetML convert packet captures into flow-level features, but they primarily capture static aggregates such as mean inter-arrival time (IAT) or packet counts. For video streaming traffic, which is bursty and segment-based, these representations fail to capture temporal variation that reflects playback quality. This project extends NetML’s `flow2features` module with segment-aware temporal and rate-based features—such as segment download rate and burst variability—to improve inference of streaming quality from encrypted traffic.

Inferring video quality from encrypted traffic is an important open problem in network monitoring and performance optimization. This work connects directly to the course theme of applying machine learning to networking data. Prior research in encrypted traffic classification (e.g., QUIC and HTTPS inference) has shown that temporal dynamics can reveal underlying service quality. Our goal combines research and applied development: to evaluate the effectiveness of new features and contribute upstream improvements to NetML.

---

## Data

We will collect network traces from Netflix and YouTube streaming sessions using Wireshark and nPrint. Since payloads are encrypted, segment boundaries will be inferred heuristically (for example, by identifying gaps greater than one second between bursts). Labels will be derived from observable playback behavior such as resolution changes, rebuffering events, or bitrate plateaus. Approximately 10–15 sessions per service will be recorded, producing around 100 MB of packet capture data. These captures will be processed with NetML and the extended feature extraction module.

---

## Deliverables

- Extended NetML module implementing new temporal and rate-based features  
- Evaluation report comparing baseline NetML features with the extended feature set using metrics such as accuracy, F1-score, and ROC-AUC  
- Documentation and, if feasible, a pull request to the main NetML repository  
- Final presentation summarizing methods, results, and insights into encrypted streaming traffic inference

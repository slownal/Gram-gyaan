# 🌾 Gram-Gyaan: The Delta-Update Technical Tutor
### *High-Impact AI Education for Low-Bandwidth Communities*

**Gram-Gyaan** is an AI-powered, offline-first learning platform built for the **AWS AI for Bharat Hackathon**. It solves the "Bandwidth Barrier" by treating knowledge like code—syncing only what has changed to keep technical education accessible on less than **2MB of data per week**.

---

## 🚀 The Problem: The Bandwidth Barrier
In rural "shadow zones," students face a massive digital divide:
* **Data Heavy:** Educational videos (50MB+) and PDFs are impossible to download on 2G/3G networks.
* **Connection Instability:** Downloads frequently fail due to intermittent signals.
* **High Cost:** High data consumption creates a financial barrier to technical literacy.

## 💡 The Solution: "Sync & Go"
Instead of streaming media, **Gram-Gyaan** uses a **Differential Sync (Delta) Engine**:
* **Atomization:** Distills complex technical concepts into tiny "Knowledge Nodes" (JSON + ASCII Diagrams).
* **Delta Sync:** Pushes only the specific packets a student is missing since their last connection.
* **Ultra-Compression:** Delivers localized audio summaries at GSM-friendly bitrates.

---

## 🛠 AWS Technical Stack

| Service | Role |
| :--- | :--- |
| **Amazon Bedrock** | Uses **Claude 3.5 Haiku** to distill textbooks into structured "Atomic Nodes". |
| **AWS AppSync** | Manages the **GraphQL Delta Sync** logic for efficient data updates. |
| **Amazon DynamoDB** | Stores versioned knowledge nodes and tracks user sync states. |
| **Amazon Polly** | Generates natural-sounding local language summaries. |
| **AWS Lambda** | Post-processes audio into ultra-low bitrate (8kbps Opus) formats. |

---

## 🏗 System Architecture

1.  **Content Processing:** Bedrock (Haiku) breaks a technical chapter into 2KB-5KB JSON nodes.
2.  **Versioning:** Each node is assigned a version ID in DynamoDB.
3.  **The Sync Engine:** AppSync compares the user's local version with the server and pushes only the "Delta".
4.  **Offline Learning:** Content is cached locally, allowing the student to learn with text, ASCII art, and audio without an active signal.

---


## Real-World Impact
Technical Equity: Enables vocational and "high-tech" learning in zero-speed zones.

Resilience: Resumes sync automatically, making it ideal for rural infrastructure.

Extreme Efficiency: A full week of curriculum fits into the size of a single low-quality photo.

---

## 📂 Knowledge Packet Structure (Example)
```json
{
  "node_id": "NET_101_OSI",
  "version": 4,
  "title": "The Physical Layer",
  "content": "Focuses on bits, cables, and signal voltages.",
  "diagram": "[PC] --- (Cable) --- [Switch]",
  "audio_ref": "s3://gram-gyaan/audio/node_v4.opus",
  "checksum": "a1b2c3d4"
}

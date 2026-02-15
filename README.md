# 🌾 Gram-Gyaan: The Delta-Update Technical Tutor
### *High-Impact AI Education for Low-Bandwidth Communities*

[cite_start]**Gram-Gyaan** is an AI-powered, offline-first learning platform built for the **AWS AI for Bharat Hackathon**. [cite_start]It solves the "Bandwidth Barrier" by treating knowledge like code—syncing only what has changed to keep technical education accessible on less than **2MB of data per week**[cite: 2, 4].

---

## 🚀 The Problem: The Bandwidth Barrier
[cite_start]In rural "shadow zones," students face a massive digital divide[cite: 2]:
* [cite_start]**Data Heavy:** Educational videos (50MB+) and PDFs are impossible to download on 2G/3G networks[cite: 2].
* [cite_start]**Connection Instability:** Downloads frequently fail due to intermittent signals[cite: 2].
* [cite_start]**High Cost:** High data consumption creates a financial barrier to technical literacy[cite: 2].

## 💡 The Solution: "Sync & Go"
[cite_start]Instead of streaming media, **Gram-Gyaan** uses a **Differential Sync (Delta) Engine**:
* [cite_start]**Atomization:** Distills complex technical concepts into tiny "Knowledge Nodes" (JSON + ASCII Diagrams)[cite: 4, 9].
* [cite_start]**Delta Sync:** Pushes only the specific packets a student is missing since their last connection[cite: 4, 11].
* [cite_start]**Ultra-Compression:** Delivers localized audio summaries at GSM-friendly bitrates[cite: 4, 9].

---

## 🛠 AWS Technical Stack

| Service | Role |
| :--- | :--- |
| **Amazon Bedrock** | [cite_start]Uses **Claude 3.5 Haiku** to distill textbooks into structured "Atomic Nodes"[cite: 4, 15]. |
| **AWS AppSync** | [cite_start]Manages the **GraphQL Delta Sync** logic for efficient data updates[cite: 4, 15]. |
| **Amazon DynamoDB** | [cite_start]Stores versioned knowledge nodes and tracks user sync states[cite: 4, 15]. |
| **Amazon Polly** | [cite_start]Generates natural-sounding local language summaries[cite: 4, 15]. |
| **AWS Lambda** | [cite_start]Post-processes audio into ultra-low bitrate (8kbps Opus) formats[cite: 4, 15]. |

---

## 🏗 System Architecture

1.  [cite_start]**Content Processing:** Bedrock (Haiku) breaks a technical chapter into 2KB-5KB JSON nodes[cite: 4, 14].
2.  [cite_start]**Versioning:** Each node is assigned a version ID in DynamoDB[cite: 4, 14].
3.  [cite_start]**The Sync Engine:** AppSync compares the user's local version with the server and pushes only the "Delta"[cite: 11, 12, 14].
4.  [cite_start]**Offline Learning:** Content is cached locally, allowing the student to learn with text, ASCII art, and audio without an active signal[cite: 4, 12].

---

## 📂 Knowledge Packet Structure (Example)
```json
{
  "node_id": "NET_101_OSI",
  "version": 4,
  "title": "The Physical Layer",
  "content": "Focuses on bits, cables, and signal voltages.",
  "diagram": "[PC] --- (Cable) --- [Switch]",
  "audio_ref": "s3://bucket/audio/net_101_v4.opus",
  "checksum": "a1b2c3d4"
}

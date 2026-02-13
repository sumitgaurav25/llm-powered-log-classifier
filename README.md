# Multi-Tiered Log Intelligence: A Hybrid Classification Framework

## 📌 Problem Statement
Modern system infrastructures generate vast amounts of log data that are often unstructured and noisy. Standard rule-based systems are too rigid to handle new log formats, while pure Machine Learning models require extensive labeled datasets. This project addresses the challenge of accurately categorizing logs in dynamic environments where data labels might be scarce or patterns highly variable.

## 🌍 Real-World Problem Solving
This framework is built for SRE (Site Reliability Engineering) and DevOps teams to:
* **Reduce Alert Fatigue:** By filtering out noise using high-speed regex.
* **Automate Root Cause Analysis:** By semantically grouping similar error messages.
* **Handle Unknowns:** Using LLMs to interpret rare, "Black Swan" log events that have never been seen before.

## 🛠 The Hybrid Approach
The system utilizes a three-tier pipeline to maximize efficiency:
1. **Regex Layer:** Instant classification for predictable, recurring patterns.
2. **Semantic Layer:** Uses **Sentence Transformers** and **Logistic Regression** to understand the "meaning" behind complex logs with existing training data.
3. **Reasoning Layer:** Employs **Large Language Models (LLMs)** as a fallback for zero-shot classification when no labels exist.

## 🧠 Challenges Faced
* **Threshold Calibration:** Designing the logic to seamlessly transition between ML and LLM layers without losing context.
* **Performance Optimization:** Integrating heavy transformer models into a responsive FastAPI environment.
* **Pipeline Reliability:** Managing dependencies between different classification engines to ensure a single failed layer doesn't crash the system.

## 📊 Accuracy
The hybrid model provides a robust accuracy profile:
* **High Confidence:** Captured by the deterministic Regex and ML layers.
* **Contextual Depth:** Provided by the LLM layer, ensuring even obscure logs are categorized with high semantic relevance.

---

## 📂 Folder Structure
* `training/`: Logic for model development and regex patterns.
* `models/`: Saved model artifacts.
* `resources/`: Test data and documentation assets.
* `server.py`: The FastAPI application.

## 🚀 Setup & Usage
1. **Install:** `pip install -r requirements.txt`
2. **Run:** `uvicorn server:app --reload`
3. **Process:** Upload a CSV with `source` and `log_message` to receive a classified `target_label` output.

---
*Disclaimer: This project is for educational purposes.*

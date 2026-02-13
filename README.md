# Intelligent Log Classification System

## 📌 Problem Statement

Modern applications generate thousands of log entries every minute. These logs contain critical information for debugging, monitoring, anomaly detection, and security analysis. However, manually reviewing and categorizing logs is:

- Time-consuming  
- Not scalable  
- Prone to human error  

The objective of this project is to design and implement an automated log classification system that can intelligently categorize log messages, even when log formats vary or labeled data is limited.

---

## 🚀 Project Overview

This project implements a hybrid log classification pipeline that adapts based on the structure and complexity of incoming logs.

Instead of relying on a single technique, the system combines:

- Rule-based classification for structured logs  
- Embedding-based supervised learning for moderately complex logs  
- LLM-based reasoning for ambiguous or low-data scenarios  

This layered architecture ensures both speed and robustness.

---

## 🧠 Classification Strategies

### 1️⃣ Rule-Based Pattern Matching
Used for highly structured and predictable log formats.  
Provides fast and deterministic classification.

### 2️⃣ Transformer Embeddings + Logistic Regression
Used when sufficient labeled data is available.

- Log messages are converted into semantic embeddings.
- A Logistic Regression classifier predicts the final label.

This approach balances accuracy and efficiency.

### 3️⃣ LLM-Based Classification
Used when:
- Training data is insufficient  
- Patterns are highly variable  
- Labels are ambiguous  

The LLM acts as a reasoning engine to classify complex logs.

---

## 🏗 System Architecture

1. Logs are received via API.
2. The system determines the most appropriate classification strategy.
3. Prediction is generated.
4. Output is returned with assigned labels.

The system is deployed using a FastAPI server for easy integration.

---

## 📂 Project Structure


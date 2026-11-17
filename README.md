# 🤖 AI Career & Recruitment Assistant Agent

An autonomous, modular Agentic AI system designed to streamline the recruitment process, analyze resumes (CVs), perform deep skill-gap analysis against job descriptions, and act as an interactive mock-interview coach.

> **Note:** This repository is built incrementally as part of an ongoing Agentic AI course project, expanding phase-by-phase from architectural design to full multi-agent tool execution.

---

## 🎯 Problem Statement & Motivation
* **For Recruiters:** Manually screening hundreds of resumes is time-consuming and prone to oversight.
* **For Job Seekers:** Candidates often struggle to identify skill gaps in their resumes or tailor their preparation for specific job roles.
* **The Solution:** An autonomous AI Agent capable of breaking down complex career tasks, utilizing specialized tools to extract and match data, and providing objective, actionable feedback without hallucination.

---

## 🏗️ Phase 1: System Blueprint & Architecture Design

### 1. Use Case
* **Domain:** HR Tech & Career Development.
* **Core Capabilities:** Resume parsing, semantic job matching, skill-gap identification, and personalized technical interview coaching.

### 2. LLM & Provider Configuration
* **Provider:** Hugging Face (Local / Open-Weights Execution via `transformers` & `langchain-huggingface`).
* **Model:** `HuggingFaceTB/SmolLM2-1.7B-Instruct` *(Lightweight instruction-tuned model selected for efficient local reasoning and deterministic tool calling)*.

### 3. Planned Agent Tools
* 🛠️ **`cv_parser_tool`**: Extracts structured entities (skills, experience, education, projects) from raw PDF/text resumes.
* 🔍 **`job_matcher_rag_tool`**: Performs dense vector retrieval over job descriptions and industry requirements.
* 📊 **`skill_gap_analyzer_tool`**: Compares candidate profiles against target role requirements to compute match scores and highlight missing competencies.
* 🎙️ **`mock_interview_coach_tool`**: Generates tailored technical questions and evaluates candidate responses in real time.

### 4. System Prompt
```text
You are an expert, autonomous AI Career and Recruitment Agent. Your mission is to help candidates optimize their career profiles and assist in evaluating talent objectively.

Guidelines:
- Always utilize your available tools (CV Parser, Job Matcher, Skill-Gap Analyzer, and Interview Tool) to gather factual data before providing feedback.
- Be constructive, objective, and precise. Do not hallucinate qualifications or invent hiring criteria.
- Break down complex user requests (e.g., 'Evaluate my CV and prepare me for an interview') into structured sequential steps, invoke the necessary tools, and deliver a comprehensive, actionable response.

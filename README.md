## Overview
A hands-on adversarial security assessment of a local multi-model AI environment 
built using Ollama, evaluating five open-source LLMs — Mistral, Qwen, Gemma, 
Granite, and LLaMA — against real-world attack techniques mapped to the OWASP 
Top 10 for LLM Applications.

## What Was Done
- Deployed and exposed a local Ollama instance across five models for adversarial testing
- Conducted automated prompt injection testing using Garak v0.14, firing 768 attack 
  attempts across three probe types
- Mistral:7b was rated DC-2 (Very High Risk) with attack success rates of:
  - 70.70% on long prompt injection attacks
  - 53.12% on hate-based hijacking
  - 48.83% on kill-command hijacking
- Fingerprinted the hidden backend model of a live RAG-powered chatbot using LLMap,
  identifying Mistral-7B-Instruct-v0.3 purely through response pattern analysis 
  with no internal system access
- Built and open-sourced garak-report-to-excel, a Python utility that parses raw 
  Garak .jsonl vulnerability reports into structured Excel spreadsheets

## OWASP LLM Mapping
Findings were mapped to real-world attack scenarios including data leakage, 
output manipulation, and guardrail bypass.

## Tools Used
Garak v0.14, Ollama, LLMap, Python, Excel

## Screenshots

### Models Under Test
![Models to test](screenshots/01-models-to-test.png)

### Exposing Ollama to Local Network
![Exposing Ollama to local network](screenshots/02-ollama-network-exposure.png)

### Model Fingerprinting with LLMmap
![Model identification with LLMmap](screenshots/03-llmmap-identification.png)

### Successfully Identified the Model
![Successfully identified the model](screenshots/04-llmmap-success.png)

### Prompt Injection with Garak
![Injection with Garak](screenshots/05-garak-injection.png)

### High Risk Identified
![High risk identified](screenshots/06-high-risk.png)

### Successful Injection Types — Percentage Breakdown
![Successful injection types percentage](screenshots/07-injection-percentage.png)

### Raw Garak Output — Messy Prompts and Responses
![Messy prompts and response](screenshots/08-messy-output.png)

### garak-report-to-excel Tool
![My tool for clean response](screenshots/09-garak-report-to-excel.png)

### Clean Output in Excel Format
![Clean prompt and response in Excel](screenshots/10-excel-output.png)

## Related Tool
[garak-report-to-excel](https://github.com/rakibnadir33/garak-report-to-excel)

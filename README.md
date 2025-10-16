# sdalsan_gemini
Tds project files
# TDS Project – Gemini API

This repository contains the source code for my **Task Deployment System (TDS) Project**.

## Project Overview
The project implements a **FastAPI-based API** that receives JSON POST requests containing task briefs, uses an LLM-assisted generator to create minimal apps, deploys them to GitHub, and notifies an evaluation system. It supports multiple rounds of task updates and redeployments.

## Files Included
- `main.py` – FastAPI backend handling task requests and deployments  
- `Dockerfile` – Docker configuration for deploying the API on Hugging Face Spaces  
- `requirements.txt` – Python dependencies for running the project  
- `README.md` – Project description and instructions  
- `LICENSE` – MIT License for the project

## Deployment
The API is deployed on **Hugging Face Spaces** and is accessible here:  
**[https://sdalsan-cool.hf.space/ready](https://sdalsan-cool.hf.space/ready)**

## Usage
1. Send a POST request to `/ready` with a JSON payload containing:
   - `brief`: Description of the app/task
   - `attachments`: Optional task attachments
2. The API will generate the app, push it to a unique GitHub repository, and notify the evaluation system.
3. For round 2 updates, the API can accept another POST with `{"round": 2}` to modify and redeploy the app.

## Notes
- Each generated app is pushed to a **new GitHub repo** named according to the task.  
- The app automatically handles multiple task rounds.  
- Secrets are **never stored in GitHub repos** — only in environment variables.  
- GitHub Pages is enabled for all generated apps, making them publicly accessible.  

## License
This project is licensed under the **MIT License**. See the LICENSE file for details.

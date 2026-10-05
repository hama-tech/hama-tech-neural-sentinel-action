# 🛡️ Neural Sentinel AI TRiSM Scanner

[![Secured by Neural Sentinel](https://img.shields.io/badge/Secured%20by-Neural%20Sentinel-blue?style=for-the-badge&logo=shield)](https://github.com/hama-tech/hama-tech-neural-sentinel-action)

**Automated AI Trust, Risk, and Security Management (TRiSM) for Agentic AI.**  
Blocks Pull Requests containing CWE-269 combinatorial kill-chains, prompt injection vulnerabilities, and unconstrained parameters. Automatically maps findings to the **EU AI Act** and **ISO/IEC 42001**.

---

## 🚀 Quick Start

Add this to your `.github/workflows/neural-sentinel.yml`:

```yaml
name: Neural Sentinel AI Scan
on: [pull_request]

jobs:
  ai-security-scan:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4
      
      - name: Run Neural Sentinel Scanner
        uses: hama-tech/hama-tech-neural-sentinel-action@v1.3
        with:
          # Leave blank for public/open-source repos (Free Community Mode)
          # Email neuralsentinel.sec@proton.me for an Enterprise Key for private repos
          license-key: ${{ secrets.NEURAL_SENTINEL_LICENSE_KEY }} 
          fail-on-severity: 'HIGH' # Options: CRITICAL, HIGH

```






---

## 🔍 How It Works

1. **Static Analysis:** Scans your AI agent schemas (CrewAI, LangGraph, AutoGen) for structural vulnerabilities without needing heavy LLM inference in the CI pipeline.
2. **Compliance Mapping:** Automatically flags violations and maps them to EU AI Act Articles (9, 10, 14, 15) and ISO/IEC 42001 Annex A controls.
3. **Air-Gapped Security:** The scanner runs entirely within your GitHub Actions runner. Your source code and prompts never leave your environment.

---

## 🏢 Enterprise & Private Repositories

The free Community Mode is designed for public, open-source repositories. 

For **private repositories** or enterprise deployments requiring auditor-ready compliance reports, an Enterprise License Key is required. 

📩 **Contact:** `neuralsentinel.sec@proton.me` to request an enterprise license or schedule a technical demo.

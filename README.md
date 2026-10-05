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
        uses: hama-tech/hama-tech-neural-sentinel-action@v1.1
        with:
          # Leave blank for public/open-source repos (Free Community Mode)
          # Email neuralsentinel.sec@proton.me for an Enterprise Key for private repos
          license-key: ${{ secrets.NEURAL_SENTINEL_LICENSE_KEY }} 
          fail-on-severity: 'HIGH' # Options: CRITICAL, HIGH

[![OpenSSF Best Practices](https://www.bestpractices.dev/projects/15266/badge)](https://www.bestpractices.dev/projects/15266)

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
        uses: hama-tech/hama-tech-neural-sentinel-action@v2.0
        with:
          # Leave blank for public/open-source repos (Free Community Mode)
          # Email mohamed@neuralsentinel.online for an Enterprise Key for private repos
          license-key: ${{ secrets.NEURAL_SENTINEL_LICENSE_KEY }} 
          fail-on-severity: 'HIGH' # Options: CRITICAL, HIGH
```






---

## 🔍 How It Works

1. **Static Analysis:** Scans your AI agent schemas (CrewAI, LangGraph, AutoGen, MCP) for structural vulnerabilities without needing heavy LLM inference in the CI pipeline.
2. **Compliance Mapping:** Automatically flags violations and maps them to EU AI Act Articles (9, 10, 14, 15) and ISO/IEC 42001 / 27001 Annex A controls.
3. **Air-Gapped Security:** The scanner runs entirely within your GitHub Actions runner or local Docker environment. Your source code and prompts never leave your infrastructure.

---

## 🏢 Enterprise & Private Repositories

The free Community Mode is designed for public, open-source repositories. 

For **private repositories** or enterprise deployments requiring auditor-ready compliance reports, an Enterprise License Key is required. 
Enterprise capabilities include:

🏢 Air-Gapped Docker Appliance: Run deep semantic scans locally. Zero data leaves your VPC.

📄 Auditor-Ready Reports: Generate _FINAL.pdf and _audit_matrix.md mapped directly to ISO 27001 & 42001.

🔗 GRC Automation Add-on: Automatically push structured, HMAC-SHA256 signed JSON evidence directly to Vanta, Drata, Jira, or custom SIEMs.

👉 View [Public Webhook Schema & Security Docs](https://github.com/hama-tech/hama-tech-neural-sentinel-action/blob/main/WEBHOOK_SCHEMA.md)

📩 **Contact:** `engineering@neuralsentinel.online` to request an enterprise license or schedule a technical demo.

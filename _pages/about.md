---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>

Hello, I am **Jiahao (Alex) Jiang**, a final-year undergraduate at **Xi'an Jiaotong-Liverpool University (XJTLU)** majoring in **Information Management & Information Systems** (GPA 3.95/4.0, WES), currently an **AI Engineer Intern at Amazon**.

I work at the intersection of **AI agents and real-world systems**, on both sides of the fence:

- **Research** — I study how AI agents interact with the environments humans built: how web accessibility failures break autonomous agents (targeting CHI/ASSETS 2027), and how humans and chatbots jointly construct distorted self-narratives in AI-assisted reflection (SURF 2026, targeting CHI 2027 LBW).
- **Engineering** — At Amazon I build AI-native data infrastructure: GenAI copilots, MCP tooling that grounds LLM-generated SQL in mined organizational knowledge, and modern data-warehouse foundations.

I am actively looking for **graduate research opportunities (2027 Fall)** in HCI, AI agents, and human-AI interaction.

[![GitHub](https://img.shields.io/badge/GitHub-View_Profile-blue?logo=github)](https://github.com/Alex-jjh)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/jiahao-jiang04)

# News
- *2026.07*: &nbsp;🔬 SURF 2026 project on **cognitive co-deception in AI-assisted reflection** enters formative-study phase (supervised by Dr. Brennan Jones, XJTLU).
- *2026.04*: &nbsp;📊 Completed large-scale data collection (~14.7K agent trajectories) for the **AI Agent × Web Accessibility** study.
- *2026.04*: &nbsp;🔬 Started research on **AI agents and web accessibility** as principal investigator, targeting CHI/ASSETS 2027.
- *2025.11*: &nbsp;🚀 Joined **Amazon** as an **AI Engineer Intern** (Global Logistics, Shanghai).
- *2025.09*: &nbsp;💼 Joined **IQVIA** as a **Technology Consulting Intern** (AI, Digital & Tech Solutions).
- *2025.05*: &nbsp;🏆 **Meritorious Winner (Top 10%)**, Mathematical Contest in Modeling (MCM/ICM).
- *2025.03*: &nbsp;💼 Joined **SAP Labs China** as a **Project Management Intern** (Strategy & Operations).

# Research

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">CHI/ASSETS 2027</div><img src='images/a11y_research.svg' alt="Same Barrier hypothesis: accessibility degradation affects both AI agents and screen readers" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[When the Web Breaks for Agents: Accessibility and AI Agent Task Success](https://github.com/Alex-jjh/ai-agent-accessibility)

**Jiahao Jiang** (Principal Investigator), co-advised by Dr. Brennan Jones (XJTLU)
*Empirical study · N = 14,768 controlled agent trajectories · Apr 2026 – Present*

- Tests the **"Same Barrier" hypothesis**: AI agents and screen-reader users face structurally equivalent barriers, because both depend on the browser Accessibility Tree.
- Designed the **Accessibility Manipulation Taxonomy (AMT)**: 26 WCAG-grounded DOM operators that degrade accessibility in controlled ways, with a dual 12-dim DOM × 3-architecture behavioral-signature method to attribute failures to the semantic, visual, or functional layer.
- Headline finding: degrading accessibility drops text-only agent success from **93.8% → 38.5%** (p < 10⁻⁶); the effect replicates across closed-source (Claude Sonnet) and open-source (Llama 4) models.
- Discovered three novel phenomena: **Landmark Paradox**, **Shadow DOM Ghost Buttons**, and **Forced Simplification**. All 28 headline statistics reproducible from raw data via a one-command verification pipeline.
- Full TypeScript + Python platform on AWS (EC2, Bedrock) with a custom computer-use agent; pre-registered 48-task set filtered from 684 candidates via a 7-gate pipeline.
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">CHI 2027 LBW</div><img src='images/codeception_research.svg' alt="Cognitive co-deception: user and AI jointly reinforce a distorted self-narrative" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Cognitive Co-Deception in Proactive AI-Assisted Reflection](https://github.com/Alex-jjh/surf-work-reflection-research)

**Jiahao Jiang**, supervised by Dr. Brennan Jones (XJTLU)
*SURF 2026 (Summer Undergraduate Research Fellowship) · Jun 2026 – Present*

- Studies a bilateral failure mode of everyday chatbot reflection: the user and the AI, **neither holding ground truth**, jointly construct and reinforce a comfortable but distorted self-narrative — beyond one-way sycophancy.
- Phase A formative study validates four observable risk markers: entry posture, certainty phrasing, regeneration ("narrative shopping") patterns, and framing acceptance.
- Built the bilingual (zh/en) session instrument: a Streamlit chat platform over Bedrock with Latin-square conditions, embedded probes, full regeneration logging, and a privacy-first data pipeline (de-identification gates enforced by pre-commit checks).
- Phase B: sidebar-coach MVP + two-condition study (chatbot vs. chatbot + coach), feeding a CHI 2027 Late-Breaking Work submission and a full paper at DIS/CSCW/CHI 2028.
</div>
</div>

# Industry Experience

- *2025.11 – Present*, **Amazon — Global Logistics**, Shanghai, China. **AI Engineer Intern**.
  - **Top-down — data warehouse rebuild (0 → 1 infra)**: Built the foundations of a next-generation data warehouse alongside a legacy one: everything-as-code ETL with code review and CI/CD (replacing UI-managed jobs), serverless compute, IaC-managed pipelines, and a clean dataset namespace with clear ownership — so data engineers ship a new table by writing SQL + a job definition and getting it reviewed, never touching a UI.
  - **Bottom-up — mining gold from legacy SQL**: Distilled ~4,000 production ETL queries into a **confidence-weighted knowledge graph** (931 tables / 28.9K columns / 1.6K metrics) capturing the tacit semantics that lived only in code and senior engineers' heads: trusted join keys, required filters, and metric definitions. Served to AI agents via an **MCP server (18 tools)**; a `validate_query` engine catches "runs-fine-but-silently-wrong" SQL — missing soft-delete filters, composite-key fan-out, conflicting metric definitions — and returns paste-ready fixes with workload evidence. Guarded by a 62-case offline eval suite run as a CI gate.
  - **GenAI Sales Copilot**: Co-led 0-to-1 development on a serverless, event-driven architecture (Lambda, SQS, Bedrock), combining multimodal RAG with a multi-agent layer routing intents to specialized handlers for secure Text-to-SQL with dynamic row-level security; authored the PRD through sales-user interviews.
  - **ML at scale**: Hybrid classification pipeline (heuristics + Gaussian Mixture Models) segmenting 1M+ unlabeled shipping records, with an automated MLOps backfill workflow.

- *2025.09 – 2025.11*, **IQVIA — AI, Digital & Technology Solutions**, Shanghai, China. **Technology Consulting Intern**.
  - Supported end-to-end implementation of the SmartSolve® Quality Management System; translated business requirements into technical specifications, flowcharts, test scripts, and training materials.

- *2025.03 – 2025.09*, **SAP Labs China — Strategy & Operations**, Shanghai, China. **Project Management Intern**.
  - Co-led Developer Experience initiatives for a 2,000+ developer community; managed end-to-end execution of 50+ technical workshops; automated administrative workflows with Power Automate.

- *2025.01 – 2025.03*, **Assembly (Stagwell)**, Shanghai, China. **Data Analyst Intern**.
  - Engineered Python pipelines over multi-source advertising APIs; built interactive Tableau dashboards informing 5+ client presentations.

# Selected Projects

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">Full-Stack 2026</div><img src='images/heritage_platform.svg' alt="Heritage Resource Platform Architecture" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Heritage Resource Platform — Community-Driven Cultural Heritage Sharing](https://github.com/Alex-jjh/heritage-resource-platform)

**Jiahao Jiang** (Solo Developer)
*Full-Stack Web Application*

- A community platform for discovering, sharing, and preserving cultural heritage resources — images, stories, traditions, and historical sites.
- **Stack:** Next.js + React 19 + TypeScript frontend; Spring Boot 3 + Java 21 + MySQL backend; JWT auth, role-based 4-tier permissions, structured review workflow.
- **Cloud & DevOps:** AWS (Cognito, S3, Lambda thumbnails, Amplify SSR), Terraform IaC, GitHub Actions CI/CD.
- Built with an AI-assisted, spec-driven development workflow (Kiro, Claude Code).
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">MCM 2025</div><img src='images/mcm_model.png' alt="MCM Model" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Data Insights into Medal Outcomes and Performance Drivers](https://github.com/Alex-jjh)

**Jiahao Jiang**, with teammates
*Mathematical Contest in Modeling (MCM) — Meritorious Winner (Top 10%)*

- Engineered three analytical models for Olympic performance: **Random Forest** (medal count prediction), **Logistic Regression** (medalist identification), and **Difference-in-Differences** (quantifying the "great coach" effect).
- Delivered data-driven resource-allocation strategies using Python and Tableau.
</div>
</div>

**Open-source & side projects**

- [agent-style](https://github.com/yzhao062/agent-style) — "The Elements of Agent Style": 21 writing rules that make AI agents write like tech pros. Published on [PyPI](https://pypi.org/project/agent-style/) & [npm](https://www.npmjs.com/package/agent-style) (contributor).
- [word-card-web](https://github.com/Alex-jjh/word-card-web) — GRE vocab in office micro-breaks: an always-on-top Picture-in-Picture flash-card widget with real-exam word-frequency scheduling.
- [aws-lightsail-proxy-sample](https://github.com/Alex-jjh/aws-lightsail-proxy-sample) — One-click IaC deployment (CloudFormation & Terraform) of a proxy stack on AWS Lightsail.

# Education
- *2023 – 2027 (Expected)*, **Xi'an Jiaotong-Liverpool University (XJTLU)**.
  - B.Sc. Information Management & Information Systems. **GPA: 3.95/4.0 (WES)**. University Academic Excellence Award.
- *Summer 2024*, **Duke Kunshan University (DKU)** — Machine Learning (Grade: A).
- *Summer 2024*, **Nanyang Technological University (NTU)** — Cybersecurity (Grade: A+).
- *Spring 2024*, **UCLA Extension** — Introduction to Data Science (Grade: A).
- *Summer 2024*, **EM-Normandie Business School** — Project Management (Grade: A).

# Certifications & Skills
- **AWS Certifications:** Solutions Architect – Associate (SAA-C03) · AI Practitioner (AIF-C01).
- **Languages & Frameworks:** Python (Pandas, NumPy, Scikit-learn), SQL, Java, TypeScript, Git, CI/CD.
- **AI & Cloud:** AWS (Lambda, Bedrock, Redshift, EC2, S3), RAG, GenAI agents, MCP, MLOps, IaC (Terraform, CDK).
- **BI & Tools:** Tableau, Power BI, Amazon QuickSight, JIRA, Power Automate.
- **English:** IELTS 7.5 · TOEFL 6.0/6.0 (new format).

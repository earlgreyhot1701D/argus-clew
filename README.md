# Argus Clew

**Agent Readiness Prompts for AWS**

---

## Why Argus?

In Greek mythology, Argus Panoptes was the hundred-eyed giant who never slept. He was the ultimate watchman, seeing everything at once.

Argus Clew carries that idea into software. It watches your codebase for structural issues that humans overlook but machines can't ignore. "Clew" is the thread that guides you through the problem, part of a growing suite of developer tools (Hermes Clew, Argus Clew, and others) that help developers see what they can't easily see themselves.

Hermes Clew scans. Argus Clew watches.

## The Problem

Many web applications look acceptable to humans while remaining structurally difficult for AI agents, automation systems, retrieval workflows, and other machine driven consumers to interpret.

Agents hit unlabeled inputs, styled divs instead of buttons, generic link text, missing metadata, and content hidden behind client side rendering. They fail silently. The developer never finds out because the app looks fine to a human.

## The Solution

Argus Clew is a family of three production-ready prompts that bring agent readiness to AWS development workflows. Each prompt is copy-paste ready for use with any AI assistant (Kiro, Q Developer CLI, Claude, Amazon Bedrock, or similar).

Scanning methodology inspired by the Hermes Clew Agent Readiness Framework:
https://github.com/earlgreyhot1701D/hermes-clew

### The Three Prompts

| Prompt | What It Does | AWS Services |
|--------|-------------|--------------|
| **Argus Clew** | Deterministic scanning pipeline. Scans every commit, produces a readiness score, stores history, sends notifications, gates deployments. | CodePipeline, CodeBuild, DynamoDB, S3, SNS, SSM, CloudWatch, IAM |
| **Argus Clew Deploy** | Agent-friendly deployment. Deploys your app to S3/CloudFront with metadata preservation, safe WAF defaults, and optional experimental machine readable conventions. | S3, CloudFront, WAF, CloudWatch, Route 53, IAM, ACM |
| **Argus Clew Audit** | One-time structural review. No infrastructure required by default. Preflight assessment before deploying to AWS or adopting the full pipeline. | Optional S3 export, optional CloudWatch metrics, optional CodeBuild wrapper |

They form a natural progression: **Audit** to understand the current state, **Clew** to guard against regressions on every commit, **Deploy** to ship with machine readability preserved.

## Scoring Model

All three prompts use a deterministic weighted rubric totaling 100 points.

| Category | Weight | What It Evaluates |
|----------|--------|------------------|
| Semantic structure | 20 | Landmarks, tag appropriateness, document structure |
| Metadata and machine readable context | 15 | Title, description, Open Graph, meta tags |
| Navigation discoverability | 15 | Link clarity, navigation structure, route visibility |
| Form clarity and input labeling | 15 | Label association, input types, submit mechanisms |
| Structured data and content cues | 10 | Schema.org, JSON-LD, microdata |
| Interaction clarity | 10 | Button labels, click handler patterns, interactive elements |
| Consistency and hierarchy | 10 | Heading order, structural regularity |
| Risk deductions for critical blockers | 5 | Severe issues that fundamentally break machine interpretation |

The score is a deterministic comparative signal, not a formal accessibility certification or universal quality metric.

## How to Use

### Quick Start (Argus Clew Audit)

Copy the contents of `prompts/argus-clew-audit.md` and paste it into your AI assistant. Provide your project details when prompted. You'll get a scored report with prioritized findings and remediation guidance. No AWS infrastructure required.

### Full Pipeline (Argus Clew)

Copy the contents of `prompts/argus-clew.md` and paste it into your AI assistant. Provide your repository and AWS configuration details. The prompt generates a complete scanning pipeline with CodePipeline, CodeBuild, DynamoDB history, SNS notifications, and deployment gating.

### Agent-Friendly Deployment (Argus Clew Deploy)

Copy the contents of `prompts/argus-clew-deploy.md` and paste it into your AI assistant. Provide your project and deployment details. The prompt generates S3/CloudFront infrastructure with metadata preservation, safe WAF defaults, and optional experimental conventions.

## Project Structure

```
argus-clew/
├── LICENSE                              # CC0 1.0 Universal (public domain)
├── README.md                            # This file
├── prompts/
│   ├── argus-clew.md                    # Submission 1: Deterministic scanning pipeline
│   ├── argus-clew-deploy.md             # Submission 2: Agent-friendly deployment
│   └── argus-clew-audit.md              # Submission 3: One-time structural audit
└── docs/
    └── design-decisions.md              # Architecture context and rationale
```

## Key Principles

These principles hold across all three prompts:

**Read-only.** The scanner never modifies source code. Never changes dependencies. Never auto-fixes. The developer decides what to fix.

**Deterministic.** The same inputs and configuration produce the same score every time. No LLM is used for scoring.

**Conservative in claims.** The score is a comparative tool for structural readiness, not a universal truth engine. It does not replace runtime accessibility testing, end-to-end testing, or live agent evaluation.

**AWS Well-Architected aligned.** Every prompt maps to the five pillars: security, operational excellence, reliability, performance efficiency, and cost optimization.

**Honest about limitations.** Framework patterns may require calibration. JavaScript heavy applications may hide structure not visible in source alone. Source-based scanning is useful but not equivalent to rendered DOM analysis.

## AWS Well-Architected Framework Alignment

### Security
- Read-only scan behavior
- Least privilege IAM
- Encrypted storage
- No trust placed in spoofable client identities

### Operational Excellence
- Repeatable pipeline behavior
- Documented thresholds
- Clear operator feedback
- Stored comparison history

### Reliability
- Durable report storage
- Repeatable scan execution
- Alerting for failures
- Clear baseline handling

### Performance Efficiency
- Deterministic static analysis for fast feedback
- Targeted metrics and reports
- Optional calibration for framework specific patterns

### Cost Optimization
- Designed for low cost operation on small to medium teams
- No idle compute resources
- On-demand billing where applicable
- Optional extensions add cost only when enabled

## Built For

AWS Prompt the Planet Challenge (2026) on DoraHacks.

## License

CC0 1.0 Universal (public domain). You can copy, modify, distribute, and use these prompts for any purpose without permission.

---

*This project was created with AI assistance and human review. Final direction, selection, and submission decisions were made by the author.*

*Argus Clew — Awareness, not judgment.*

# Awesome-Workflow-Automation-Engine

# Top Workflow Automation Engine Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on BPMN Process Engines, Durable Execution & Self-Hosted Orchestration*  
**Last updated: October 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Workflow Automation Engines**. These tools provide the foundational runtime for executing business processes—orchestrating tasks, managing state, handling retries, and coordinating human and system interactions—whether as visual low-code platforms or code-first durable execution engines.

**Examples** include Atlassian Workflow Engine, Zapier, Make, Workato, Tray.io, n8n, Kissflow, Nintex, Camunda, and ServiceNow Flow Designer (the category leaders).

**Open-source emphasis**: Workflow Automation Engines is a domain where open-source tooling is **exceptionally mature but bifurcated into two distinct architectures**. **BPMN-based engines** like **Camunda (Zeebe)** and **Flowable** provide standards-compliant process orchestration with visual modeling, human task management, and enterprise-grade state machines—Camunda's Zeebe powers Camunda Platform 8 with horizontal scaling and no relational database requirement , while Flowable offers a compact, Spring-integrated BPMN 2 engine under Apache 2.0 . **Durable execution engines** like **Temporal** (and its derivatives) take a code-first approach, guaranteeing workflow replay and state persistence across failures without BPMN constraints. **Windmill** bridges both worlds—a fast, open-source workflow engine and developer platform supporting TypeScript, Python, and Go with flows, scripts, and UIs . For visual event-driven automation, **Node-RED** provides low-code flow-based programming for IoT and API integration . For data pipeline orchestration, **Apache Airflow** remains the standard for programmatic DAG scheduling . The critical gap: **no open-source engine replicates the turnkey, no-code SaaS experience** of Zapier or Make—open-source engines require engineering expertise to deploy, model, and maintain.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Atlassian Workflow Engine](https://www.atlassian.com/)**  
  Jira's native workflow engine with configurable statuses, transitions, conditions, validators, and post-functions; supports visual workflow editing and automation rules.

- **[Zapier](https://zapier.com/)**  
  Market-leading no-code automation platform with 9,000+ app integrations; trigger-and-action workflows for connecting SaaS tools without engineering effort.

- **[Make](https://www.make.com/)**  
  Visual automation platform with 3,000+ pre-built apps; Scenario Builder with If-Else, Merge, and iterators for complex data transformation.

- **[Workato](https://www.workato.com/)**  
  Enterprise automation platform with AI-powered recipe building, low-code connectors, and comprehensive security compliance (PCI-DSS, ISO 27001, SOC 2, HIPAA).

- **[Tray.io](https://tray.ai/)**  
  Low-code automation platform with powerful data transformation, workspaces, and hundreds of pre-built connectors plus custom connector builder.

- **[n8n](https://n8n.io/)**  
  Source-available automation platform with visual canvas and custom code; 1500+ integrations and AI-native capabilities (see open-source section for self-hosted details).

- **[Kissflow](https://kissflow.com/)**  
  Low-code workflow and process automation platform for business users; includes form builder, process designer, and approval workflows.

- **[Nintex](https://www.nintex.com/)**  
  Enterprise workflow automation with visual designer, forms, and document generation; strong for SharePoint and Microsoft 365 environments.

- **[Camunda](https://camunda.com/)**  
  BPMN-based process orchestration platform; Camunda 8 (powered by Zeebe) provides high-throughput, horizontally scalable workflow execution with visual modeling (see open-source section for Zeebe details).

- **[ServiceNow Flow Designer](https://www.servicenow.com/)**  
  Native workflow automation within ServiceNow; visual flow builder with actions, triggers, and integrations across the Now Platform.

## Open-Source GitHub Projects

### BPMN-Based Process Engines

- **[Camunda Zeebe](https://github.com/camunda/camunda)**  
  The workflow engine powering Camunda Platform 8 (Zeebe Community License 1.1, with Java/Go clients under Apache 2.0)  . Defines processes visually in **BPMN 2.0**, deploys with Docker/Kubernetes, reacts to Kafka and message queues, and **scales horizontally to very high throughput** with **no relational database required** (fault tolerance via replication) . Exports process data for monitoring and analysis. **The strongest open-source BPMN engine for high-throughput microservices orchestration**—but the core engine uses a source-available license, not OSI-approved.

- **[Flowable](https://github.com/flowable/flowable-engine)**  
  Compact, high-efficiency **BPMN 2 process engine** written in Java (Apache 2.0)  . Runs embedded in any Java application, on a server, cluster, or cloud; integrates perfectly with Spring; provides rich Java and REST APIs for orchestrating human or system activities. **The most permissively licensed BPMN engine** for teams wanting Apache 2.0 without source-available restrictions—best for Java/Spring ecosystems.

- **[Activiti](https://github.com/Activiti/Activiti)**  
  Lightweight BPMN 2 process engine for Java (Apache 2.0)  . Super-fast and rock-solid core; runs in any Java application, server, cluster, or cloud; integrates with Spring. **A mature, permissive alternative to Flowable** (Activiti and Flowable share lineage)—best for teams wanting a simpler BPMN engine without Flowable's additional modules.

- **[Elsa Workflows](https://github.com/elsa-workflows/elsa-core)**  
  Open-source workflow engine for **.NET** (MIT); visual designer (Elsa Studio) with BPMN-like modeling, long-running workflows with bookmarks and triggers, versioned definitions, and Docker deployment  . Supports HTTP triggers, timers, and message-based workflows. **The strongest open-source workflow engine for .NET teams**—but smaller ecosystem than Java-based alternatives.

### Durable Execution Engines (Code-First)

- **[Temporal](https://github.com/temporalio/temporal)**  
  Open-source **durable execution platform** (MIT) for reliable, long-running workflows; workflows are code (Go, Java, TypeScript, Python, .NET, PHP, Ruby) with automatic state persistence, replay, and retry—no BPMN modeling required . Separates **workflow logic** (deterministic orchestration) from **activities** (non-deterministic external calls)  . Handles distributed transactions (saga pattern), entity workflows (shopping cart, account lifecycle), fan-out/fan-in, and human-in-the-loop approvals with timeouts . **The standard for code-first durable orchestration** when you need replayable state and clear execution timelines without visual modeling.

- **[Windmill](https://github.com/windmill-labs/windmill)**  
  Fast, open-source **workflow engine and developer platform** (AGPL-3.0) for building endpoints, workflows, and UIs in TypeScript, Python, Go, and more  . Features built-in IDE, **flows with branches/loops/approvals/retries**, scripts, low-code and full-code apps, data pipelines (alpha), and **Workflow-as-Code** (express a workflow as a single script) . Self-host via Helm or Docker Compose; cloud option with 1,000 monthly executions free. **The strongest open-source bridge between code-first and visual workflow**—for teams wanting developer flexibility with a UI.

### Visual / Event-Driven Automation

- **[Node-RED](https://github.com/node-red/node-red)**  
  Open-source **flow-based programming tool** for event-driven applications (Apache 2.0)  . Browser-based drag-and-drop editor for wiring together hardware devices, APIs, and online services; supports HTTP, WebSocket, MQTT, database connections, and custom JavaScript function nodes. **The standard for IoT and integration-heavy event-driven automation**—lighter than BPMN engines but not designed for complex human task orchestration.

- **[Apache Airflow](https://github.com/apache/airflow)**  
  Open-source platform to **programmatically author, schedule, and monitor workflows** (Apache 2.0)  . Workflows defined as code (Python DAGs) become maintainable, versionable, testable, and collaborative; scheduler executes tasks on workers following dependencies; rich UI for visualization and troubleshooting. **The standard for data pipeline orchestration**—not a BPMN or human-workflow engine, but essential for batch/data-driven automation.

### Additional Strong Open-Source Options

- **Imixs-Workflow** — Human-centric BPMN 2.0 workflow engine (Java, 418 GitHub stars); focused on business process management with human tasks  .
- **Goflow** — Simple but powerful DAG scheduler and dashboard in Go (483 GitHub stars)  .
- **Cordum** — Governance-first control plane for AI agents and external workers (Go, 511 GitHub stars); policy-before-dispatch, approval gates, audit trails  .

**Frameworks for building custom systems**: For **BPMN with high throughput and no database**, Camunda Zeebe . For **permissive Apache 2.0 BPMN in Java/Spring**, Flowable or Activiti . For **.NET workflows**, Elsa . For **code-first durable execution with replay**, Temporal . For **developer-friendly workflows with a UI in multiple languages**, Windmill . For **event-driven IoT/API automation**, Node-RED . For **data pipeline DAGs**, Airflow . No open-source engine matches the no-code SaaS simplicity of Zapier or Make—expect to invest in engineering, infrastructure, and ongoing maintenance.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Workflow automation engines handling business processes and credentials must comply with applicable security policies and data governance requirements; workflow state may contain sensitive business data requiring encryption and access controls.
- **Open-source workflow engines are mature but require engineering investment**—Camunda Zeebe and Flowable provide production-grade BPMN orchestration , Temporal provides durable code-first execution , and Windmill bridges developer flexibility with visual flows . However, **no open-source engine replicates the turnkey, no-code experience** of Zapier or Make; deployment, modeling, and maintenance are your responsibility. Choose based on architectural fit (BPMN vs. code-first vs. event-driven) and team skills.
- Verify license terms for commercial use; Camunda Zeebe uses the Zeebe Community License 1.1 (source-available, not OSI-approved) with Apache 2.0 clients , Flowable and Activiti use Apache 2.0 , Temporal uses MIT , Windmill uses AGPL-3.0 , and Node-RED/Airflow use Apache 2.0 .

---

**Made for platform engineers, integration architects, BPM practitioners, and workflow automation developers.**  
Let's make workflow automation more open, but with clear eyes about the engineering investment and architectural trade-offs that define each engine.

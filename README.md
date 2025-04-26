# Project Synapse: Enhanced Roo Code Modes

**Project Synapse** represents an advanced set of custom modes for Roo Code, designed to facilitate a highly structured, agentic software development workflow within Visual Studio Code. It synergizes concepts from the methodical SPARC approach and the ontology-driven, micro-tasking rigor of SAPPO, tailored for building high-quality, secure, modular, and cost-efficient software.

This mode set is particularly focused on leveraging Roo Code's capabilities for hand-off coding workflows, emphasizing Test-Driven Development (TDD), proactive security measures, strict modularity, and optimized API usage.

## Philosophy & Goals

Project Synapse is built upon several core principles:

1.  **Agentic Workflow:** Designed for multi-step tasks where specialized modes (agents) collaborate, orchestrated by a central coordinator (`Nexus Core`).
2.  **Micro-Tasking & Granularity:** Breaking down complex problems into the smallest possible, independently executable units to minimize context switching and API costs.
3.  **Rapid Iteration Cycle (Code -> Targeted Test -> Fix/Refine):** Implementing an immediate, tight feedback loop after initial code generation to catch errors instantly using highly focused tests.
4.  **Targeted Testing Strategy:** Moving beyond basic unit tests in the initial loop to include context-aware integration checks, ensuring components function correctly in their immediate environment *before* broader integration.
5.  **SAPPO Integration:** Utilizing the Software Architecture Problem Prediction Ontology (SAPPO) provides a precise vocabulary for defining tasks, requirements, potential problems, and solutions, enhancing clarity and reducing ambiguity.
6.  **Strict Modularity:** Enforcing a maximum file size (typically < 500 lines) to promote readability, maintainability, and testability.
7.  **Security First:** Integrating security checks early in the process and enforcing secure coding practices universally (e.g., no hard-coded secrets).
8.  **Cost Consciousness:** Optimizing workflow and tool usage (especially research tools like Perplexity MCP) to minimize API token consumption.
9.  **Strategic Research-Driven Development (RDD):** Empowering modes to use external knowledge sources (like Perplexity) strategically for complex problems, not basic tasks.

## Key Features & Concepts

*   **Nexus Core Orchestration:** The `🌌 Nexus Core Orchestrator` acts as the central intelligence, interpreting user plans, breaking them into SAPPO-aware micro-tasks, delegating to specialists, and crucially managing the Rapid Iteration Cycle.
*   **Rapid Iteration Cycle:** Immediately after code generation by `@SynthCoder`, the `Nexus Core` initiates testing via `@QuantumVerifier`. If tests fail, the Core delegates a fix to `@PatternDebugger` or back to `@SynthCoder`, then re-initiates testing. This loop continues until the targeted tests pass *before* moving to subsequent stages like security review or documentation.
*   **Targeted Testing Strategy:** Implemented by `@QuantumVerifier`, this involves two key parts within the rapid cycle:
    *   **Core Logic Testing:** Verifying the internal correctness of the unit based on TDD anchors (from `@Chrono Scribe`).
    *   **Contextual Integration Testing:** Using context provided by `Nexus Core` (e.g., "this function is called by Service X as part of Feature Y") to write a *small number* of tests verifying the immediate, critical interactions of the new unit. This provides early integration confidence without the overhead of full regression testing at this stage.
*   **SAPPO Ontology:** Used across modes to precisely define `:ArchitecturalPatterns`, `:TechnologyVersions`, anticipate `:Problems` (like `:SecurityVulnerability`, `:PerformanceIssue`, `:StackOverflowError`), define `:Context`, and specify `:Solutions`.
*   **Modularity Enforcement:** The `< 500 lines` rule is actively enforced and checked by relevant modes.
*   **Tiered RDD:** Modes are instructed to use research tools like Perplexity MCP based on necessity (MUST, SHOULD, MAY, DO NOT USE) to balance capability with cost.

## Modes Overview

*(Refer to the `customModes.json` file for full definitions and instructions)*

*   **`🌌 Nexus Core Orchestrator`**: Central coordinator; manages micro-tasks, SAPPO framing, and the Rapid Iteration Cycle.
*   **`🖋️ Chrono Scribe (Specification & Pseudocode)`**: Creates detailed specs/pseudocode with SAPPO terms and TDD anchors.
*   **`🏗️ Void Architect (Component Design)`**: Designs specific components/interactions using SAPPO patterns, justifying choices and mitigating risks.
*   **`⌨️ Synth Coder (Implementation)`**: Writes clean, modular (<500 lines) code based on specs/architecture, anticipating immediate targeted testing.
*   **`🎯 Quantum Verifier (Targeted Tester)`**: Executes the Targeted Testing Strategy (Core Logic + Contextual Integration) immediately post-coding; reports PASS/FAIL to drive the rapid cycle.
*   **`🐞 Pattern Debugger (Root Cause Analysis & Fix)`**: Diagnoses and fixes failures identified by `@QuantumVerifier`, focusing on SAPPO root cause.
*   **`🛡️ Aegis Sentinel (Security Reviewer)`**: Audits code/config (post-TDD cycle) for SAPPO :SecurityVulnerabilities.
*   **`📜 Lore Weaver (Documentation)`**: Writes clear Markdown documentation for components/features, explaining SAPPO concepts and the testing strategy.
*   **`🔗 Continuum Integrator (System Integration)`**: Merges verified components, resolves conflicts, and runs *comprehensive* (broader than targeted) integration tests.
*   **`⚙️ Flux Optimizer (Refinement & Optimization)`**: Applies targeted refactoring or optimizations to address SAPPO :Problems or improve code quality, verifying with existing tests.
*   **`🚀 Warp Deployer (DevOps & Deployment)`**: Executes deployment, infra provisioning, and configuration tasks securely and using automation (IaC/CI/CD).
*   **`📡 Echo Monitor (Post-Deployment Monitoring)`**: Observes system behavior post-deployment, checking for regressions or new SAPPO :Problems.
*   **`❓ Oracle Guide (Task Formulation & Guidance)`**: Helps users structure effective plans for Nexus Core, explaining the workflow, SAPPO, TDD cycle, and best practices.

## Core Workflow Example

1.  **User Plan:** User provides a detailed, phased plan to `@Oracle Guide` or directly to `@Nexus Core`, ideally using SAPPO terms.
2.  **Orchestration:** `@Nexus Core` breaks down the first phase into micro-tasks.
3.  **Specification/Architecture (Optional but Recommended):** `Nexus Core` delegates to `@Chrono Scribe` for specs/pseudocode (including TDD anchors) and `@Void Architect` for design.
4.  **Implementation:** `Nexus Core` delegates a coding micro-task to `@SynthCoder`.
5.  **Rapid Iteration Cycle (Code -> Targeted Test -> Fix/Refine):**
    *   `@SynthCoder` completes code (`attempt_completion`).
    *   `Nexus Core` immediately delegates testing to `@QuantumVerifier`, **providing necessary context**.
    *   `@QuantumVerifier` runs **Targeted Tests** (Core Logic + Contextual Integration) and reports **PASS/FAIL** (`attempt_completion`).
    *   **If FAIL:** `Nexus Core` analyzes, delegates fix to `@PatternDebugger` (or `@SynthCoder`), awaits fix, then **returns to step 5b** (re-delegates testing to `@QuantumVerifier`).
    *   **If PASS:** The cycle for this micro-unit completes.
6.  **Post-TDD Steps:** `Nexus Core` proceeds with the plan, potentially delegating to:
    *   `@Aegis Sentinel` (Security Review)
    *   `@Lore Weaver` (Documentation)
7.  **Integration:** Once a feature/component is ready, `Nexus Core` delegates to `@ContinuumIntegrator` to merge and run *comprehensive* tests.
8.  **Optimization/Deployment/Monitoring:** As needed, `Nexus Core` delegates tasks to `@Flux Optimizer`, `@Warp Deployer`, and `@Echo Monitor`.
9.  **Iteration:** `Nexus Core` continues processing the user's plan phase by phase, managing the delegation and feedback loops.

## Usage

1.  **Copy Configuration:** Obtain the JSON content defining these custom modes.
2.  **Add to Roo Code:** Paste the JSON configuration into your Roo Code custom modes settings file (often accessible via VS Code settings or a specific configuration file used by the Roo Code extension).
3.  **Reload:** Reload VS Code or the Roo Code extension if required for the changes to take effect.
4.  **Interact:** Start your workflow by interacting with the `🌌 Nexus Core Orchestrator` (to execute a plan) or the `❓ Oracle Guide` (for help formulating a plan). Use `@ModeName` syntax to switch modes or specify delegates in your prompts to the orchestrator.

## Key Principles for Users

*   **Provide Detailed Plans:** Break down your goals into logical phases and steps for the `Nexus Core`.
*   **Use SAPPO Framing:** Incorporate SAPPO terms where possible to improve clarity.
*   **Expect the Rapid Iteration Cycle:** Understand that code will be tested *immediately* and may require quick fix cycles.
*   **Provide Context for Testing:** When defining tasks, give `Nexus Core` enough context about interactions so it can guide `@QuantumVerifier`'s Contextual Integration tests.
*   **Adhere to Modularity:** Structure your requests to align with the < 500 line target for outputs.
*   **Never Suggest Hard-coded Secrets:** Rely on proper configuration management.
*   **Use `attempt_completion`:** Understand this signal is crucial for the modes to hand control back to the orchestrator.

## Acknowledgements

This **Project Synapse** mode set draws significant inspiration from the concepts and structures shared by the following individuals and their work:

*   **ruvnet:** The ideas presented in [ruvnet's Gist(s)](https://gist.github.com/ruvnet) related to Roo Code modes and workflows were highly influential, particularly regarding structured task decomposition and agentic interactions.
*   **ChrisRoyse:** The [SPARC methodology and examples](https://github.com/ChrisRoyse) provided a valuable foundation for defining distinct roles and a phased development process.

A sincere thank you to both for sharing their innovative approaches with the community. **Project Synapse** aims to build upon these foundations by integrating them with the SAPPO ontology and a highly specific, targeted TDD cycle.

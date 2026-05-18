# Graphify Master Plan & Execution Guide
### For Local Systems, Users, and Agentic Coding Assistants

This document serves as the master blueprint and step-by-step playbook for building, compiling, labeling, serving, and verifying **Graphify Codebase Knowledge Graphs** (`graphify-out`) for any folder or repository on this system.

---

## 📖 What is Graphify?
**Graphify** is a state-of-the-art codebase architecture compiler. It parses any local folder containing code, documentation, papers, images, or media, and synthesizes it into three high-performance outputs:
1. `graph.json` — A GraphRAG-ready node-link network dataset.
2. `graph.html` — A fully-interactive, animated, searchable visual graph powered by **Vis.js** (complete with physics-based floating layouts, community clustering, and detailed inspect panels).
3. `GRAPH_REPORT.md` — A structured, plain-language markdown audit detailing modular architectural divisions ("Communities"), central high-connectivity variables ("God Nodes"), and automatic domain-relevant Q&A prompts.

---

## 🛠️ Step-by-Step Execution Guide

Follow these sequential blocks to compile and operate Graphify on any folder:

### Block 1: Environment Verification
Before running Graphify, locate the executable on the host system:
- **Windows (PowerShell)**:
  ```powershell
  Get-Command graphify
  ```
- **Platform Paths**: Graphify installs globally at `C:\Users\<User>\AppData\Local\Programs\...` or is accessible as a global `graphify` application in standard terminal shells.
- **Python / UV Fallback**: If the global executable is unavailable, it can be run via:
  ```powershell
  uv tool run graphifyy <command>
  # OR
  python -m graphify <command>
  ```

---

### Block 2: Initial Graph Compilation (AST & Structure)
To perform a lightning-fast, zero-cost structural extraction of any codebase (parsing imports, call flows, markdown structures, and file hierarchies without calling external LLM APIs):
1. Navigate to the target project directory.
2. Run the update command:
   ```powershell
   graphify update .
   ```
3. **What happens**: Graphify instantly creates a `graphify-out` directory containing:
   - `graphify-out/graph.json`
   - `graphify-out/graph.html`
   - `graphify-out/GRAPH_REPORT.md`
   - `graphify-out/manifest.json`

---

### Block 3: AI-Powered Semantic Extraction (Optional)
To enrich the structural graph with deep semantic understanding (such as design patterns, conceptual dependencies, image/chart layout diagrams, and mathematical paper formulas):
1. Set your Gemini API credentials in the environment:
   ```powershell
   $env:GEMINI_API_KEY="your_api_key_here"
   # OR
   $env:GOOGLE_API_KEY="your_api_key_here"
   ```
2. Run the semantic extractor:
   ```powershell
   graphify extract . --backend gemini --model gemini-3-flash
   ```
   *Note: For large folders, Graphify automatically partitions files into parallel chunks, caches previous runs to save tokens, and merges the AST and AI extraction into a unified graph.*

---

### Block 4: Modular Community Custom Labeling
Graphify runs advanced clustering algorithms to group related files and symbols into **Communities**. By default, these are named `Community 0`, `Community 1`, etc. To upgrade the graph to a premium state:
1. Open the generated `graphify-out/GRAPH_REPORT.md` and read the files/symbols listed under each community.
2. Formulate a highly descriptive 2-5 word name for each community (e.g., `Logistic Churn Classifiers` or `Tenure & CLV Regressors`).
3. Save these custom labels to a temporary dictionary file or execute the Python labeling script:
   ```python
   # Run in Python to update labels and regenerate the report
   import json
   from pathlib import Path
   from graphify.build import build_from_json
   from graphify.cluster import score_all
   from graphify.analyze import god_nodes, surprising_connections, suggest_questions
   from graphify.report import generate
   
   extraction = json.loads(Path('graphify-out/.graphify_extract.json').read_text())
   detection  = json.loads(Path('graphify-out/.graphify_detect.json').read_text())
   analysis   = json.loads(Path('graphify-out/.graphify_analysis.json').read_text())
   
   G = build_from_json(extraction)
   communities = {int(k): v for k, v in analysis['communities'].items()}
   cohesion = {int(k): v for k, v in analysis['cohesion'].items()}
   tokens = {'input': extraction.get('input_tokens', 0), 'output': extraction.get('output_tokens', 0)}
   
   # REPLACE WITH YOUR DESCRIPTIVE CUSTOM LABELS
   labels = {
       0: "Churn Classification Models",
       1: "Tenure & CLV Regression",
       2: "Evaluation & Leakage Diagnostics",
       # ... add other communities
   }
   
   questions = suggest_questions(G, communities, labels)
   report = generate(G, communities, cohesion, labels, analysis['gods'], analysis['surprises'], detection, tokens, '.', suggested_questions=questions)
   Path('graphify-out/GRAPH_REPORT.md').write_text(report)
   Path('graphify-out/.graphify_labels.json').write_text(json.dumps({str(k): v for k, v in labels.items()}))
   ```
4. **Result**: The report and interactive visualizer will now display these rich human-readable architectural titles.

---

### Block 5: Local Serving & Browser Verification
Due to browser local filesystem security constraints (CORS), opening a raw `.html` file directly from a local path can restrict interactive network features. Always serve the graph locally:
1. Spin up a lightweight Python HTTP server on port `8080` rooted in the output directory:
   ```powershell
   cmd /C "python -m http.server 8080 --directory graphify-out"
   ```
2. Open your web browser and navigate to:
   ```text
   http://localhost:8080/graph.html
   ```
3. **Interactive Verification Checklist**:
   - [ ] Wait 3-5 seconds for the physics layout solver to arrange floating clusters.
   - [ ] Search for a known "God Node" or key file using the visual search bar.
   - [ ] Toggle individual architectural communities to see sub-graphs isolate.
   - [ ] Expand the detailed inspect panel on the right by clicking any node.

---

### Block 6: Integrating Graphify into AI Agents
You can install Graphify rules, workflows, and skills directly into your AI coding assistant (like Google Antigravity, Claude Code, or Cursor) so they automatically consult the knowledge graph before answering codebase questions:
1. Run the developer install command in the project root:
   ```powershell
   graphify antigravity install
   ```
2. **What this writes**:
   - `.agents/rules/graphify.md` — Directs the agent to always read `graphify-out/GRAPH_REPORT.md` before making edits or answering questions.
   - `.agents/workflows/graphify.md` — Establishes standard CLI sub-workflows.
   - `C:\Users\<User>\.agents\skills\graphify\SKILL.md` — The global agentic skill file that coordinates multi-turn browser and CLI tools.

---

## 🧹 Server Cleanup
When you are done visualizing or testing, gracefully shut down the background http.server to free up local ports:
```powershell
# Terminate the http.server running on port 8080
Stop-Process -Id (Get-NetTCPConnection -LocalPort 8080).OwningProcess -Force
```

---

## 🌟 Case Study: Week 4 - Statistical ML: Linear Models
Here is exactly how Graphify was compiled, labeled, and verified for the Week 4 Churn & CLV workspace:

1. **Structural Compilation**:
   Run structural compilation to build the codebase link network:
   ```powershell
   graphify update .
   ```
   *Result*: Discovered 77 nodes, 70 edges, and 13 architectural communities mapping scripts, data split justifications, and models.

2. **Custom Architectural Community Labeling**:
   Created `graphify-out/.graphify_labels.json` to assign professional human-readable descriptions:
   ```json
   {
     "0": "Churn Classification Pipeline & Experiments",
     "1": "Environment & Automation Workspace",
     "2": "Tenure & CLV Regression Models",
     "3": "Evaluation Integrity & Leakage Diagnostics",
     "4": "Project Corpus & Datasets",
     "5": "Statistical ML Concepts & Workspace Guidelines",
     "6": "Problem Formulation & Data Profiling",
     "7": "Production Evaluation & Model Card Commitments"
   }
   ```
   Recompiled the labels into the vis.js visualizer and Markdown report:
   ```powershell
   graphify cluster-only .
   ```

3. **Visual Verification**:
   Started the local http.server:
   ```powershell
   cmd /C "python -m http.server 8080 --directory graphify-out"
   ```
   Opened `http://localhost:8080/graph.html` and verified:
   - Vis.js float stabilization is completed within 3-5 seconds.
   - Node search and neighbor node traversal operate seamlessly.
   - Customized labels map perfectly to their respective interactive sub-graphs.

---
*End of Plan. Use this file as a direct instruction set for any developer or autonomous coding assistant.*


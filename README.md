# Hi there 👋

<p align="center">
  <img alt="ScyLab" width="200" src="https://github.com/user-attachments/assets/677df6fb-3a89-4cdc-a679-e012f4adc0cd" />
</p>

I’m a Senior R&D Engineer with a PhD in Computational Mechanics from École des Mines de Paris 🎓. My core expertise lies in building high-performance, web-based software systems that bridge the gap between complex computational science and practical engineering workflows. Professionally, I focus on optimizing graphics rendering systems, automating highly parallel simulation pipelines, and crafting intuitive visual interfaces that make deep technology reliable in real-world environments.

Alongside my corporate R&D work, I architect independent developer tools and automation platforms that span the entire web and cloud stack 🚀. My software portfolio—including my browser-based data visualization engines (VU & VU-VERSE), serverless infrastructure platforms (AntiNode with its amAIra AI proxy), and automated media systems (ABR-INSIGHTS)—is driven by a passion for lean, stateless, and event-driven architectures.

Whether working with web rendering, serverless cloud setups, or automated AI pipelines, my goal remains the same 🛠️: to eliminate repetitive infrastructure friction, keep data secure, and build tools that make development faster and more intuitive.

---

## My Projects

### 🧊 Scenaven

**Visualization architecture**
Three layers, each with one job:
- ⚙️ **VTK on the server.** Reads `.vtk`, `.vtkhdf`, `.vtp`, and `.vtu`. Holds the loaded simulation, runs clip, warp, and extract, and prepares frames for playback.
- 📦 **OpenUSD as the handoff.** After conversion, and again after each filter, the server writes the scene the viewer loads: scene tree, field names and ranges, time steps, visibility, and the surfaces to draw.
- 🎨 **Three.js in the browser.** Orbit, pan, and zoom. Colormaps, legends, and opacity. Picking, probes, and extract tools. Time controls that ask the server for each frame.
**Data flow**
- VTK file → server converts and filters with VTK
- OpenUSD scene stored for the session
- Browser fetches surfaces and field values
- Three.js draws the mesh
Sign-in and the 3D view are separate. An auth shell hosts the viewer, so login and the GPU lifecycle stay independent. The shell never imports the WebGL engine. They talk across a versioned message protocol. 🧱
**Rendering**
- 🖼️ **WebGL** is the default. The viewport runs in a normal browser tab, with the existing material, colormap, and compose path.
- ⚡ **WebGPU** is opt-in when the deployment allows it. Unsupported browsers, or a failed init, stay on WebGL.
Client analytics run off the render thread. GPU-owning modules release their resources when a scene is torn down.
**Powered by Antinode**
- 🔐 **Secure login.** Identity, session, and entitlements are checked before cloud-bound work. The browser is not the trust root.
- 🤖 **Agentic flow.** amAIra sits beside the scene. It follows what you loaded, which row is selected, and which time step you are on, and can point you at a control or a Python snippet. Skills only run what the account and connection already allow.
- 🐍 **Python shell.** A server-side session for short VTK and NumPy snippets against the simulation already open in the view. The code runs next to the data, not in the tab.
**What you can do in the viewer**
- 👀 Orbit, pan, and zoom a full-screen 3D view
- 🎨 Color by a scalar field, with colormap, opacity, and legend
- ✂️ Clip, warp, or extract a region. Filters rebuild the surface on the server, then show up in the scene tree
- ⏱️ Play through time when the dataset has more than one step
- 💬 Ask amAIra about the scene, a field, or a filter
- 🐍 Run a short Python snippet on that same simulation
**Deploy modes**
Same viewer bundle. Same conversion pipeline. Storage, auth context, and which tools are on are what change.
- ☁️ **Cloud.** Hosted viewer, Antinode sign-in, storage per account. A cloud preview can start from curated examples. Uploads, filters, Python, and simulation skills turn on when cloud services are enabled for the connection.
- 🐳 **On-prem.** The same stack in Docker on your own network, with data on a local volume. Mesh API and the viewer UI run as containers you control.
Switch between them from **Infrastructure** in the viewer.

👉 https://www.scenaven.site

<img width="1398" height="864" alt="Screenshot 2026-10-06 at 05 23 03" src="https://github.com/user-attachments/assets/955d45af-ce59-4713-a88b-c436ee62da12" />



### 🧠 ANTINODE
Antinode: AI-First Backend-as-a-Service for Frontend Developers

Antinode is a managed, AI-first Backend-as-a-Service (BaaS) platform that enables frontend engineers, indie hackers, and product teams to ship production-ready full-stack applications without provisioning servers, managing databases, or maintaining complex backend infrastructure.

Simply integrate the lightweight Antinode SDK and remain entirely frontend-first.

* 🚀 The Flagship Feature: amAIra Native Embeds & Agentic Workflows
Real-time AI experiences shouldn't require a dedicated backend. Antinode brings amAIra directly into the gateway layer—a secure, proxy-native AI assistant framework now powered by Agentic Workflows. Configure commercial LLM providers or local Ollama deployments from your dashboard, keep your API keys securely on the gateway, and instantly embed an intelligent, streaming in-app copilot with a single script tag and zero custom streaming infrastructure.

  - 📚 Knowledge (Context Grounding): Supply Markdown playbooks directly to the model so responses are tightly anchored to your specific product documentation and business logic.
  - 🛠️ Skills (Declarative Actions): Enable visitors to trigger live API actions via /skill-id or natural language. 
  - 🔒 Zero-Proxy Privacy: Live agent actions run directly from the visitor’s browser using their active AntiNode session. AntiNode orchestrates chat and metadata without ever proxying or storing your private backend data.

* 🛡️ Production Infrastructure Included
While amAIra powers user-facing AI experiences, Antinode quietly provides the core services required by modern SaaS applications:
  - 🔒 Identity & IAM: Secure authentication and user session management powered by Google Sign-In under the hood. Your frontend never needs to deal directly with OAuth complexity.
  - 🔑 BYOK Secrets Vault: Store third-party credentials and private API keys securely using Google Cloud Secret Manager. Secrets are loaded only during serverless execution and are never exposed to client applications.
  - 💳 Billing & Stripe Subscriptions: Connect Stripe to provision subscription plans, launch hosted checkouts, process signed webhooks, and provide self-service customer billing portals with minimal configuration.

* 🛡️ Perimeter Protection by Design
Antinode is built around strict cryptographic multi-tenancy and edge-level financial circuit breaking. The gateway acts as an active billing shield, automatically detecting and dropping abusive traffic before requests reach your upstream AI providers, helping protect both service availability and usage-based costs.

> Replace backend complexity with frontend autonomy.


---

### 🌐 VU-VERSE
Unified Visualization Platform for VTK HDF Time-Series Datasets

VU-VERSE is a unified visualization platform for exploring VTK HDF time-series datasets using the Visualization Toolkit and its vtkHDF format.

The platform is built around cross-platform parity: the same UI layer, interaction model, and VTK rendering pipeline are shared across native and WebAssembly builds. This ensures consistent behavior, feature availability, and performance characteristics between desktop and web deployments, while preserving high-performance interactive visualization and time-series exploration.

* Project Links
  - [📺 YouTube Demo](https://www.youtube.com/watch?v=I-roFNQmASY)
  - [🚀 Release Notes (Desktop)](https://github.com/basavaakula/ScyLab-Tools/releases/tag/VU-VERSE)
  - [🌐 Web Viewer](https://basavaakula.github.io/vu-verse/viewer.html)
  - [📚 Documentation](https://basavaakula.github.io/vu-verse/docs_site/index.html)

<p align="center">
  <img alt="vu-verse" width="95%" src="assets/vu_verse_post.svg" />
</p>

---

### 📰 ABR-INSIGHTS
AI-Native Information Platform

ABR-INSIGHTS is an AI-native information platform that automatically analyzes and summarizes stories from trusted, publicly available news sources. It delivers concise insights across technology, science, AI, global news, and business, and ships extended summaries and multilingual audio briefings in: 🇬🇧 English, 🇫🇷 French, 🇩🇪 German, and 🇪🇸 Spanish.

* Hub Links
<p align="left" style="margin-top: 10px;">
  <a href="https://www.abr-insights.news" target="_blank" rel="noopener noreferrer">
    <img alt="ABR News hub" src="assets/abrinsights_news.webp" style="width:130px;height:72px;object-fit:cover;border-radius:6px;margin-right:10px;"/>
  </a>
  <a href="https://www.abr-insights.tech/" target="_blank" rel="noopener noreferrer">
    <img alt="ABR Tech hub" src="assets/abrinsights_tech.webp" style="width:130px;height:72px;object-fit:cover;border-radius:6px;margin-right:10px;"/>
  </a>
  <a href="https://www.abr-insights.site/" target="_blank" rel="noopener noreferrer">
    <img alt="ABR Market hub" src="assets/abrinsights_market.png" style="width:130px;height:72px;object-fit:cover;border-radius:6px;"/>
  </a>
</p>

---

### 📊 VU
Web-Based Finite Element Results Visualizer

VU is a web-based application to view and analyze finite element results. The project combines Flask, HDF5, VTK, and WebAssembly to provide an interactive visualization experience on both web and desktop targets.

* Project Links
  - [📺 YouTube Demo](https://www.youtube.com/watch?v=IancX0b6ZBI)
  - [🚀 Release Notes (Desktop)](https://github.com/basavaakula/ScyLab-Tools/releases/tag/VU-v1.0.0)

<p align="center">
  <img alt="vu" width="95%" src="assets/vu_visu.svg" />
</p>

---

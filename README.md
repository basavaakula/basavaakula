# Hi there 👋

<p align="center">
  <img alt="ScyLab" width="200" src="https://github.com/user-attachments/assets/677df6fb-3a89-4cdc-a679-e012f4adc0cd" />
</p>
I’m an engineer with a PhD in Computational Mechanics from École des Mines de Paris 🎓 and currently work as a Senior R&D Engineer designing and building web-based applications for complex simulation workflows.

My core interest lies in building intuitive, highly efficient tools that bridge the gap between advanced computing and practical engineering workflows ⚙️. I specialize in designing responsive graphical interfaces, automating highly parallel pipelines, and optimizing performance so that complex technologies can be deployed reliably in real-world environments.

Alongside my professional work, I design and release independent developer tools and serverless infrastructure software 🚀. My most recent project is AntiNode—an AI-first, stateless Backend-as-a-Service (BaaS) gateway built to give frontend engineers and indie hackers full-stack capabilities without origin-server overhead. Through these projects, I focus heavily on low-latency system design, cryptographic multi-tenancy, and removing repetitive infrastructural friction for developers 🛠️.

I also explore AI-driven technical content creation and system integrations 🤖, experimenting with how modern language models—like my conversational streaming engine, amAIra—can be securely routed to help analyze, communicate, and interface with complex data more effectively.

---

## My projects

<div style="display:flex;flex-wrap:wrap;gap:18px">

<div style="flex:1 1 420px;min-width:300px;border-radius:10px;padding:18px;">
  <h3 style="margin:0"><strong>ANTINODE</strong></h3>
  <p style="margin:10px 0 12px;line-height:1.5">
🧠 Antinode: AI-First BaaS for Frontend Developers

Antinode is a managed, AI-first Backend-as-a-Service (BaaS) platform that lets frontend engineers, indie hackers, and product teams ship full-stack web apps without provisioning servers, managing databases, or handling complex microservices. Integrate our thin client SDK and stay entirely frontend-first.

🚀 The Flagship Feature: amAIra Native Embeds

Real-time AI text generation shouldn't require a heavy origin server. Antinode puts amAIra directly into the gateway.

amAIra is a secure, proxy-native AI assistant interface. Configure commercial LLMs or local Ollama instances in your dashboard, and mount a high-performance streaming chat widget with zero complex server-side streaming logic or socket management. Antinode handles streaming buffers and token delivery natively, letting you drop conversational AI into static assets with a single script tag.

🛡️ The Complete Supporting Infrastructure

While amAIra powers user experiences, the gateway silently delivers the essential infrastructure every production SaaS needs:
<ul>
<li>🔒 Identity & IAM: Robust, secure user sessions backed by Google Sign-In under the hood. Your frontend code never handles raw OAuth primitives directly.<li>

<li>🔑 BYOK Secrets Vault: Third-party tokens and private API keys are encrypted via Google Cloud Secret Manager and loaded strictly in-memory during serverless handshakes, preventing client-side exposure.<li>

<li>💳 Billing & Stripe Subscriptions: Out-of-the-box payment orchestration. Connect Stripe to provision plans, handle checkouts, process signed webhooks, and launch billing portals effortlessly.<li>
<ul>

🛡️ The Perimeter Protection

Built with a strict cryptographic multi-tenancy model and edge financial circuit breaking, Antinode acts as an active billing shield—automatically dropping abusive traffic before it hits your upstream AI provider balances. Replace backend complexity with absolute frontend autonomy.
</div>


<div style="flex:1 1 420px;min-width:300px;border-radius:10px;padding:18px;">
  <h3 style="margin:0"><strong>VU-VERSE</strong></h3>
  <p style="margin:10px 0 12px;line-height:1.5">
  VU-VERSE is a unified visualization platform for exploring VTK HDF time-series datasets using Visualization Toolkit and its vtkHDF format.

The platform is built around cross-platform parity: the same UI layer, interaction model, and VTK rendering pipeline are shared across native and WebAssembly builds. This ensures consistent behavior, feature availability, and performance characteristics between desktop and web deployments, while preserving high-performance interactive visualization and time-series exploration.
  </p>
    <p>
    <ul>
      <li><a href="https://www.youtube.com/watch?v=I-roFNQmASY">YouTube demo</a></li>
      <li><a href="https://github.com/basavaakula/ScyLab-Tools/releases/tag/VU-VERSE">Release notes (desktop)</a></li>
      <li><a href="https://basavaakula.github.io/vu-verse/viewer.html">Web viewer</a></li>
      <li><a href="https://basavaakula.github.io/vu-verse/docs_site/index.html">Docs</a></li>
    </ul>
    </p>
  <div style="display:flex;gap:10px;align-items:center;margin-bottom:12px">
    <img alt="vu-verse" width="95%" src="assets/vu_verse_post.svg" />
  </div>
</div>

<div style="flex:1 1 420px;min-width:300px;border-radius:10px;padding:18px;">
  <h3 style="margin:0"><strong>ABR-INSIGHTS</strong></h3>
  <p style="margin:10px 0 12px;line-height:1.5">
    ABR-INSIGHTS is an AI-native information platform that automatically analyzes and summarizes stories from trusted, publicly available news sources. It delivers concise insights across technology, science, AI, global news and business, and ships extended summaries and multilingual audio briefings in: 🇬🇧 English, 🇫🇷 French, 🇩🇪 German, and 🇪🇸 Spanish.
  </p>
  <div style="display:flex;gap:10px;align-items:center;margin-bottom:12px">
    <a href="https://www.abr-insights.news" target="_blank" rel="noopener noreferrer"><img alt="ABR News hub" src="assets/abrinsights_news.webp" style="width:130px;height:72px;object-fit:cover;border-radius:6px;"/></a>
    <a href="https://www.abr-insights.tech/" target="_blank" rel="noopener noreferrer"><img alt="ABR Tech hub" src="assets/abrinsights_tech.webp" style="width:130px;height:72px;object-fit:cover;border-radius:6px;"/></a>
    <a href="https://www.abr-insights.site/" target="_blank" rel="noopener noreferrer"><img alt="ABR Market hub" src="assets/abrinsights_market.png" style="width:130px;height:72px;object-fit:cover;border-radius:6px;"/></a>
  </div>
</div>

<!-- VU card -->
<div style="flex:1 1 420px;min-width:300px;border-radius:10px;padding:18px;">
  <h3 style="margin:0"><strong>VU</strong></h3>
  <p style="margin:10px 0 12px;line-height:1.5">
    VU is a web-based application to view and analyze finite element results. The project combines Flask, HDF5, VTK and WebAssembly to provide an interactive visualization experience on both web and desktop targets.
  </p>
    <p>
    <ul>
      <li><a href="https://www.youtube.com/watch?v=IancX0b6ZBI">YouTube demo</a></li>
      <li><a href="https://github.com/basavaakula/ScyLab-Tools/releases/tag/VU-v1.0.0">Release notes (desktop)</a></li>
    </ul>
    </p>
  <div style="display:flex;gap:10px;align-items:center;margin-bottom:12px">
    <img alt="vu" width="95%" src="assets/vu_visu.svg" />
  </div>
</div>

</div>

---

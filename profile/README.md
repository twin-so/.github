<img width="250" height="66.41" alt="image" src="https://github.com/user-attachments/assets/64cd3b81-a0b1-4498-ab1d-dcd72e753ecb" />

[Twin](https://twin.so) is an agent builder that lets anyone automate workflows across their applications using natural language — no code, no setup, no infrastructure.

Under the hood, it's a multi-agent system: an **orchestrator** routes intent, a **builder** creates the automation (API integrations, browser actions, code execution), and a **runner** executes it autonomously on a schedule — at ~10x lower cost. Our browser-use agent is core to ~80% of user workflows.

**1,000,000 workflows automated. 100,000 agents deployed. 60,000 users.**

## What we built

Twin's stack is Rust and Nix, end to end. A few things we're proud of:

- **Multi-agent framework** — A proprietary orchestrator/builder/runner architecture. The builder uses high-reasoning models to create tools and integrations from scratch (discovering APIs, writing schemas, testing iteratively). The runner executes autonomously with smaller models at a fraction of the cost. Agents self-heal when integrations break: diagnose → search docs → patch the tool → memorize the fix.

- **Wayland compositor for computer-use agents** — A custom headless Wayland compositor (`waysmoother`) that unifies composition, H.264 encoding, and WebSocket streaming in a single process. Commit-driven encoding (no polling, no tearing, no redundant frames), adaptive framerate, and raw NAL unit delivery to WebCodecs in the browser. Sub-50ms end-to-end latency at 100+ concurrent sessions — ~3× more efficient than Xvfb + FFmpeg.

- **Browser-use agent framework** — Two years of iteration on autonomous browser control. Agents operate in cloud-sandboxed Chromium sessions via Wayland, with full support for popups, auth flows, file downloads, and multi-tab navigation. API-first, browser as fallback — covering any website, even without an API.

- **NixOS infrastructure** — Reproducible, elastic deployments on Hetzner Cloud. Each session gets its own sandboxed compositor + browser process. Zero-config scaling from 10 to 1,000+ concurrent sessions.

## Vision

Coding agents like Cursor and Lovable proved you can vibe code software. Twin is the platform to vibe code everything else — sales, support, logistics, finance, marketing, back-office. Describe what you want in plain language, and Twin builds and runs the automation end to end.

Our fastest-growing segment is SMBs: delivery services, rental operators, real estate agents, agencies, e-commerce stores. Users who were never served by existing automation tools, building production-grade agents in minutes from their phone. We win because Twin is simple enough for non-technical users and powerful enough to automate real businesses.

Founded in 2024, we've raised €12M from [LocalGlobe](https://localglobe.vc) and unicorn founders including Hugging Face, Datadog, Zama, and Alan.

[Check out our open positions](https://twin.so/careers)

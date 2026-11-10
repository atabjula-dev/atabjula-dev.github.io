# Portfolio site brief — Akhil Tabjula

Purpose: the source of truth for this repo's personal portfolio (GitHub Pages, `atabjula-dev.github.io`).

Build a single-page personal portfolio site as ONE self-contained index.html
(inline CSS + vanilla JS, no frameworks, no CDN dependencies, no build step).
It will be hosted on GitHub Pages.

## WHO
Akhil Tabjula — Senior Data Engineer, 10+ years. Builds streaming, lakehouse,
and ML data platforms on Azure, Databricks, and Snowflake.
Positioning (Nov 2026): site title is "Data & AI Engineer", targeting BOTH Senior Data Engineer and
Forward Deployed Engineer roles with one story (no view toggle). The site is a portfolio, not a job ad:
never add "Open to … roles" / job-seeking lines anywhere (hero, contact, meta).
Confirmed FDE evidence (only claim these): scoping with business/sales stakeholders, demos/exec readouts,
shipping tools non-engineers use. NOT client-facing delivery at Wipro. Agentic AI work is recent only;
don't imply it in earlier roles.
Contact: tabjulaakhil@gmail.com | linkedin.com/in/akhil172 (no phone number).
Resume file: resume.pdf (same folder).

## HERO — SIGNATURE ANIMATION
Animated data pipeline: glowing packets flowing
Stages are generic verbs (Ingest → Stream → Process → Serve → Consume); the tool line in each stage
cycles (STAGE_TOOLS in the JS) so the hero isn't tied to one stack. Tooltips describe each stage across tools.
No section-level instruction captions or disclaimers ("hover/click to …", "generic examples only");
interactions should be self-evident. One short line inside an interactive demo is fine.
Hovering a stage shows a short tooltip on how I've used it.
Name, title, one-line positioning, buttons: Download Resume, LinkedIn.

## ABOUT
Short bio. Personal touch, one plain line with no metaphor: I collect coins, currency, and travel mugs.

## HOW I WORK (#approach, between About and Experience)
Bridges the DE and FDE audiences. Four strength cards (Start with the user's problem,
Own it end to end, Integrate messy real systems, Make it trustworthy). "Zero to one" was removed on request. Each has a "Show where" chip
(`data-tool="w-*"`, `data-label` sets the filter-bar text) that reuses the chip filter; add the `w-*`
slug to a role/project's `data-tools` only when that item truly demonstrates the strength.

## EXPERIENCE (company-based timeline; 2–3 impact lines + 4–6 tool chips each)
- Coca-Cola Southwest Beverages, Oct 2023–Present: joined as sole data engineer,
  built the function and now lead a team of 4 within the Advanced Analytics org.
  Chips: Databricks, Snowflake, dbt, Kafka, LangGraph
- Victoria's Secret, Jun 2021–Sep 2023: led Teradata→Snowflake migration;
  re-architected real-time POS ingestion from Mulesoft to Kafka.
  Chips: Snowflake, Kafka, Snowpark, dbt
- Inspire Brands, Jan–May 2021
- Wipro Technologies, Aug 2014–Aug 2019: built features for Dynamics 365
  scheduling modules with C# and Azure.
- Education: M.S. Data Science, University of North Texas;
  B.Tech, KL University

## CAPABILITIES (grouped, not a flat list)
- Streaming & Ingestion: Kafka, Structured Streaming, Auto Loader, Snowpipe,
  Fivetran, Lakeflow Connect
- Lakehouse & Warehouse: Databricks, Delta Lake, Unity Catalog, Snowflake, Redshift
- Transformation & Modeling: dbt, Spark, Snowpark, Kimball, Data Vault
- Data Quality & Governance: Great Expectations, RBAC, dynamic masking,
  column-level security
- AI & ML Data: LangChain/LangGraph, RAG pipelines, MCP agents, vector search
- Cloud & DevOps: Azure, AWS (S3, Glue, Lambda, Batch), Docker, Kubernetes,
  GitHub Actions, Databricks Asset Bundles
- Apps & Delivery: Python, FastAPI, React + TypeScript, REST / GraphQL APIs, OAuth2, Power BI
- Geospatial: PostGIS, GeoPandas, H3, CARTO

Every tool chip is clickable: clicking highlights all roles/projects that
used it and dims the rest; clicking again resets.

## PROJECTS (3 cards; expand on click: Problem → Architecture → Key decisions → Outcome)
1. Real-time POS streaming: Kafka → Snowpark → Snowflake Streams/Tasks → data marts
2. Catching a silent vendor data rewrite: a third-party source retroactively
   changed historical data; how it was detected and guarded against
3. Agentic API orchestrator: LangGraph stateful agent + vector search over
   API metadata; an execute agent gathers params, calls the API, and
   explains the result in plain language

Include a simple animated SVG architecture diagram in each.

## CONTACT
Email + LinkedIn + resume download.

## STYLE
Modern dark theme with light/dark toggle. Subtle scroll-reveal animations,
hover lift on cards, animated "10+ years" counter. Tasteful, not flashy.
Fully responsive (looks great on phones). Respect prefers-reduced-motion.
Fast load.

## SEO / SHARING
`<title>Akhil Tabjula | Data &amp; AI Engineer</title>`, meta description,
Open Graph tags so the link previews nicely on LinkedIn, simple inline SVG
favicon with initials "AT".

## RULES
- Architecture patterns only — no internal company data, schemas, or screenshots.
- No revenue, ROI, or other numeric business metrics.
- Never show the phone number (it appears in the source resume; keep it off the site).
- Build in stages: structure first, then styling, then animations. Show the user after each stage.

## AGENTIC AI (second group inside #projects, anchor `#agents` on its `.group-head`)
Projects is ONE section ("Selected work") with two `.group-head` groups: "Data platforms" (the 2
collapsible pattern cards) first, then "Agentic AI" (the 2 showcases). No separate nav item.
Keep showcases lean: the Orchestrator graph is static nodes with LLM/Code badges (no per-agent
detail panel), lit by 3 "Try a route" prompts; no "Add an API" callout. No-Guess shows safety strip +
"Walk the pipeline" only; the generated-project explorer lives inside its deep-dive.
Two interactive showcases, sourced from `sources/agentic_api_orchestrator.md` and
`sources/no-guess-test-agents.md` (local only, gitignored). They replaced the old Project 3 card.
Each showcase keeps only the pitch + interactive demos visible; supporting detail lives in a
collapsed `<details class="deep-dive">` ("Architecture & design details"). Avoid restating the same idea.
1. Agentic API Orchestrator: before/after toggle, clickable 8-agent graph, 3 "Try a route" prompts
   (catalog / execute auto-run / low-confidence clarify). Deep-dive: layers, hybrid intelligence,
   interaction design.
2. No-Guess Test Agents (fail-closed test automation): 10-stage clickable pipeline demo
   (approval gate locks Generate/Ready/Execute; conflict toggle → clarify → blocks only SC-02;
   toggling conflict invalidates approval), skills vs auditors, generated-project file explorer.

Confidentiality rules for these projects (strict):
- No employer names, internal product/API names, hostnames, scopes, env vars, IDs, repos.
- Don't attribute them to any employer anywhere on the site (Experience bullets included).
- No healthcare / insurance / claims / eligibility / benefits / member language. Domain-agnostic only.
- Generic examples only ("Lookup API A", fictional `orders_sync` demo data). No invented metrics.

## Build status
- Stage 1 (structure): done
- Stage 2 (styling): done (theme tokens on :root / [data-theme="light"], toggle persists to localStorage;
  horizontal pipeline SVG `.pipe-h` on desktop, vertical `.pipe-v` under 720px)
- Stage 3 (animations/interactivity): done. All JS is one IIFE at the end of index.html: theme toggle,
  scroll reveal (IntersectionObserver), 10+ counter, rAF pipeline packets along `.links path`,
  stage tooltips (hover / focus-visible / tap), chip filter driven by `data-tool` on chips and
  `data-tools` on `.filterable` roles/projects, floating `.filter-bar`. Reduced motion → static packets, no reveal/counter.
  To add a tool: give the chip a `data-tool` slug and add that slug to the relevant `data-tools` lists.
- `resume.pdf` (repo root) is exported from `sources/AkhilTabjula_Resume.docx` via Word with the phone
  number stripped from the contact line. Re-export the same way whenever the .docx changes.
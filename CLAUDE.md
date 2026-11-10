# Portfolio site brief — Akhil Tabjula

Purpose: the source of truth for this repo's personal portfolio (GitHub Pages, `atabjula-dev.github.io`).

Build a single-page personal portfolio site as ONE self-contained index.html
(inline CSS + vanilla JS, no frameworks, no CDN dependencies, no build step).
It will be hosted on GitHub Pages.

## WHO
Akhil Tabjula — Senior Data Engineer, 10+ years. Builds streaming, lakehouse,
and ML data platforms on Azure, Databricks, and Snowflake.
Contact: tabjulaakhil@gmail.com | linkedin.com/in/akhil172 (no phone number).
Resume file: resume.pdf (same folder).

## HERO — SIGNATURE ANIMATION
Animated data pipeline: glowing packets flowing
Sources → Kafka → Spark/Databricks → Snowflake → Dashboards/ML.
Hovering a stage shows a short tooltip on how I've used it.
Name, title, one-line positioning, buttons: Download Resume, LinkedIn.

## ABOUT
Short bio. Personal touch: I collect coins, currency, and travel mugs.

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
`<title>Akhil Tabjula | Senior Data Engineer</title>`, meta description,
Open Graph tags so the link previews nicely on LinkedIn, simple inline SVG
favicon with initials "AT".

## RULES
- Architecture patterns only — no internal company data, schemas, or screenshots.
- No revenue, ROI, or other numeric business metrics.
- Never show the phone number (it appears in the source resume; keep it off the site).
- Build in stages: structure first, then styling, then animations. Show the user after each stage.

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
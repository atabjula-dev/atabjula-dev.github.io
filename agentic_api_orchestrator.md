Add this project to my interactive personal portfolio website. Match the existing site’s visual language, interaction patterns, and component style. Present it as a featured / showcase project with rich interactive detail (not a flat text dump). Prefer expandable sections, hoverable architecture nodes, filterable tech tags, and a step-through “how it works” flow if those patterns already exist on the site.

PUBLIC / CONFIDENTIALITY RULES (STRICT):
- Do NOT include employer names, internal product names, internal API names, hostnames, OAuth scopes, credentials, environment variables, real identifiers, private repos, or internal docs.
- Do NOT mention healthcare, insurance, claims, eligibility, coverage, benefits, members, patients, subscribers, medical data, or any industry-specific domain language.
- Describe the product purely as an enterprise conversational API orchestration system.
- If examples are needed, use fully generic labels only (e.g., “Catalog API”, “Lookup API A”, “Lookup API B”).
- Do not invent metrics, production claims, or company branding.

================================================================================
PROJECT (PUBLIC-SAFE, DOMAIN-AGNOSTIC)
================================================================================

### Display title options (pick one)
- Agentic API Orchestrator
- Conversational API Orchestrator
- Multi-Agent API Copilot
- Natural-Language Enterprise API Assistant

### One-line pitch
A multi-agent chat assistant that turns plain-English questions into authenticated enterprise API calls — selecting the right API, reading its contract, collecting missing fields, executing the request, and explaining the result.

### Short blurb (card / grid)
Built an interactive AI orchestrator with FastAPI, LangGraph, and React that lets non-technical users query enterprise APIs in natural language. A multi-agent pipeline classifies intent, retrieves the best API via embeddings, guides users through lookup scenarios and payload forms, calls live backends with OAuth authentication, and returns a clear business-friendly answer. New APIs are onboarded through registry cards and OpenAPI contracts — without rewriting the agent graph.

### Longer description (detail page)
Many users know the question they want answered, but not which API to call, which request shape to use, how to fill the payload, or how to interpret the JSON response.

This project solves that with a conversational agentic system:

1. The user asks in chat.
2. The system decides whether they want catalog knowledge (“what APIs exist?”, “what fields does this need?”) or an actual lookup/execution.
3. For execution, it retrieves the best matching API from a capability registry, loads that API’s OpenAPI contract, and guides the user through scenario selection and required fields using interactive cards and forms.
4. When the payload is complete, it authenticates, calls the target API (REST or GraphQL), and explains the response in plain language.
5. After the answer, quick actions let the user edit the same payload or switch lookup scenarios without restarting the conversation.

The experience is closer to a guided copilot than a one-shot chatbot: clarification loops, interrupt/resume, editable forms, and post-response retries are first-class.

### Problem → Solution (before / after)

BEFORE (manual):
User has a question → doesn’t know which API → reads documentation/contract → manually builds request → authenticates → calls API → interprets raw JSON.

AFTER (agentic):
User asks in plain English → agent selects API → agent reads contract → agent asks only for missing values (or opens a form) → agent builds payload → agent calls API → agent explains the result → user can edit values or switch lookup and try again.

### Capability framing (generic only)
Supports a small set of onboarded enterprise APIs for:
- Catalog discovery (list/describe available APIs and request shapes)
- Structured lookup execution against registered backends
- Multi-scenario request patterns for APIs that support more than one payload shape

If the UI needs named examples, use only:
- “Catalog / Discovery”
- “Lookup API A”
- “Lookup API B”
- “Lookup API C”

### Signature interactive UX features
- Chat UI with markdown answers and a visible agent / request-flow trace
- API clarification cards when routing confidence is low
- Lookup scenario cards for APIs with multiple request shapes
- Editable payload forms with contract-driven validation
- Auto-run when the user’s message already supplies everything needed for exactly one lookup
- Post-answer quick actions: edit payload / choose a different lookup
- Optional feedback capture (useful / not useful)
- Sample prompt chips for demos
- Session memory for chat history and per-API context
- Theme support and chat history sidebar

### Architecture (interactive diagram friendly)

Layers:
1. Web UI — React + TypeScript + Vite
2. API server — FastAPI
3. Agent orchestration — LangGraph state machine with interrupt/resume
4. Knowledge base — MongoDB + JSON source-of-truth files
5. External services — LLM gateway, embedding gateway, OAuth token service, target APIs

Agent pipeline (8 focused roles):
1. Intent Router — catalog vs execute; retrieve best API; clarify when unsure
2. Catalog Agent — answer “what APIs / fields / scenarios exist?” without calling backends
3. Contract Discovery — resolve how to invoke the selected API
4. Contract Reader — parse OpenAPI; extract fields, constraints, scenarios
5. Parameter Collector — conversation, scenario selection, validation, forms (pauses for user input when needed)
6. Payload Builder — shape the final request body
7. API Executor — authenticate and call the target API; return field errors to the form when needed
8. Response Explainer — convert raw responses into a clear business answer + follow-ups

Design principle:
Keep the graph generic. New API behavior comes from registry cards + contracts, not hardcoded branches per API.

Hybrid intelligence:
- LLM only where language judgment is needed (routing refinement, extraction, explanation)
- Deterministic code for contract parsing, payload shaping, auth, and HTTP/GraphQL execution
- Guardrails: do not invent missing identifiers or invent facts not present in the API response

### Knowledge / retrieval approach
- Capability cards are embedded and retrieved with similarity search to choose an API
- Contracts are fetched exactly after selection (fuzzy selection, exact execution)
- Fallback keyword scoring if vector retrieval is disabled

### Extensibility (strong public talking point)
Add a new API without changing the agent graph:
1. Add a capability card
2. Add an OpenAPI contract (optionally with multiple lookup scenarios)
3. Link card → contract
4. Re-index / re-embed
Catalog answers automatically include newly active APIs.

### Tech stack tags
Backend: Python, FastAPI, LangGraph, LangChain, Pydantic, httpx, MongoDB, Pytest, OAuth2
Frontend: React, TypeScript, Vite, Markdown rendering
AI / data: LLM gateway, embeddings, vector retrieval, conversational memory
Protocols: REST, GraphQL, OpenAPI

### Engineering challenges highlighted
- Separating catalog questions from execution so backends aren’t called unnecessarily
- Confidence-aware routing with interactive clarification instead of silent wrong guesses
- Contract-driven forms instead of hardcoded UIs per API
- Multi-scenario APIs with card selection and smart auto-run
- Authenticated live calls with recovery when the backend rejects fields
- Mixing LLM judgment with deterministic request building for reliability
- Making the system extensible via data (registry + contracts)

### Safe demo quote chips (fully generic)
Catalog:
- “List all available APIs”
- “What fields does Lookup API A need?”
- “What lookup scenarios are supported?”

Execute:
- “Run a lookup with these identifiers”
- “Fetch details for this account”
- “Show results for this request”

Mid-flow:
- “Which lookup should I use?”
- “What is required for this request?”
- “Explain the contract fields”

Do not include real IDs in any quote chips.

### Role framing (edit to match my contribution)
“Designed and built end-to-end: multi-agent LangGraph orchestration, FastAPI backend, React chat UI, Mongo-backed knowledge/retrieval, OAuth-authenticated API execution, interactive clarification/form loops, and a registry/contract onboarding model for new APIs.”

### Suggested interactive portfolio blocks
1. Hero: title + one-line pitch + tech pills
2. Before → after stepper
3. Clickable 8-agent graph with short job descriptions
4. Feature gallery describing cards / forms / quick actions (no sensitive screenshots)
5. Extensibility callout: “Add an API with config, not a rewrite”
6. Filterable tech tags
7. Outcomes focused on architecture and UX quality — not any business domain

### Categories / tags
AI Agents, LangGraph, RAG, Full-Stack, Conversational UI, API Orchestration, FastAPI, React

### Tone
Professional, product-minded, technically specific.
Emphasize guided interaction and reliability over “magic chatbot.”
Do not claim production scale or business impact metrics unless I provide them.
Do not imply any specific industry domain.

Please integrate this project into the site now using only this public-safe, domain-agnostic description.

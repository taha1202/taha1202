# Muhammad Taha

Software engineer in Karachi. I work on AI systems and backend infrastructure —
currently at ByteCorp, building agent pipelines and LLM-backed applications.

Most of what I find interesting happens after something fails: what an agent
does when its tools lie to it, whether a pipeline can resume mid-flight, how a
system behaves when the fallback path is also broken.

---

### Cascade — chaos engineering for LLM agents
[`taha1202/cascade`](https://github.com/taha1202/cascade)

Agent frameworks are tested on the happy path. Cascade injects semantically
distinct faults at the tool boundary — timeouts, silent empties, confidently
wrong answers, schema drift — and searches for failures that single-fault
testing structurally cannot find.

Against a reference agent with retry logic, a cache fallback, and response
validation, it found **27 interaction failures** across 510 schedules. Every
constituent fault was survivable alone. Single-fault testing rates that same
agent 70% robust and finds none of them.

They all share one shape: a persistent primary outage paired with a degraded
fallback — the path that, by construction, is the least exercised code in the
system.

Runs offline on CPU in ~7 seconds. No API keys, no GPU.

---

### Elsewhere

- **FraudHunt** — multi-signal counterfeit-listing detection: CNN over product
  imagery, transformer embeddings over review language, and PELT changepoint
  detection over rating behaviour. Fusing all three beat any single signal.
- **Document extraction pipeline** (ByteCorp) — agent-based extraction from
  long multi-page documents, running unattended through automated Microsoft
  Graph 2FA. Hours of analyst work down to under ten minutes.

---

### Working with

`Python` · `FastAPI` · `C#` · `ASP.NET Core` · `TypeScript` · `React` ·
`Next.js` · `PostgreSQL` · `MSSQL` · `Docker` · `Azure` · `AWS`

---

BS Computer Science, FAST NUCES (2026) · Open to 2026 roles

[Email](mailto:tahaghulam10@gmail.com) · [LinkedIn](https://linkedin.com/in/taha-ghulam)

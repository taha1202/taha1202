# Muhammad Taha

Computer science graduate working as a software engineer in Karachi. I build
AI-based products, and most of my attention these days goes to agents and the
systems around them.


---

### Cascade

[`taha1202/cascade`](https://github.com/taha1202/cascade) — chaos engineering
for LLM agents.

Agent frameworks get tested on the happy path. Cascade breaks things on purpose
at the tool boundary: timeouts, empty responses that look like success, answers
that are well-formed and confidently wrong, schemas that drift the way a real
API does after an unannounced version bump.

I ran it against an agent I wrote to be genuinely careful, with retries, a cache
fallback, and validation on everything it received. It found 27 failure
combinations where each individual fault was survivable on its own. Test those
faults one at a time and the agent looks 70% robust. It isn't.

They all turned out to be the same bug wearing different clothes: the primary
source goes down long enough to exhaust retries, so the agent reaches for its
fallback, and the fallback is degraded too. That path is the least-tested code
in the system because it only ever runs when something else has already failed.

The whole thing runs on CPU in about seven seconds. No API keys, so you can
clone it and see the result yourself.

My first version of it found nothing at all, which is written up in the repo.
The faults only fired once and the agent's retry landed on a healthy call.
Real outages don't heal in 50 milliseconds.

---

### Anchor

[`taha1202/anchor`](https://github.com/taha1202/anchor) — durable execution for
agents.

The other half of the same problem. Cascade shows you how agents die; Anchor
keeps the work when they do. Steps get written to a log as they finish, so a
run that gets killed at step nine restarts at step nine instead of step one.

Most of the design falls out of one decision: state is derived from the log
rather than stored next to it. Two sources of truth can disagree after a crash,
and then you're stuck deciding which one lied. Keeping one means recovery and
time travel are the same operation — replay everything, or replay part of it.

The crash tests spawn real subprocesses that kill themselves with `os._exit()`
mid-run. No unwinding, no cleanup, nothing flushed. Testing durability with a
graceful shutdown would be testing nothing. CI runs those on Linux and Windows
because the two handle process death and fsync differently.

---

### Other things I've built

**FraudHunt** — counterfeit listing detection using three signals at once: a CNN
on product images, transformer embeddings over review text, and PELT changepoint
detection on rating history. The fusion caught things no single signal did.

**Document extraction pipeline** — pulls structured data out of long, messy
documents. The hard part wasn't extraction, it was getting the thing to run
overnight without a human babysitting the login step.

---

### Tools I reach for

Python and FastAPI most days. C# and ASP.NET Core. TypeScript, React and
Next.js on the frontend. Postgres, MSSQL, Docker, Azure, AWS.

---

[Email](mailto:tahaghulam10@gmail.com) · [LinkedIn](https://linkedin.com/in/taha-ghulam)

# Python Guide for Java Developers

A self-paced, 56-day Python learning guide built for experienced Java developers. One hour per day. Every concept is framed with a Java parallel so you spend time learning Python idioms, not re-learning what you already know.

## What this is

A static HTML guide — no build step, no server. Open `index.html` in a browser and work through the days. Progress (done/not-done per day) is saved in `localStorage`.

## Structure

```
index.html      — landing page with all 56 day cards and week filter
day1.html       — Day 1: Setup + Basics
...
day56.html      — Day 56: Capstone Project
styles.css      — shared stylesheet for all day pages
```

Each day page follows the same structure:
1. **Plan for the Day** — what's covered, estimated time, Java parallel summary
2. **Content** — concept-by-concept with Java → Python side-by-side examples
3. **Quick Reference Card** — scannable cheat sheet of everything covered
4. **Wrap-up** — key takeaways, practice suggestions, teaser for the next day

## Curriculum

### Phase 1 — Foundation (Days 1–14)
Variables, control flow, functions, data structures, strings, file I/O, error handling, OOP, dunder methods, iterators, generators, decorators, context managers, type hints, dataclasses. Two mini projects: CLI Task Manager and OOP refactor.

### Phase 2 — Core Libraries (Days 15–28)
`collections`, `itertools`, `functools`, `pathlib`, `datetime`, `json`, `requests`, `httpx`, threading, multiprocessing, `asyncio`, NumPy, Pandas, `pytest`. Project: REST API client and data pipeline.

### Phase 3 — Backend + AI (Days 29–42)
FastAPI, SQLAlchemy, Pydantic, Docker, environment config, LangChain, agents, ChromaDB, OpenAI SDK, Celery, Redis, logging. Projects: full CRUD REST API and a RAG chatbot.

### Phase 4 — Advanced (Days 43–56)
ABCs, Protocols, metaclasses, `__slots__`, Python internals, profiling, packaging, design patterns, advanced testing, CI/CD, scripting, web scraping, scikit-learn. Projects: library packaging and a capstone.

## Java → Python quick reference

| Python | Java equivalent |
|--------|----------------|
| `list` | `ArrayList` |
| `dict` | `HashMap` |
| `tuple` | Immutable `List` / `Record` |
| `set` | `HashSet` |
| `@dataclass` | Lombok `@Data` / Java `Record` |
| `@property` | getters/setters |
| `yield` / generator | Iterator pattern |
| decorator | Spring AOP `@Around` |
| `with` statement | try-with-resources |
| `asyncio` | `CompletableFuture` |
| `pytest` | JUnit 5 + Mockito |
| FastAPI | Spring Boot `@RestController` |
| SQLAlchemy | JPA / Hibernate |
| Pydantic | Bean Validation + `@ConfigurationProperties` |
| Celery | `@Async` + Quartz |
| `typing.Protocol` | structural interface (no `implements`) |
| `abc.ABC` | abstract class |

## How to use

1. Clone or download this repo.
2. Open `index.html` in any modern browser.
3. Work through one day per session (~1 hour each).
4. Mark days complete — progress persists in your browser.

No dependencies. No npm install. No Python required to read the guide.

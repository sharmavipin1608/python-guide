# CLAUDE.md — Python Guide for Java Developers

## Project Overview
A self-paced Python learning guide for an experienced Java developer.
One hour per day, 56 days total. Each day is a standalone HTML page.
The goal is to learn Python idiomatically — not just "Java in Python syntax".

---

## Audience
- Experienced Java developer (Spring Boot, JPA, Kafka, etc.)
- Familiar with OOP, design patterns, concurrency
- Learning Python for backend, AI/ML, and automation
- Every concept should be framed with a Java parallel where relevant

---

## File Structure
```
/python-guide/
  CLAUDE.md         ← this file
  index.html        ← landing page, cards for all 56 days
  day1.html
  day2.html
  ...
  day56.html
```

---

## index.html Structure
- Header with title and subtitle "Python for Java Developers"
- Week selector bar: "All", "Week 1" ... "Week 8" — filters day cards, no page reload
- Grid of 56 day-cards grouped visually by phase
- Each card shows:
  - Day number
  - Topic name
  - Phase tag (Foundation / Core Libraries / Backend+AI / Advanced)
  - Type tag (core / lib / project)
  - For project days: one-line description of what gets built
  - Done/not-done state (stored in localStorage)
- Click card → opens dayN.html
- Active week button highlighted in accent yellow

---

## Page Structure (every dayN.html)

### 1. Plan for the Day
- What will be covered today (bullet list of subtopics)
- Estimated time per section
- Java parallel summary — one-liner per concept

### 2. Content
- One section per concept/subtopic
- Each concept:
  - Short explanation (2–4 sentences)
  - Java snippet → Python equivalent (side by side)
  - Annotated Python example with inline comments
- Keep examples practical, not toy problems

### 3. Quick Reference Card
- Cheat sheet of all syntax/methods covered that day
- Scannable, no prose — just code snippets with one-line comments

### 4. Wrap-up
- 3–5 key takeaways
- What to practice before next day
- Teaser for next day's topic

---

## Design Rules
- Dark background: #0d0d0d
- Surface: #1a1a1a
- Card background: #141414
- Border: #2a2a2a
- Accent: #f0e040 (yellow)
- Secondary accent: #40e0b0 (teal)
- Project tag color: #ff6b35 (orange)
- Font: Syne for headings, JetBrains Mono for code
- Load both from Google Fonts
- Syntax highlighting: highlight.js from cdnjs.cloudflare.com
- Java code blocks: grey-tinted background (#1a1a2e), subtle blue left border
- Python code blocks: dark background (#0d1a0d), yellow left border (#f0e040)
- Side-by-side Java vs Python: two-column grid, collapses to single column on mobile
- Prev / Next day navigation buttons at bottom of each page
- Back to index link in top-left of each day page
- Smooth hover transitions on cards
- Mobile responsive

---

## Building Instructions for Claude Code

When asked to build a day or range of days:
1. Read CLAUDE.md first
2. Follow page structure exactly: Plan → Content → Quick Reference → Wrap-up
3. Use the design rules — no deviations
4. Frame every concept with a Java parallel
5. Use highlight.js for syntax highlighting
6. After building day files, update index.html to reflect newly added days
7. Never skip the Quick Reference Card section
8. All Python examples must be runnable Python 3.10+
9. For project days: the day page should define the project clearly at the top, with a spec of what to build, inputs, outputs, and stretch goals

---

## 56-Day Curriculum

### Phase 1 — Foundation (Week 1–2)

**Day 1 — Setup + Basics** `core`
- Install Python, pip, venv — and why venv exists (like Maven local repo but per-project)
- Variables and dynamic typing — no `String x`, no `int y`
- Built-in types: int, float, str, bool, None
- f-strings — better than Java's String.format()
- print() and input()
- Running a .py file vs Java's compile-then-run

**Day 2 — Control Flow + Comprehensions** `core`
- if / elif / else — no switch until Python 3.10 match
- for loops — iterating over anything (no index needed)
- while, break, continue, else on loops (yes, loops have else)
- List comprehensions — replaces 90% of Java for-loop + add patterns
- Dict and set comprehensions
- Ternary expression: `x if condition else y`

**Day 3 — Functions** `core`
- Defining functions with def
- Default parameter values
- *args — variable positional args (like Java varargs)
- **kwargs — variable keyword args (no Java equivalent)
- Returning multiple values with tuples
- Lambda functions
- Functions as first-class objects — pass them as arguments
- Brief intro to decorators (full coverage Day 11)

**Day 4 — Data Structures** `core`
- list — ordered, mutable (like ArrayList)
- tuple — ordered, immutable (like an immutable List / Record)
- dict — key-value store (like HashMap), insertion-ordered since Python 3.7
- set — unordered unique elements (like HashSet)
- When to use each
- Common operations: append, pop, get, in, len, sorted, enumerate, zip
- Tuple unpacking and dict unpacking with **

**Day 5 — Strings + File I/O** `core`
- String methods: split, join, strip, replace, startswith, endswith, upper, lower
- String slicing: s[1:4], s[::2], s[::-1]
- Multiline strings with triple quotes
- Regex basics with re module: search, match, findall, sub
- Reading and writing files with open()
- Context manager pattern with open() (preview of Day 12)
- CSV reading/writing with csv module

**Day 6 — Error Handling + Modules** `core`
- try / except / else / finally
- Catching specific exceptions vs bare except
- Raising exceptions with raise
- Creating custom exception classes (like Java custom exceptions)
- Importing modules: import, from x import y, as aliasing
- Creating your own module
- __name__ == '__main__' pattern — Python's entry point equivalent

**Day 7 — Mini Project: CLI Task Manager** `project`
- Project: Build a command-line task manager
- What to build: A CLI app that lets you add, list, complete, and delete tasks. Tasks are persisted to a JSON file between runs.
- Inputs: Command-line interaction (menu-driven)
- Outputs: tasks.json file, formatted task list in terminal
- Covers: functions, file I/O, dicts, lists, error handling, modules
- Stretch goal: Add due dates and filter tasks by status

**Day 8 — OOP: Classes + Inheritance** `core`
- Defining classes with class
- __init__ as constructor (like Java constructor)
- self — Python's explicit this
- Instance variables vs class variables
- Instance methods
- Inheritance and super()
- Method overriding
- No access modifiers — convention of _private and __mangled
- Duck typing — no interfaces needed (yet)

**Day 9 — Dunder Methods + Properties** `core`
- What dunder (double underscore) methods are
- __str__ and __repr__ (like Java toString())
- __eq__, __hash__ (like Java equals/hashCode)
- __len__, __contains__, __getitem__
- @property decorator for getters
- @property.setter for setters
- Why this is cleaner than Java getters/setters

**Day 10 — Iterators + Generators** `core`
- What makes something iterable
- __iter__ and __next__ protocol
- Creating a custom iterator class
- yield keyword — turning a function into a generator
- Generator expressions (like lazy list comprehensions)
- Why generators are memory-efficient vs building full lists
- Real-world use: processing large files line by line

**Day 11 — Decorators Deep Dive** `core`
- How decorators work under the hood (functions wrapping functions)
- Writing a simple decorator
- functools.wraps — preserving metadata
- Decorators with arguments
- Stacking multiple decorators
- Built-in decorators: @staticmethod, @classmethod
- @lru_cache for memoization
- Java parallel: like Spring AOP @Around advice

**Day 12 — Context Managers** `core`
- The with statement
- How __enter__ and __exit__ work
- Writing a custom context manager with a class
- contextlib.contextmanager — generator-based shortcut
- Real uses: file handling, DB connections, timing blocks
- Java parallel: try-with-resources

**Day 13 — Type Hints + Dataclasses** `core`
- Why type hints exist (not enforced, but tooling uses them)
- Basic hints: str, int, float, bool
- typing module: List, Dict, Tuple, Optional, Union, Any
- Function signature hints
- @dataclass decorator — auto-generates __init__, __repr__, __eq__
- dataclass fields, defaults, frozen=True for immutability
- Java parallel: @dataclass ≈ Java Record or Lombok @Data

**Day 14 — Mini Project: Refactor CLI with OOP** `project`
- Project: Refactor the Day 7 CLI Task Manager using OOP
- What to build: Rewrite using a Task dataclass, a TaskManager class, decorators for logging, and type hints throughout
- Inputs: Same as Day 7
- Outputs: Cleaner, OOP-structured codebase with same functionality
- Covers: classes, dataclasses, decorators, type hints, properties
- Stretch goal: Add a TaskFilter class with method chaining

---

### Phase 2 — Core Libraries (Week 3–4)

**Day 15 — collections module** `lib`
- Counter — count occurrences (replaces verbose HashMap counting)
- defaultdict — dict with default values, no KeyError
- OrderedDict — when insertion order matters explicitly
- deque — double-ended queue, O(1) append/pop from both ends
- namedtuple — lightweight immutable data object
- Java parallels for each

**Day 16 — itertools + functools** `lib`
- itertools: chain, cycle, islice, product, permutations, combinations
- itertools.groupby — group sorted data
- functools.reduce — fold a list into a value
- functools.partial — pre-fill function arguments
- functools.wraps — already seen in Day 11
- operator module as companion to functools

**Day 17 — pathlib + os + sys** `lib`
- pathlib.Path — OOP filesystem paths (modern approach)
- Path operations: exists, mkdir, read_text, write_text, glob
- os.environ — reading environment variables
- os.path for legacy code you'll encounter
- sys.argv — command-line arguments
- sys.exit, sys.path
- Java parallel: java.nio.file.Path

**Day 18 — datetime + json** `lib`
- datetime, date, time, timedelta
- Timezone-aware datetimes with timezone
- Formatting with strftime, parsing with strptime
- json.loads / json.dumps
- json.load / json.dump (file-based)
- Handling non-serializable types with custom encoder
- Java parallel: LocalDateTime, ObjectMapper

**Day 19 — requests + httpx** `lib`
- requests.get/post/put/delete
- Headers, query params, request body
- Response status codes, .json(), .text
- Error handling with raise_for_status()
- Sessions and connection reuse
- httpx as modern alternative — same API, supports async
- Java parallel: RestTemplate / WebClient

**Day 20 — Concurrency: threading + multiprocessing** `lib`
- The GIL — why Python threads don't run in true parallel for CPU work
- threading.Thread — basic thread creation
- ThreadPoolExecutor — managed thread pool
- multiprocessing.Process — true parallelism for CPU-bound work
- ProcessPoolExecutor
- When to use threads vs processes vs async (preview of Day 22)
- Java parallel: Thread, ExecutorService, ForkJoinPool

**Day 21 — Project: REST API Client** `project`
- Project: GitHub API Client
- What to build: A CLI tool that talks to the GitHub REST API. Fetch a user's repos, list open issues for a repo, and save results to a JSON report file.
- Inputs: GitHub username and repo name (via CLI args)
- Outputs: Formatted terminal output + report.json
- Covers: requests, json, sys.argv, pathlib, datetime, error handling
- Stretch goal: Add pagination support and rate limit handling

**Day 22 — asyncio Basics** `lib`
- Why async exists — I/O-bound concurrency without threads
- async def and await
- asyncio.run() — entry point
- Coroutines vs regular functions
- asyncio.sleep vs time.sleep
- Running multiple coroutines with asyncio.gather()
- Java parallel: CompletableFuture, async/await in modern Java

**Day 23 — asyncio Advanced** `lib`
- asyncio.Queue — producer/consumer pattern
- asyncio.timeout and asyncio.wait_for
- aiofiles — async file I/O
- Running blocking code in executor (run_in_executor)
- Building a small async web scraper with httpx async client
- Error handling in async code

**Day 24 — NumPy Basics** `lib`
- Why NumPy exists — vectorized ops, no loops
- ndarray vs Python list
- Creating arrays: np.array, np.zeros, np.ones, np.arange, np.linspace
- Array shape, dtype, reshape
- Indexing and slicing (including 2D)
- Vectorized arithmetic — operations on whole arrays at once
- Broadcasting rules
- Java parallel: no direct equivalent — closest is a typed array with math operations

**Day 25 — Pandas Basics** `lib`
- Series and DataFrame
- Creating DataFrames from dicts and CSV files (read_csv)
- Selecting columns and rows: df['col'], df.loc, df.iloc
- Filtering rows with boolean indexing
- groupby and aggregate functions
- merge and join (like SQL JOIN)
- Java parallel: think of DataFrame as a typed ResultSet you can manipulate

**Day 26 — Pandas Advanced** `lib`
- apply() with lambda — transform columns
- pivot_table
- Handling missing values: isna, fillna, dropna
- String operations on columns with .str accessor
- Sorting, ranking
- Exporting: to_csv, to_excel, to_json
- Reading from multiple file types

**Day 27 — pytest** `lib`
- Writing test functions (no class needed)
- assert statements — no assertEquals, just assert
- pytest fixtures — dependency injection for tests
- @pytest.mark.parametrize — data-driven tests
- Mocking with unittest.mock and pytest-mock
- Running tests, filtering, verbose output
- Java parallel: JUnit 5 + Mockito

**Day 28 — Project: Data Pipeline** `project`
- Project: Sales Data Pipeline
- What to build: Read a raw sales CSV, clean it (handle nulls, fix types, normalize columns), analyze it (total by region, top products, monthly trends), and output a summary CSV + printed report.
- Inputs: raw_sales.csv (provided as sample data in the page)
- Outputs: clean_sales.csv, summary report in terminal
- Covers: Pandas basics + advanced, NumPy, file I/O
- Stretch goal: Add a chart using matplotlib

---

### Phase 3 — Backend + AI (Week 5–6)

**Day 29 — FastAPI Basics** `lib`
- Why FastAPI over Flask — speed, type safety, auto docs
- Creating a FastAPI app
- Path operations: @app.get, @app.post, @app.put, @app.delete
- Path parameters and query parameters
- Request body with Pydantic models
- Automatic OpenAPI docs at /docs
- Running with uvicorn
- Java parallel: Spring Boot @RestController

**Day 30 — FastAPI Advanced** `lib`
- Dependency injection with Depends()
- Middleware
- Background tasks
- Error handling with HTTPException
- Response models and status codes
- Routers for splitting large apps (like Spring @Controller per domain)
- CORS middleware

**Day 31 — SQLAlchemy** `lib`
- Declarative models with Base and mapped_column
- Session and engine setup
- CRUD operations
- Relationships: one-to-many, many-to-many
- Querying with select()
- Alembic for migrations (like Flyway/Liquibase)
- Java parallel: JPA / Hibernate

**Day 32 — Pydantic** `lib`
- BaseModel — defining schemas
- Field validation and defaults
- Nested models
- Custom validators with @field_validator
- Settings management with BaseSettings (replaces .properties files)
- Model serialization: model_dump(), model_json()
- Java parallel: Bean Validation + @ConfigurationProperties

**Day 33 — Docker + Python** `lib`
- Writing a Dockerfile for a Python app
- Multi-stage builds to keep image small
- .dockerignore
- docker-compose with Postgres + FastAPI
- Environment variables in containers
- Health checks

**Day 34 — Environment + Config Patterns** `core`
- python-dotenv — loading .env files
- Environment-specific configs (dev/staging/prod)
- Pydantic BaseSettings for typed config
- 12-factor app principles applied to Python
- Secrets management patterns
- Java parallel: Spring profiles + @ConfigurationProperties

**Day 35 — Project: FastAPI + SQLAlchemy API** `project`
- Project: Task Manager REST API
- What to build: A full REST API for the task manager from Days 7/14. CRUD endpoints for tasks, persistent storage in SQLite via SQLAlchemy, Pydantic schemas for request/response, config via .env, tested with pytest + httpx test client.
- Inputs: HTTP requests
- Outputs: JSON responses, SQLite database
- Covers: FastAPI, SQLAlchemy, Pydantic, pytest, dotenv
- Stretch goal: Add user authentication with JWT

**Day 36 — LangChain Basics** `lib`
- What LangChain is and when to use it
- LLM wrappers (OpenAI, Ollama)
- Prompt templates
- Chains: LLMChain, sequential chains
- Output parsers
- Java parallel: no direct equivalent — think of it as a framework like Spring for AI workflows

**Day 37 — LangChain: Agents + Tools** `lib`
- What agents are — LLM deciding what tool to use
- Built-in tools: web search, calculator
- Creating custom tools with @tool
- ReAct agent pattern
- Agent memory
- Connecting to your local Ollama setup

**Day 38 — ChromaDB + Vector Stores** `lib`
- What embeddings are
- ChromaDB setup and collections
- Adding documents and querying by similarity
- Embedding functions (OpenAI, sentence-transformers)
- The RAG pattern: retrieve → augment → generate
- Persisting a ChromaDB collection to disk

**Day 39 — OpenAI SDK + Streaming** `lib`
- openai Python SDK setup
- chat.completions.create()
- Streaming responses with stream=True
- Function calling / tool use
- Managing token limits
- Structured outputs
- Async OpenAI client

**Day 40 — Celery + Redis** `lib`
- What Celery is — distributed task queue
- Setting up Celery with Redis broker
- Defining and calling tasks with @celery.task
- Delayed execution and scheduled tasks (beat)
- Task retries and error handling
- Monitoring with Flower
- Java parallel: @Async + Spring Batch / Quartz

**Day 41 — Logging + Observability** `lib`
- Python logging module — levels, handlers, formatters
- structlog for structured JSON logging
- Correlation IDs across requests
- Integrating with Datadog / OpenTelemetry
- FastAPI request logging middleware
- Java parallel: SLF4J + Logback + MDC

**Day 42 — Project: Mini RAG Chatbot** `project`
- Project: Document Q&A Chatbot
- What to build: A FastAPI service where you upload documents (text/PDF), they get chunked and stored in ChromaDB, and you can ask questions that get answered using RAG with OpenAI or Ollama.
- Inputs: Document upload endpoint, question endpoint
- Outputs: JSON answers with source references
- Covers: FastAPI, LangChain, ChromaDB, OpenAI SDK, async
- Stretch goal: Add conversation memory so follow-up questions work

---

### Phase 4 — Advanced (Week 7–8)

**Day 43 — Advanced OOP: ABCs + Protocols** `core`
- abc.ABC and @abstractmethod — enforced interfaces
- Why Python doesn't need interfaces like Java
- typing.Protocol — structural subtyping (duck typing + type safety)
- Difference between ABC (nominal) and Protocol (structural)
- Real-world use: define a Protocol for a repository pattern
- Java parallel: interface, abstract class

**Day 44 — Metaclasses + __slots__** `core`
- What metaclasses are — classes that create classes
- type as the default metaclass
- Writing a custom metaclass
- When metaclasses are actually useful (ORMs, frameworks)
- __slots__ — restricting instance attributes for memory savings
- Benchmarking __slots__ vs regular class

**Day 45 — Python Internals** `core`
- The GIL deep dive — why it exists, CPython specifics
- Reference counting and garbage collection
- gc module — detecting cycles, manual collection
- Memory model — mutable vs immutable objects
- id() and object identity vs equality
- Python bytecode with dis module

**Day 46 — Performance + Profiling** `core`
- cProfile — function-level profiling
- line_profiler — line-by-line profiling
- memory_profiler — memory usage per line
- timeit for micro-benchmarks
- Common Python performance pitfalls
- When to reach for NumPy, C extensions, or PyPy

**Day 47 — Packaging + CLI Tools** `core`
- pyproject.toml — modern Python packaging
- setuptools and build
- Creating an installable package with pip install -e .
- Click framework for CLI apps (better than argparse)
- Entry points — making your package a CLI command
- Publishing to PyPI (overview)

**Day 48 — Design Patterns in Python** `core`
- Singleton — using modules or metaclass
- Factory — using functions, not static factory methods
- Strategy — using first-class functions instead of interfaces
- Observer — using simple callbacks or libraries
- Decorator pattern vs Python decorator syntax
- How Python idioms replace verbose Java patterns

**Day 49 — Project: Package a Library** `project`
- Project: Package the Task Manager as a reusable library
- What to build: Take the Task Manager from Day 35, extract the core logic into a proper Python package with pyproject.toml, CLI entry point via Click, type hints throughout, full pytest suite, and a README.
- Inputs: Existing Day 35 codebase
- Outputs: Installable Python package
- Stretch goal: Publish to TestPyPI

**Day 50 — Advanced Testing** `lib`
- pytest-asyncio — testing async code
- httpx AsyncClient as FastAPI test client
- Testcontainers — spinning up real Postgres/Redis in tests
- Coverage reports with pytest-cov
- Factories and fixtures for complex test data
- Testing Celery tasks

**Day 51 — CI/CD for Python** `core`
- GitHub Actions workflow for Python
- Steps: install deps, lint with ruff, type check with mypy, run pytest
- Coverage reporting in CI
- Building and pushing Docker image
- Environment secrets in GitHub Actions
- Java parallel: Maven/Gradle + Jenkins/GitHub Actions

**Day 52 — Scripting + Automation** `lib`
- subprocess — running shell commands from Python
- shutil — file operations (copy, move, archive)
- schedule — run functions on a timer
- Automating file processing workflows
- Sending emails with smtplib
- Real estate use case: automate report generation or data collection

**Day 53 — Web Scraping** `lib`
- requests + BeautifulSoup — static page scraping
- Parsing HTML: find, find_all, CSS selectors
- Handling pagination
- Playwright for dynamic/JS-rendered pages
- Rate limiting and polite scraping
- robots.txt and ethical considerations

**Day 54 — Intro to ML Stack** `lib`
- scikit-learn overview
- train/test split
- A simple classifier: RandomForestClassifier
- Pipeline — chaining preprocessing + model
- Model evaluation: accuracy, confusion matrix
- Saving and loading models with joblib
- Where this fits in the broader ML landscape (pandas → sklearn → torch/tf)

**Day 55 — Review + Weak Spots** `core`
- Revisit the concepts that felt least solid
- Read and understand a real Python codebase on GitHub (suggestions provided)
- Pythonic code checklist — are you writing Python or Java-in-Python?
- Common Python anti-patterns to avoid
- What to learn next based on your direction (backend / AI / data)

**Day 56 — Capstone Project** `project`
- Project: Your choice of two options
- Option A — Real Estate Automation: A FastAPI service that scrapes property listings, stores them in a DB, sends email digests, and exposes a query API. Uses: FastAPI, SQLAlchemy, BeautifulSoup, Celery, smtplib.
- Option B — AI Dev Tool: A LangChain + FastAPI service where you can chat with your codebase. Index .py files into ChromaDB, ask questions, get answers with file + line references. Uses: FastAPI, LangChain, ChromaDB, OpenAI/Ollama.
- Covers: everything from the 56-day plan
- Stretch goal: Deploy to a VPS with Docker + nginx

---

## Implementation Notes (decisions made while building)

### Progress
- All 56 days are fully built and unlocked in index.html
- The guide is complete.

### Known Issues
- Days 1–7 have wrap-up section rendering issues (wrong structure). Not yet fixed — deferred to a later session.
- All days 8–32 use the correct three-part wrap-up structure.

### Wrap-up Section — Correct Structure
The wrap-up must use exactly these three CSS classes in order:
```html
<ul class="takeaway-list">...</ul>   <!-- 3–5 bullet takeaways -->
<div class="practice-box">...</div>  <!-- what to practice -->
<div class="next-teaser">...</div>   <!-- teaser for next day -->
```

### Phase Badge Colors
Each phase uses a different hero/badge color scheme:
- Phase 1 (Days 1–14): teal — background `#0d1a1a`, badge text `#40e0b0`
- Phase 2 (Days 15–28): blue — background `#1a1a2e`, badge text `#7090ff`
- Phase 3 (Days 29–42): orange — background `#2a1a0f`, badge text `#ff6b35`
- Phase 4 (Days 43–56): purple — background `#1a0d2e`, badge text `#b070ff` (not yet confirmed, use as default)

### Project Day Styling
Project days (7, 14, 21, 28, 35, 42, 49, 56) use:
- Orange day badge: `background: #ff6b35`
- `<div class="spec-box">` for project spec (inputs/outputs/covers)
- `<div class="stretch-box">` for stretch goals
- No `plan-box` — the spec-box replaces it

### Custom CSS Classes Added During Build
These classes were added to individual day pages and should be reused consistently:
- `.dunder-table` — reference table for dunder methods (day9)
- `.diagram-box` — visual diagram box (day10)
- `.decision-table` — comparison table (e.g., threads vs processes) (day20)
- `.shell-block` — terminal/shell command blocks (day27)

### Shared CSS File
All day pages now link to a single `styles.css` in the project root. Do NOT embed the full CSS inline in new day pages.

Each day page's `<head>` should look like:
```html
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet" />
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/github-dark.min.css" />
<link rel="stylesheet" href="styles.css" />
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/highlight.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/languages/python.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/languages/java.min.js"></script>
<style>
  /* Phase N — Label: color badge */
  .phase-badge { background: ...; color: ...; border: ...; }
  /* Project days only: */
  .day-badge { background: #ff6b35; color: #fff; }
</style>
```

The only things in the per-file `<style>` block are:
- `.phase-badge` color override (differs per phase)
- `.day-badge` override for project days (orange background)

If you add a new reusable CSS class, add it to `styles.css` — not inline in the day file.

### takeaway-list li — Do NOT use display:flex
The correct `.takeaway-list li` rule uses `position: relative` + `padding-left`, NOT `display: flex`. The flex approach breaks inline code and long wrapping text inside list items.

Correct rule (already in styles.css):
```css
.takeaway-list li { position: relative; padding-left: 20px; font-size: 0.95rem; color: #c0c0c0; line-height: 1.6; }
.takeaway-list li::before { content: '◆'; color: #f0e040; font-size: 0.6rem; position: absolute; left: 0; top: 0.45em; }
```

### Bulk HTML edits — use Python, not sed
For bulk changes across many HTML files, use a Python script via Bash tool. macOS `sed` is unreliable for multi-pattern or multi-file edits. Python's `str.replace()` and `re.sub()` are safe and predictable.

### Unlocking Cards in index.html
**Use the Edit tool directly — do NOT use bash `sed` on macOS.**
macOS `sed -i ''` with multiple patterns in a single command silently fails.
Each card unlock is a separate Edit call: remove `card-locked` from the `<a>` tag's class list.

### Done/Not-Done State
Stored in `localStorage` keyed by day number. Cleared if the user clears browser cache — this is expected and acceptable behavior.

---

## Java Framing Cheatsheet

| Python | Java Equivalent |
|--------|----------------|
| Dynamic typing | No explicit types like `String x` |
| list | ArrayList |
| dict | HashMap |
| tuple | Immutable List / Record |
| set | HashSet |
| @dataclass | POJO / Lombok @Data / Java Record |
| @property | getters/setters |
| yield / generator | Iterator pattern |
| decorator | AOP / @Around advice |
| with statement | try-with-resources |
| asyncio | CompletableFuture |
| threading | java.util.concurrent |
| pytest | JUnit 5 + Mockito |
| FastAPI | Spring Boot @RestController |
| SQLAlchemy | JPA / Hibernate |
| Pydantic | Bean Validation + @ConfigurationProperties |
| Celery | @Async + Quartz |
| __slots__ | memory optimization hint |
| Protocol | structural interface (no `implements`) |
| abc.ABC | abstract class |
| click | picocli |
| structlog | SLF4J + Logback + MDC |

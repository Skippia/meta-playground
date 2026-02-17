# meta-playground

Aggregated playground: all my learning repos as git submodules — algorithms, Node.js, TypeScript, DevOps, databases, patterns & more.

> [Версия на русском](./README.md)

## Repos

### Core Node.js

| # | Repo | Language | Description | Use cases |
|---|------|----------|-------------|-----------|
| 1 | [nodejs-playground](https://github.com/Skippia/nodejs-playground) | JavaScript | • Node.js core modules — path, os, process, url, events, stream (pipe + backpressure), fs (custom promisify)<br>• cluster (multi-core forking)<br>• HTTP server | CLI tools, process management, framework-free HTTP servers |
| 2 | [streams-playground](https://github.com/Skippia/streams-playground) | TypeScript | • 19 modules: all stream types, pipe vs pipeline, backpressure, async generators, AbortController, Web Streams API<br>• CSV-to-NDJSON ETL, TCP chat, SQLite pagination<br>• child_process/worker_threads parallelism<br>• Streaming internet radio with SoX<br>• Observer/Pub-Sub EventEmitter | ETL pipelines, large file processing, media streaming |
| 3 | [asynchronous-nodejs-playground](https://github.com/Skippia/asynchronous-nodejs-playground) | TypeScript | • Event loop internals, libuv threadpool, promise ordering<br>• Worker threads/workerpools, clustering + PM2, actors model<br>• Sequential vs concurrent vs parallel execution<br>• Async debugger, baseline perf benchmarks | Throughput optimization, event loop blocking diagnostics, PM2/cluster scaling |
| 4 | [parallel-programming-playground](https://github.com/Skippia/parallel-programming-playground) | TypeScript | • Mutex (4 impls + deadlock/livelock), Semaphore (binary/counting + atomics), Atomics benchmarks<br>• WorkerPool, async primitives (async-mutex, async-semaphore, barrier, bounded-channel, rate-limiter, rw-lock)<br>• Distributed Redis lock, lock-free CAS counter | CPU-intensive tasks (images/video), rate limiting, connection pools, distributed locks |
| 5 | [V8-sandboxes-playground](https://github.com/Skippia/V8-sandboxes-playground) | JavaScript | • Isolated sandboxes via Node.js `vm` module<br>• Dual implementation: safeRequire (CJS) and safeImport (ESM)<br>• Whitelisted module loading, proxied globals, sandboxed fs access | Plugin systems, user script execution, multi-tenant isolation |

### TypeScript & FP

| # | Repo | Language | Description | Use cases |
|---|------|----------|-------------|-----------|
| 6 | [typescript-playground](https://github.com/Skippia/typescript-playground) | TypeScript | • 42 type-level challenges (all utility types from scratch), type-level arithmetic, UnionToIntersection<br>• Recursive types, template literals, covariance/contravariance<br>• Distributive conditionals, type narrowing edge cases<br>• misc-types (DeepReadonly, Invert, NoInfer) + 7 edge-case behavior files | Type-safe libraries, SDK design, complex generic APIs |
| 7 | [fp-playground](https://github.com/Skippia/fp-playground) | TypeScript | • fp-ts/ramda/monocle-ts — HOF, currying, composition, tagless final, type-driven dev<br>• Category theory (functors, applicatives, monads, Kleisli)<br>• All monadic types (Option, Either, Task, Reader, State, Writer)<br>• Algebraic structures, optics, Game of Life | Error-handling pipelines, data transformations, DI via Reader, side-effect management |
| 8 | [legacy-decorators-playground](https://github.com/Skippia/legacy-decorators-playground) | TypeScript | • Legacy `experimentalDecorators` + reflect-metadata<br>• Method/class decorators, factories, execution order, double-wrapping<br>• design:type/paramtypes/returntype emission | NestJS/Angular DI, ORM decorators, validation, AOP |

### Databases & Messaging

| # | Repo | Language | Description | Use cases |
|---|------|----------|-------------|-----------|
| 9 | [postgres-playground](https://github.com/Skippia/postgres-playground) | TypeScript / SQL | • Ranking, CTEs, recursive CTEs, functions/procedures, window functions, JSONB<br>• Materialized views, triggers, pg-cron, full-text/fuzzy search, domain types<br>• Indexes (exclusion, composite, partial)<br>• Replication, partitioning, PgBouncer, backup/restore, SSL, migrations<br>• Advisory locks, isolation levels<br>• Correlated subqueries, LISTEN/NOTIFY pub-sub, pg_ivm incremental materialized views | Complex analytics, full-text search, sharding/replication, job scheduling |
| 10 | [redis-playground](https://github.com/Skippia/redis-playground) | TypeScript | • 3-project monorepo: NestJS + ioredis (session auth, Redlock, WATCH/transaction, optimistic locking, ELK)<br>• SvelteKit auction (RediSearch, HyperLogLog, Lua scripts, Keygrip cookies)<br>• Vue 3 search UI with MSW | Sessions, distributed locks, real-time search, caching, auctions |
| 11 | [rabbitmq-playground](https://github.com/Skippia/rabbitmq-playground) | TypeScript | • Topic exchange, publisher confirms, RPC, alternate/dead letter exchanges, consistent hash<br>• 3 retry strategies (DLX+TTL, exponential backoff, delayed_message_exchange plugin)<br>• 3 publisher confirm strategies (sync/batch/async), poison message handling<br>• NestJS microservices + MongoDB, 3-node cluster with HAProxy + Shovels, clinic.js benchmarks | Microservice communication, retry/DLQ strategies, event-driven architecture |

### Patterns & Architecture

| # | Repo | Language | Description | Use cases |
|---|------|----------|-------------|-----------|
| 12 | [patterns-playground](https://github.com/Skippia/patterns-playground) | TypeScript | • GoF patterns (8 behavioral, 1 creational, 3 structural)<br>• DDD Specification, Factorify pattern<br>• Decorators, memoization, mixins, object pool, thenable, Revealing Constructor | Clean architecture, plugin systems, state machines |
| 13 | [event-sourcing-playground](https://github.com/Skippia/event-sourcing-playground) | TypeScript | • 5 progressive examples (maritime shipping domain): basic apply/replay, event reversal (Memento), external caching (Decorator/QueryLog)<br>• Retroactive replacement/rejection with rewind, side-effect buffering with differential cancel/re-notify<br>• Bonus: event-based CRUD cart with MongoDB + Express | Audit trails, undo/redo, temporal queries, finance/logistics |
| 14 | [vertical-slice-architecture-playground](https://github.com/Skippia/vertical-slice-architecture-playground) | TypeScript | • Two NestJS + CQRS implementations: basic (Drizzle + SQLite) and production (multi-app monorepo, PostgreSQL, RabbitMQ)<br>• Winston logger + trace ID, Joi validation, Docker Compose<br>• Circular dependency detection via madge<br>• 30 E2E tests per version | Feature-based code organization, CQRS in NestJS, monorepo |

### DevOps & Infra

| # | Repo | Language | Description | Use cases |
|---|------|----------|-------------|-----------|
| 15 | [devops-playground](https://github.com/Skippia/devops-playground) | YAML / Dockerfile | • Docker Compose multi-stack (NestJS+RabbitMQ, Laravel+PHP-FPM, Vue/React+Express+MySQL/MongoDB)<br>• Swiggy microservices (Nginx + PostgreSQL), pgAdmin<br>• K8s manifests (local + AWS EKS, EFS, Secrets, ConfigMaps)<br>• GitHub Actions pipelines, Nginx configs | CI/CD pipelines, containerization, K8s orchestration, reverse proxy |
| 16 | [SSR-cache-demo](https://github.com/Skippia/SSR-cache-demo) | TypeScript | • 3 Nuxt 3 SSR caching strategies: routeRules SWR (in-memory TTL), ETag + stale-while-revalidate (browser-side, MD5, 304)<br>• Server middleware + external storage (TTL-based render interception) | SSR performance optimization, CDN caching, SEO |

### Protocols & Communication

| # | Repo | Language | Description | Use cases |
|---|------|----------|-------------|-----------|
| 17 | [gRPC-playground](https://github.com/Skippia/gRPC-playground) | TypeScript | • Eliza service from .proto (buf + protoc-gen-ts)<br>• Server/client interceptors, health checks, server reflection, error handling<br>• Streaming types (server/bidi), retry/deadline policies | Microservice APIs, high-performance RPC, data streaming |
| 18 | [realtime-playground](https://github.com/Skippia/realtime-playground) | JavaScript / TypeScript | • 7 mini-chat implementations: short polling (RAF), long polling (EventEmitter), SSE, HTTP/2 streams<br>• Basic WebSocket, WebSocket + Redis pub/sub + HAProxy scaling<br>• Collaborative spreadsheet (Vue 3 + Pinia) | Chats, live dashboards, collaborative editing, notifications |

### Misc

| # | Repo | Language | Description | Use cases |
|---|------|----------|-------------|-----------|
| 19 | [miscellaneous-playground](https://github.com/Skippia/miscellaneous-playground) | JavaScript | • 7 standalone examples: undefined shadowing, short-circuit side effects, autoboxing/prototype pollution<br>• Comma operator, async stack trace loss, Error non-enumerable serialization<br>• Async race conditions | Code review, security audits (prototype pollution), async debugging |
| 20 | [algorithms-playground](https://github.com/Skippia/algorithms-playground) | JavaScript / TypeScript | • Sorting (bubble, insert, merge, quick, selection)<br>• Search (binary, BFS, Dijkstra), data structures (binary trees, hash table, linked list)<br>• Puzzles: Fibonacci memoization, palindrome, Caesar cipher, sieve of Eratosthenes, FizzBuzz, reverse words, two sum, harmless ransom note, mean/median/mode, max profit, island perimeter | Coding interviews, performance optimization, custom data structures |
| 21 | [automapper-demo](https://github.com/Skippia/automapper-demo) | TypeScript | • @automapper library demo: classic (decorator-based with @automapper/classes) and auto (plain objects with @automapper/pojos)<br>• User entity-to-DTO mapping | DTO mapping in layered architecture, API response transformation |

## Setup

```bash
# Clone with all submodules
git clone --recurse-submodules git@github.com:Skippia/meta-playground.git

# Or init submodules after clone
git submodule update --init --recursive
```

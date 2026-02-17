# meta-playground

Aggregated playground: all my learning repos as git submodules — algorithms, Node.js, TypeScript, DevOps, databases, patterns & more.

## Repos

### Core Node.js

| Repo | Language | Description |
|------|----------|-------------|
| [nodejs-playground](./nodejs-playground) | JavaScript | Node.js core modules — path, os, process, url, events, stream (pipe + backpressure), fs (custom promisify), cluster (multi-core forking), HTTP server |
| [streams-playground](./streams-playground) | TypeScript | 18 modules: all stream types, pipe vs pipeline, backpressure, async generators, AbortController, Web Streams API, CSV-to-NDJSON ETL, TCP chat, SQLite pagination, child_process/worker_threads parallelism, streaming internet radio with SoX |
| [asynchronous-nodejs-playground](./asynchronous-nodejs-playground) | TypeScript | Event loop internals, libuv threadpool, promise ordering, worker threads/workerpools, clustering + PM2, actors model |
| [parallel-programming-playground](./parallel-programming-playground) | TypeScript | Mutex (4 impls + deadlock/livelock), Semaphore (binary/counting + atomics), Atomics benchmarks, WorkerPool, async primitives (async-mutex, async-semaphore, barrier, bounded-channel, rate-limiter, rw-lock), distributed Redis lock, lock-free CAS counter |
| [V8-sandboxes-playground](./V8-sandboxes-playground) | JavaScript | Isolated sandboxes via Node.js `vm` module — safeRequire (CJS) / safeImport (ESM), whitelisted module loading, proxied globals, sandboxed fs access |

### TypeScript & FP

| Repo | Language | Description |
|------|----------|-------------|
| [typescript-playground](./typescript-playground) | TypeScript | 42 type-level challenges (all utility types from scratch), type-level arithmetic, UnionToIntersection, recursive types, template literals, covariance/contravariance, distributive conditionals, type narrowing edge cases |
| [fp-playground](./fp-playground) | TypeScript | fp-ts/ramda/monocle-ts — HOF, currying, composition, tagless final, type-driven dev; category theory (functors, applicatives, monads, Kleisli); all monadic types (Option, Either, Task, Reader, State, Writer); algebraic structures; optics; Game of Life |
| [legacy-decorators-playground](./legacy-decorators-playground) | TypeScript | Legacy `experimentalDecorators` + reflect-metadata: method/class decorators, factories, execution order, double-wrapping, design:type/paramtypes/returntype emission |

### Databases & Messaging

| Repo | Language | Description |
|------|----------|-------------|
| [postgres-playground](./postgres-playground) | TypeScript / SQL | Ranking, CTEs, recursive CTEs, functions/procedures, window functions, JSONB, materialized views, triggers, pg-cron, full-text/fuzzy search, domain types; indexes (exclusion, composite, partial); replication, partitioning, PgBouncer, backup/restore, SSL, migrations; advisory locks, isolation levels |
| [redis-playground](./redis-playground) | TypeScript | 3-project monorepo: NestJS + ioredis (session auth, Redlock, WATCH/transaction, optimistic locking, ELK); SvelteKit auction (RediSearch, HyperLogLog, Lua scripts, Keygrip cookies); Vue 3 search UI with MSW |
| [rabbitmq-playground](./rabbitmq-playground) | TypeScript | Topic exchange, publisher confirms, RPC, alternate/dead letter exchanges, consistent hash, 3 retry strategies (DLX+TTL, exponential backoff, delayed_message_exchange plugin), NestJS microservices + MongoDB, 3-node cluster with HAProxy + Shovels, clinic.js benchmarks |

### Patterns & Architecture

| Repo | Language | Description |
|------|----------|-------------|
| [patterns-playground](./patterns-playground) | TypeScript | GoF patterns (8 behavioral, 1 creational, 3 structural), DDD Specification, plus decorators, memoization, mixins, object pool, thenable, Revealing Constructor |
| [event-sourcing-playground](./event-sourcing-playground) | TypeScript | 5 progressive examples (maritime shipping domain): basic apply/replay, event reversal (Memento), external caching (Decorator/QueryLog), retroactive replacement/rejection with rewind, side-effect buffering with differential cancel/re-notify; bonus: event-based CRUD cart with MongoDB + Express |
| [vertical-slice-architecture-playground](./vertical-slice-architecture-playground) | TypeScript | Two NestJS + CQRS implementations: basic (Drizzle + SQLite) and production (multi-app monorepo, PostgreSQL, RabbitMQ, Pino, Joi, Docker Compose, madge circular dependency detection) |

### DevOps & Infra

| Repo | Language | Description |
|------|----------|-------------|
| [devops-playground](./devops-playground) | YAML / Dockerfile | Docker Compose multi-stack (NestJS+RabbitMQ, Laravel+PHP-FPM, Vue/React+Express+MySQL/MongoDB), K8s manifests (local + AWS EKS, EFS, Secrets, ConfigMaps), GitHub Actions pipelines, Nginx configs |
| [SSR-cache-demo](./SSR-cache-demo) | TypeScript | 3 Nuxt 3 SSR caching strategies: routeRules SWR (in-memory TTL), ETag + stale-while-revalidate (browser-side, MD5, 304), server middleware + external storage (TTL-based render interception) |

### Protocols & Communication

| Repo | Language | Description |
|------|----------|-------------|
| [gRPC-playground](./gRPC-playground) | TypeScript | Eliza service from .proto (buf + protoc-gen-ts), server/client interceptors, health checks, server reflection, error handling, Swagger/OpenAPI generation |
| [realtime-playground](./realtime-playground) | JavaScript / TypeScript | 7 mini-chat implementations: short polling (RAF), long polling (EventEmitter), SSE, HTTP/2 streams, basic WebSocket, WebSocket + Redis pub/sub + HAProxy scaling, collaborative spreadsheet (Vue 3 + Pinia) |

### Misc

| Repo | Language | Description |
|------|----------|-------------|
| [miscellaneous-playground](./miscellaneous-playground) | JavaScript | 10 standalone examples: undefined shadowing, short-circuit side effects, autoboxing/prototype pollution, comma operator, async stack trace loss, Error non-enumerable serialization, async race conditions |
| [algorithms-playground](./algorithms-playground) | JavaScript / TypeScript | Sorting (bubble, insert, merge, quick), search (binary, BFS, Dijkstra), data structures (binary trees, hash table, linked list), puzzles (Fibonacci memoization, palindrome, Caesar cipher, sieve of Eratosthenes) |
| [automapper-demo](./automapper-demo) | TypeScript | @automapper library demo: classic (decorator-based with @automapper/classes) and auto (plain objects with @automapper/pojos), User entity-to-DTO mapping |

## Setup

```bash
# Clone with all submodules
git clone --recurse-submodules git@github.com:Skippia/meta-playground.git

# Or init submodules after clone
git submodule update --init --recursive
```

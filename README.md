# meta-playground

Aggregated playground: all my learning repos as git submodules — algorithms, Node.js, TypeScript, DevOps, databases, patterns & more.

## Repos

### Core Node.js

| Repo | Language | Description |
|------|----------|-------------|
| [nodejs-playground](./nodejs-playground) | TypeScript | Core Node.js concepts and internals |
| [streams-playground](./streams-playground) | TypeScript | Node.js streams deep dive |
| [asynchronous-nodejs-playground](./asynchronous-nodejs-playground) | TypeScript | Async patterns in Node.js (event loop, libuv, promises) |
| [parallel-programming-playground](./parallel-programming-playground) | TypeScript | Worker threads, sync primitives, lock-free structures |
| [V8-sandboxes-playground](./V8-sandboxes-playground) | TypeScript | V8 engine sandboxing and isolation |

### TypeScript & FP

| Repo | Language | Description |
|------|----------|-------------|
| [typescript-playground](./typescript-playground) | TypeScript | Advanced TypeScript type-level programming |
| [fp-playground](./fp-playground) | TypeScript | Functional programming patterns and abstractions |
| [legacy-decorators-playground](./legacy-decorators-playground) | TypeScript | TypeScript legacy decorators exploration |

### Databases & Messaging

| Repo | Language | Description |
|------|----------|-------------|
| [postgres-playground](./postgres-playground) | SQL / TypeScript | PostgreSQL features, queries, and integration |
| [redis-playground](./redis-playground) | TypeScript | Redis data structures and use cases |
| [rabbitmq-playground](./rabbitmq-playground) | TypeScript | RabbitMQ messaging patterns |

### Patterns & Architecture

| Repo | Language | Description |
|------|----------|-------------|
| [patterns-playground](./patterns-playground) | TypeScript | Design patterns implementations |
| [event-sourcing-playground](./event-sourcing-playground) | TypeScript | Event sourcing and CQRS |
| [vertical-slice-architecture-playground](./vertical-slice-architecture-playground) | TypeScript | Vertical slice architecture approach |

### DevOps & Infra

| Repo | Language | Description |
|------|----------|-------------|
| [devops-playground](./devops-playground) | YAML / Shell | Docker, CI/CD, infrastructure as code |
| [SSR-cache-demo](./SSR-cache-demo) | TypeScript | SSR caching strategies demo |

### Protocols & Communication

| Repo | Language | Description |
|------|----------|-------------|
| [gRPC-playground](./gRPC-playground) | TypeScript | gRPC services and protobuf |
| [realtime-playground](./realtime-playground) | TypeScript | WebSockets and real-time communication |

### Misc

| Repo | Language | Description |
|------|----------|-------------|
| [miscellaneous-playground](./miscellaneous-playground) | TypeScript | Various experiments and snippets |
| [algorithms-playground](./algorithms-playground) | TypeScript | Algorithms and data structures |
| [automapper-demo](./automapper-demo) | TypeScript | AutoMapper library demo |

## Setup

```bash
# Clone with all submodules
git clone --recurse-submodules git@github.com:Skippia/meta-playground.git

# Or init submodules after clone
git submodule update --init --recursive
```

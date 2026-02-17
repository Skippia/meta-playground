# meta-playground

Агрегированный playground: все мои учебные репозитории как git-подмодули — алгоритмы, Node.js, TypeScript, DevOps, базы данных, паттерны и многое другое.

> [English version](./README.md)

## Репозитории

### Ядро Node.js

| Репозиторий | Язык | Описание |
|-------------|------|----------|
| [nodejs-playground](./nodejs-playground) | JavaScript | Ключевые модули Node.js — path, os, process, url, events, stream (pipe + backpressure), fs (кастомный promisify), cluster (форкинг на несколько ядер), HTTP-сервер |
| [streams-playground](./streams-playground) | TypeScript | 18 модулей: все типы стримов, pipe vs pipeline, backpressure, async-генераторы, AbortController, Web Streams API, ETL CSV-to-NDJSON, TCP-чат, пагинация SQLite, параллелизм через child_process/worker_threads, стриминговое интернет-радио с SoX |
| [asynchronous-nodejs-playground](./asynchronous-nodejs-playground) | TypeScript | Внутреннее устройство event loop, libuv threadpool, порядок выполнения промисов, worker threads/workerpools, кластеризация + PM2, модель акторов |
| [parallel-programming-playground](./parallel-programming-playground) | TypeScript | Mutex (4 реализации + deadlock/livelock), Semaphore (бинарный/счётный + atomics), бенчмарки Atomics, WorkerPool, async-примитивы (async-mutex, async-semaphore, barrier, bounded-channel, rate-limiter, rw-lock), распределённая блокировка Redis, lock-free CAS-счётчик |
| [V8-sandboxes-playground](./V8-sandboxes-playground) | JavaScript | Изолированные песочницы через модуль `vm` Node.js — safeRequire (CJS) / safeImport (ESM), загрузка модулей по белому списку, проксированные глобальные объекты, песочница для доступа к fs |

### TypeScript и ФП

| Репозиторий | Язык | Описание |
|-------------|------|----------|
| [typescript-playground](./typescript-playground) | TypeScript | 42 задачи на уровне типов (все utility-типы с нуля), арифметика на уровне типов, UnionToIntersection, рекурсивные типы, template literals, ковариантность/контравариантность, дистрибутивные условные типы, граничные случаи сужения типов |
| [fp-playground](./fp-playground) | TypeScript | fp-ts/ramda/monocle-ts — HOF, каррирование, композиция, tagless final, type-driven разработка; теория категорий (функторы, аппликативы, монады, Kleisli); все монадические типы (Option, Either, Task, Reader, State, Writer); алгебраические структуры; оптики; Game of Life |
| [legacy-decorators-playground](./legacy-decorators-playground) | TypeScript | Legacy `experimentalDecorators` + reflect-metadata: декораторы методов/классов, фабрики, порядок выполнения, двойная обёртка, эмиссия design:type/paramtypes/returntype |

### Базы данных и очереди сообщений

| Репозиторий | Язык | Описание |
|-------------|------|----------|
| [postgres-playground](./postgres-playground) | TypeScript / SQL | Ранжирование, CTE, рекурсивные CTE, функции/процедуры, оконные функции, JSONB, материализованные представления, триггеры, pg-cron, полнотекстовый/нечёткий поиск, доменные типы; индексы (исключающие, составные, частичные); репликация, партиционирование, PgBouncer, бэкап/восстановление, SSL, миграции; рекомендательные блокировки, уровни изоляции |
| [redis-playground](./redis-playground) | TypeScript | Монорепо из 3 проектов: NestJS + ioredis (сессионная авторизация, Redlock, WATCH/транзакции, оптимистичная блокировка, ELK); SvelteKit аукцион (RediSearch, HyperLogLog, Lua-скрипты, Keygrip cookies); Vue 3 поисковый UI с MSW |
| [rabbitmq-playground](./rabbitmq-playground) | TypeScript | Topic exchange, publisher confirms, RPC, alternate/dead letter exchanges, consistent hash, 3 стратегии повторов (DLX+TTL, экспоненциальный backoff, плагин delayed_message_exchange), NestJS микросервисы + MongoDB, кластер из 3 нод с HAProxy + Shovels, бенчмарки clinic.js |

### Паттерны и архитектура

| Репозиторий | Язык | Описание |
|-------------|------|----------|
| [patterns-playground](./patterns-playground) | TypeScript | GoF-паттерны (8 поведенческих, 1 порождающий, 3 структурных), DDD Specification, а также декораторы, мемоизация, миксины, пул объектов, thenable, Revealing Constructor |
| [event-sourcing-playground](./event-sourcing-playground) | TypeScript | 5 последовательных примеров (домен морских перевозок): базовый apply/replay, реверсия событий (Memento), внешнее кэширование (Decorator/QueryLog), ретроактивная замена/отклонение с перемоткой, буферизация сайд-эффектов с дифференциальной отменой/переотправкой; бонус: event-based CRUD корзины с MongoDB + Express |
| [vertical-slice-architecture-playground](./vertical-slice-architecture-playground) | TypeScript | Две реализации NestJS + CQRS: базовая (Drizzle + SQLite) и продакшн (монорепо из нескольких приложений, PostgreSQL, RabbitMQ, Pino, Joi, Docker Compose, обнаружение циклических зависимостей через madge) |

### DevOps и инфраструктура

| Репозиторий | Язык | Описание |
|-------------|------|----------|
| [devops-playground](./devops-playground) | YAML / Dockerfile | Docker Compose мультистек (NestJS+RabbitMQ, Laravel+PHP-FPM, Vue/React+Express+MySQL/MongoDB), K8s-манифесты (локальные + AWS EKS, EFS, Secrets, ConfigMaps), пайплайны GitHub Actions, конфиги Nginx |
| [SSR-cache-demo](./SSR-cache-demo) | TypeScript | 3 стратегии кэширования SSR в Nuxt 3: routeRules SWR (in-memory TTL), ETag + stale-while-revalidate (браузерное, MD5, 304), серверная middleware + внешнее хранилище (перехват рендера на основе TTL) |

### Протоколы и коммуникация

| Репозиторий | Язык | Описание |
|-------------|------|----------|
| [gRPC-playground](./gRPC-playground) | TypeScript | Eliza-сервис из .proto (buf + protoc-gen-ts), серверные/клиентские интерцепторы, health checks, серверная рефлексия, обработка ошибок, генерация Swagger/OpenAPI |
| [realtime-playground](./realtime-playground) | JavaScript / TypeScript | 7 мини-чатов: short polling (RAF), long polling (EventEmitter), SSE, HTTP/2 streams, базовый WebSocket, WebSocket + Redis pub/sub + масштабирование через HAProxy, совместная таблица (Vue 3 + Pinia) |

### Разное

| Репозиторий | Язык | Описание |
|-------------|------|----------|
| [miscellaneous-playground](./miscellaneous-playground) | JavaScript | 10 отдельных примеров: shadowing undefined, short-circuit side effects, autoboxing/prototype pollution, оператор запятая, потеря async stack trace, неэнумерабельная сериализация Error, async race conditions |
| [algorithms-playground](./algorithms-playground) | JavaScript / TypeScript | Сортировки (пузырьковая, вставками, слиянием, быстрая), поиск (бинарный, BFS, Dijkstra), структуры данных (бинарные деревья, хэш-таблица, связный список), задачи (мемоизация Фибоначчи, палиндром, шифр Цезаря, решето Эратосфена) |
| [automapper-demo](./automapper-demo) | TypeScript | Демо библиотеки @automapper: классический подход (на декораторах через @automapper/classes) и автоматический (plain objects через @automapper/pojos), маппинг User entity в DTO |

## Установка

```bash
# Клонировать со всеми подмодулями
git clone --recurse-submodules git@github.com:Skippia/meta-playground.git

# Или инициализировать подмодули после клонирования
git submodule update --init --recursive
```

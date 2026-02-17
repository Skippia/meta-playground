# meta-playground

Агрегированный playground: все мои учебные репозитории как git-подмодули — алгоритмы, Node.js, TypeScript, DevOps, базы данных, паттерны и многое другое.

> [English version](./README.en.md)

## Репозитории

### Ядро Node.js

| # | Репозиторий | Язык | Описание | Варианты использования |
|---|-------------|------|----------|------------------------|
| 1 | [nodejs-playground](https://github.com/Skippia/nodejs-playground) | JavaScript | • Ключевые модули Node.js — path, os, process, url, events, stream (pipe + backpressure), fs (кастомный promisify)<br>• cluster (форкинг на несколько ядер)<br>• HTTP-сервер | CLI-утилиты, процесс-менеджмент, HTTP-серверы без фреймворков |
| 2 | [streams-playground](https://github.com/Skippia/streams-playground) | TypeScript | • 19 модулей: все типы стримов, pipe vs pipeline, backpressure, async-генераторы, AbortController, Web Streams API<br>• ETL CSV-to-NDJSON, TCP-чат, пагинация SQLite<br>• Параллелизм через child_process/worker_threads<br>• Стриминговое интернет-радио с SoX<br>• Observer/Pub-Sub EventEmitter | ETL-пайплайны, обработка больших файлов, медиа-стриминг |
| 3 | [asynchronous-nodejs-playground](https://github.com/Skippia/asynchronous-nodejs-playground) | TypeScript | • Внутреннее устройство event loop, libuv threadpool, порядок выполнения промисов<br>• Worker threads/workerpools, кластеризация + PM2, модель акторов<br>• Sequential vs concurrent vs parallel выполнение<br>• Async-отладчик, baseline-бенчмарки производительности | Оптимизация throughput, диагностика блокировки event loop, масштабирование PM2/cluster |
| 4 | [parallel-programming-playground](https://github.com/Skippia/parallel-programming-playground) | TypeScript | • Mutex (4 реализации + deadlock/livelock), Semaphore (бинарный/счётный + atomics), бенчмарки Atomics<br>• WorkerPool, async-примитивы (async-mutex, async-semaphore, barrier, bounded-channel, rate-limiter, rw-lock)<br>• Распределённая блокировка Redis, lock-free CAS-счётчик | CPU-интенсивные задачи (изображения/видео), rate limiting, пулы соединений, распределённые блокировки |
| 5 | [V8-sandboxes-playground](https://github.com/Skippia/V8-sandboxes-playground) | JavaScript | • Изолированные песочницы через модуль `vm` Node.js<br>• Двойная реализация: safeRequire (CJS) и safeImport (ESM)<br>• Загрузка модулей по белому списку, проксированные глобальные объекты, песочница для доступа к fs | Плагин-системы, исполнение пользовательских скриптов, мультитенантная изоляция |

### TypeScript и ФП

| # | Репозиторий | Язык | Описание | Варианты использования |
|---|-------------|------|----------|------------------------|
| 6 | [typescript-playground](https://github.com/Skippia/typescript-playground) | TypeScript | • 42 задачи на уровне типов (все utility-типы с нуля), арифметика на уровне типов, UnionToIntersection<br>• Рекурсивные типы, template literals, ковариантность/контравариантность<br>• Дистрибутивные условные типы, граничные случаи сужения типов<br>• misc-types (DeepReadonly, Invert, NoInfer) + 7 файлов с edge-case поведением | Типобезопасные библиотеки, проектирование SDK, сложные generic-API |
| 7 | [fp-playground](https://github.com/Skippia/fp-playground) | TypeScript | • fp-ts/ramda/monocle-ts — HOF, каррирование, композиция, tagless final, type-driven разработка<br>• Теория категорий (функторы, аппликативы, монады, Kleisli)<br>• Все монадические типы (Option, Either, Task, Reader, State, Writer)<br>• Алгебраические структуры, оптики, Game of Life | Пайплайны обработки ошибок, трансформации данных, DI через Reader, управление side-effects |
| 8 | [legacy-decorators-playground](https://github.com/Skippia/legacy-decorators-playground) | TypeScript | • Legacy `experimentalDecorators` + reflect-metadata<br>• Декораторы методов/классов, фабрики, порядок выполнения, двойная обёртка<br>• Эмиссия design:type/paramtypes/returntype | NestJS/Angular DI, ORM-декораторы, валидация, AOP |

### Базы данных и очереди сообщений

| # | Репозиторий | Язык | Описание | Варианты использования |
|---|-------------|------|----------|------------------------|
| 9 | [postgres-playground](https://github.com/Skippia/postgres-playground) | TypeScript / SQL | • Ранжирование, CTE, рекурсивные CTE, функции/процедуры, оконные функции, JSONB<br>• Материализованные представления, триггеры, pg-cron, полнотекстовый/нечёткий поиск, доменные типы<br>• Индексы (исключающие, составные, частичные)<br>• Репликация, партиционирование, PgBouncer, бэкап/восстановление, SSL, миграции<br>• Рекомендательные блокировки, уровни изоляции<br>• Коррелированные подзапросы, LISTEN/NOTIFY pub-sub, pg_ivm инкрементальные материализованные представления | Сложная аналитика, полнотекстовый поиск, шардинг/репликация, планировщик задач |
| 10 | [redis-playground](https://github.com/Skippia/redis-playground) | TypeScript | • Монорепо из 3 проектов: NestJS + ioredis (сессионная авторизация, Redlock, WATCH/транзакции, оптимистичная блокировка, ELK)<br>• SvelteKit аукцион (RediSearch, HyperLogLog, Lua-скрипты, Keygrip cookies)<br>• Vue 3 поисковый UI с MSW | Сессии, распределённые блокировки, real-time поиск, кэширование, аукционы |
| 11 | [rabbitmq-playground](https://github.com/Skippia/rabbitmq-playground) | TypeScript | • Topic exchange, publisher confirms, RPC, alternate/dead letter exchanges, consistent hash<br>• 3 стратегии повторов (DLX+TTL, экспоненциальный backoff, плагин delayed_message_exchange)<br>• 3 стратегии publisher confirms (синхронная/пакетная/асинхронная), обработка poison messages<br>• NestJS микросервисы + MongoDB, кластер из 3 нод с HAProxy + Shovels, бенчмарки clinic.js | Микросервисная коммуникация, retry/DLQ стратегии, event-driven архитектура |

### Паттерны и архитектура

| # | Репозиторий | Язык | Описание | Варианты использования |
|---|-------------|------|----------|------------------------|
| 12 | [patterns-playground](https://github.com/Skippia/patterns-playground) | TypeScript | • GoF-паттерны (8 поведенческих, 1 порождающий, 3 структурных)<br>• DDD Specification, паттерн Factorify<br>• Декораторы, мемоизация, миксины, пул объектов, thenable, Revealing Constructor | Чистая архитектура, плагин-системы, стейт-машины |
| 13 | [event-sourcing-playground](https://github.com/Skippia/event-sourcing-playground) | TypeScript | • 5 последовательных примеров (домен морских перевозок): базовый apply/replay, реверсия событий (Memento), внешнее кэширование (Decorator/QueryLog)<br>• Ретроактивная замена/отклонение с перемоткой, буферизация сайд-эффектов с дифференциальной отменой/переотправкой<br>• Бонус: event-based CRUD корзины с MongoDB + Express | Аудит-трейлы, undo/redo, темпоральные запросы, финансы/логистика |
| 14 | [vertical-slice-architecture-playground](https://github.com/Skippia/vertical-slice-architecture-playground) | TypeScript | • Две реализации NestJS + CQRS: базовая (Drizzle + SQLite) и продакшн (монорепо из нескольких приложений, PostgreSQL, RabbitMQ)<br>• Winston логгер + trace ID, Joi валидация, Docker Compose<br>• Обнаружение циклических зависимостей через madge<br>• 30 E2E-тестов на каждую версию | Feature-based организация кода, CQRS в NestJS, монорепо |

### DevOps и инфраструктура

| # | Репозиторий | Язык | Описание | Варианты использования |
|---|-------------|------|----------|------------------------|
| 15 | [devops-playground](https://github.com/Skippia/devops-playground) | YAML / Dockerfile | • Docker Compose мультистек (NestJS+RabbitMQ, Laravel+PHP-FPM, Vue/React+Express+MySQL/MongoDB)<br>• Swiggy микросервисы (Nginx + PostgreSQL), pgAdmin<br>• K8s-манифесты (локальные + AWS EKS, EFS, Secrets, ConfigMaps)<br>• Пайплайны GitHub Actions, конфиги Nginx | CI/CD пайплайны, контейнеризация, K8s-оркестрация, reverse proxy |
| 16 | [SSR-cache-demo](https://github.com/Skippia/SSR-cache-demo) | TypeScript | • 3 стратегии кэширования SSR в Nuxt 3: routeRules SWR (in-memory TTL), ETag + stale-while-revalidate (браузерное, MD5, 304)<br>• Серверная middleware + внешнее хранилище (перехват рендера на основе TTL) | Оптимизация SSR-производительности, CDN-кэширование, SEO |

### Протоколы и коммуникация

| # | Репозиторий | Язык | Описание | Варианты использования |
|---|-------------|------|----------|------------------------|
| 17 | [gRPC-playground](https://github.com/Skippia/gRPC-playground) | TypeScript | • Eliza-сервис из .proto (buf + protoc-gen-ts)<br>• Серверные/клиентские интерцепторы, health checks, серверная рефлексия, обработка ошибок<br>• Типы стриминга (server/bidi), политики retry/deadline | Микросервисные API, high-performance RPC, стриминг данных |
| 18 | [realtime-playground](https://github.com/Skippia/realtime-playground) | JavaScript / TypeScript | • 7 мини-чатов: short polling (RAF), long polling (EventEmitter), SSE, HTTP/2 streams<br>• Базовый WebSocket, WebSocket + Redis pub/sub + масштабирование через HAProxy<br>• Совместная таблица (Vue 3 + Pinia) | Чаты, live-дашборды, совместное редактирование, нотификации |

### Разное

| # | Репозиторий | Язык | Описание | Варианты использования |
|---|-------------|------|----------|------------------------|
| 19 | [miscellaneous-playground](https://github.com/Skippia/miscellaneous-playground) | JavaScript | • 7 отдельных примеров: shadowing undefined, short-circuit side effects, autoboxing/prototype pollution<br>• Оператор запятая, потеря async stack trace, неэнумерабельная сериализация Error<br>• Async race conditions | Код-ревью, аудит безопасности (prototype pollution), отладка async |
| 20 | [algorithms-playground](https://github.com/Skippia/algorithms-playground) | JavaScript / TypeScript | • Сортировки (пузырьковая, вставками, слиянием, быстрая, выбором)<br>• Поиск (бинарный, BFS, Dijkstra), структуры данных (бинарные деревья, хэш-таблица, связный список)<br>• Задачи: мемоизация Фибоначчи, палиндром, шифр Цезаря, решето Эратосфена, FizzBuzz, reverse words, two sum, harmless ransom note, mean/median/mode, max profit, island perimeter | Coding-интервью, оптимизация производительности, кастомные структуры данных |
| 21 | [automapper-demo](https://github.com/Skippia/automapper-demo) | TypeScript | • Демо библиотеки @automapper: классический подход (на декораторах через @automapper/classes) и автоматический (plain objects через @automapper/pojos)<br>• Маппинг User entity в DTO | DTO-маппинг в layered-архитектуре, трансформация API-ответов |

## Установка

```bash
# Клонировать со всеми подмодулями
git clone --recurse-submodules git@github.com:Skippia/meta-playground.git

# Или инициализировать подмодули после клонирования
git submodule update --init --recursive
```

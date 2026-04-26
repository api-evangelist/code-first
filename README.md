# Code First (code-first)

Code-first is an API design and software development approach where the application's source code is the primary source of truth and the API contract (OpenAPI document, GraphQL schema, gRPC proto, type definitions) is generated from that code via decorators, annotations, type inference, or runtime introspection. It contrasts with the design-first (or contract-first) approach in which a hand-authored OpenAPI/GraphQL/Proto contract is written first and code is scaffolded from it. Code-first approaches are widely used in TypeScript, Python, Java, Go, and C# ecosystems where strong type systems make schema generation reliable.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/code-first/refs/heads/main/apis.yml)

## Scope

- **Type:** Index (Topic)
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- API Design
- Code Generation
- Code-First
- Decorators
- Development Methodology
- Software Architecture
- Type Safety

## Timestamps

- **Created:** 2025-01-01
- **Modified:** 2026-04-26

## Key Frameworks and Tooling

| Framework | Language | Contract Generation |
| --- | --- | --- |
| [FastAPI](https://fastapi.tiangolo.com/) | Python | OpenAPI 3.x from Pydantic models and type hints |
| [NestJS](https://docs.nestjs.com/openapi/introduction) | TypeScript | OpenAPI via `@nestjs/swagger` decorators |
| [tRPC](https://trpc.io/) | TypeScript | End-to-end TypeScript types, no separate IDL |
| [Hono RPC](https://hono.dev/docs/guides/rpc) | TypeScript | TypeScript inference, optional OpenAPI via `@hono/zod-openapi` |
| [Spring Boot + springdoc](https://springdoc.org/) | Java/Kotlin | OpenAPI from JAX-RS/Spring annotations |
| [Quarkus](https://quarkus.io/guides/openapi-swaggerui) | Java/Kotlin | MicroProfile OpenAPI from JAX-RS annotations |
| [Micronaut OpenAPI](https://micronaut-projects.github.io/micronaut-openapi/) | Java/Kotlin | Compile-time AST inspection |
| [ASP.NET Core](https://learn.microsoft.com/aspnet/core/fundamentals/openapi) | C# | `Microsoft.AspNetCore.OpenApi` / Swashbuckle |
| [Huma](https://huma.rocks/) | Go | OpenAPI from struct tags and reflection |
| [Encore](https://encore.dev/) | Go/TypeScript | API contract inferred from typed handlers |
| [zod-openapi](https://github.com/asteasolutions/zod-to-openapi) | TypeScript | OpenAPI generated from Zod schemas |
| [rswag](https://github.com/rswag/rswag) | Ruby on Rails | OpenAPI from RSpec request specs |
| [Scribe](https://scribe.knuckles.wtf/) | PHP / Laravel | OpenAPI from controller introspection and PHPDoc |
| [Pothos](https://pothos-graphql.dev/) | TypeScript | GraphQL SDL from typed builders |
| [grpc-gateway](https://github.com/grpc-ecosystem/grpc-gateway) | Go | Proto + code; reverse-proxy to REST |

## Trade-offs

### Pros
- Single source of truth eliminates contract/code drift
- Faster iteration - no separate OpenAPI editing step
- Strong type safety end-to-end (especially in TypeScript and Python)
- Familiar to backend engineers; low onboarding cost
- IDE-friendly - routes and types surface natively

### Cons
- Contract changes are implicit and harder to review independently
- Risk of leaking implementation details into the public contract
- Cross-team or cross-organization governance is harder
- Generated specs often lack examples, descriptions, and security details
- Frontend or partner teams cannot start integration before code is written

## When to Use

- Internal services where the backend team owns producer and consumer
- Rapid product development with tight feedback loops
- TypeScript monorepos using tRPC or shared types
- Python / FastAPI services where Pydantic already models the domain

## When to Avoid

- Public APIs with diverse external consumers
- Government, banking, or other contract-bound API programs
- Multi-team programs where contract review precedes implementation
- SDK generation pipelines that need stable, reviewed schemas

## Common Properties

- [Wikipedia: Code First](https://en.wikipedia.org/wiki/Code_first)
- [Postman: API-First vs Code-First](https://blog.postman.com/api-first-vs-code-first/)
- [Stoplight: API Design-First vs Code-First](https://blog.stoplight.io/api-design-first-vs-code-first)
- [Swagger: Code-First vs Design-First](https://swagger.io/blog/code-first-vs-design-first-api/)
- [OpenAPI Specification](https://spec.openapis.org/)

## Notes

This profile is a topic landscape, not a single API. No OpenAPI specification, JSON-LD vocabulary, Spectral ruleset, or Naftiko capability bundle is generated because there is no single contract to lint or describe; each framework above ships its own.

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com

# Code First (code-first)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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

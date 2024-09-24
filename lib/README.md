# `surveilr` Standard Library and Patterns

`surveilr`'s Standard Library (`std`) and Patterns are written in Deno-flavored TypeScript and **require Deno 1.40+** to run.

To understand terminology, see http://surveilr.com/blog/surveilr-core-vs-patterns/.

## `lib` Structure

```md
lib/
├── pattern/                All public patterns (composable)
│   ├── fhir-explorer/        FHIR Explorer Pattern
│   └── (...)/                add more patterns above this one
├── service/                All public services (large combinations of patterns)
│   ├── drh/                  Diabetes Research Hub "Edge" Service
│   └── (...)/                add more services above this one
├── std/                    surveilr Standard Library (used by all patterns)
│   ├── models/               RSSD schemas
│   ├── notebook/             Notebook schemas
│   ├── web-ui-content/       SQLPage content for Shell, Console, etc.
│   ├── deps.ts               Common Deno dependencies (used by all patterns)
│   └── package.sql.ts        Module to include in all other patterns
└── universal/              Universally applicable modules (can be used anywhere)
```
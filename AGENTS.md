# Agent guidance

This file is read by automated agents (security scanners, code
analyzers, AI assistants) operating on this repository. It
points them at the human-authored references they should
consult before producing output.

## Security

Security model: [SECURITY.md](./SECURITY.md)

Agents that scan this repository should consult `SECURITY.md`
for the project's threat model, in-scope / out-of-scope
declarations, and known non-findings before reporting issues.

## Cursor Cloud

Cloud Agents use OpenJDK 25 (`JAVA_HOME=/usr/lib/jvm/java-25-openjdk-amd64`). On boot, PostgreSQL 16 starts locally and `./gradlew devRun` serves the API at `https://localhost:8443/fineract-provider`. The health check and default `mifos` login are in the Quick Start section of `README.md`.

PostgreSQL is not Docker. Role `root` with password `postgres` owns `fineract_tenants` and `fineract_default` on `localhost:5432`.

`:fineract-core:test` and `:fineract-validation:test` do not need extra services. Tests in `fineract-provider` and `fineract-command-*` that use Testcontainers need Docker, which this environment does not start.

# Greenmask

**Open-source tools for reproducible, production-like environments.**

We help engineering teams get safe, production-like environments for development, testing, CI and AI agents — without
manual database preparation or waiting on DBA queues.

[![Website](https://img.shields.io/badge/website-greenmask.io-14C19A)](https://www.greenmask.io/?utm_source=github&utm_medium=repo&utm_campaign=oss)
[![Discord](https://img.shields.io/discord/1179422525294399488?label=Discord&logo=discord)](https://discord.com/invite/rKBKvDECfd)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue)](https://www.apache.org/licenses/LICENSE-2.0)

---

## Products

<table>
  <tr>
    <td align="center" width="50%">
      <a href="https://www.greenmask.io/docs/greenmask/?utm_source=github&utm_medium=repo&utm_campaign=oss">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/greenmask-logo-dark.svg">
          <img src="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/greenmask-logo-light.svg" alt="Greenmask" height="44">
        </picture>
      </a>
      <br><br>
      Test data management and anonymization for databases
      <br>
      <a href="https://www.greenmask.io/docs/greenmask/?utm_source=github&utm_medium=repo&utm_campaign=oss">Docs</a> ·
      <a href="https://github.com/GreenmaskIO/greenmask">Repo</a>
    </td>
    <td align="center" width="50%">
      <a href="https://www.greenmask.io/docs/arcave/?utm_source=github&utm_medium=repo&utm_campaign=oss">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/arcave-logo-dark.svg">
          <img src="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/arcave-logo-light.svg" alt="arcave" height="44">
        </picture>
      </a>
      <br><br>
      Savepoints, rollback and branching for any Docker Compose project
      <br>
      <a href="https://www.greenmask.io/docs/arcave/?utm_source=github&utm_medium=repo&utm_campaign=oss">Docs</a> ·
      <a href="https://github.com/GreenmaskIO/arcave">Repo</a>
    </td>
  </tr>
</table>

Greenmask makes the data in an environment safe and realistic; arcave makes the environment holding that data
reproducible.

### Greenmask

Turns production into safe, production-like datasets and delivers them to development, testing and CI.

- **Anonymization** — mask and transform sensitive values in-flight, inside the logical dump stream.
- **Subsetting** — extract only the part of production you need, keeping relational consistency.
- **Synthetic data** — generate realistic replacement values and datasets.
- **Stateless by design** — nothing to host between runs and no raw data at rest, so it automates cleanly in CI.
- **Extensible** — complement the built-in transformers with your own.

Try it in the [playground](https://www.greenmask.io/docs/greenmask/playground?utm_source=github&utm_medium=repo&utm_campaign=oss).

### arcave

Saves the whole live state of a running Compose project — every volume, every container filesystem, and the compose
spec itself — as one consistent savepoint, and puts it back in one command. Fork independent copies off any savepoint.
Ships an MCP server so AI agents can checkpoint and roll back on their own
([agent loops](https://www.greenmask.io/docs/arcave/use_cases/agent_loops?utm_source=github&utm_medium=repo&utm_campaign=oss)).

```shell
arcave savepoint create before-migration
# ...run the migration, the test suite, the agent...
arcave rollback before-migration
```

---

## How It Works

<table>
  <tr>
    <td width="50%" valign="top">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/step-01-dark.svg">
        <img src="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/step-01-light.svg" alt="Run your Compose project">
      </picture>
      <b>1. Run your Compose project</b><br>
      Bring your project up the way you already do. No new infrastructure, no rewrites, no allowlists.
    </td>
    <td width="50%" valign="top">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/step-02-dark.svg">
        <img src="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/step-02-light.svg" alt="Make the data safe">
      </picture>
      <b>2. Make the data safe</b> · Greenmask<br>
      Turn production into anonymized, production-like data — subset to the size the environment needs.
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/step-03-dark.svg">
        <img src="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/step-03-light.svg" alt="Capture the environment">
      </picture>
      <b>3. Capture the environment</b> · arcave<br>
      Save data, services and configuration as one consistent snapshot of the whole environment.
    </td>
    <td width="50%" valign="top">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/step-04-dark.svg">
        <img src="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/step-04-light.svg" alt="Branch and roll back">
      </picture>
      <b>4. Branch and roll back</b> · arcave<br>
      Try migrations, run agents, break things. Every developer, pipeline and agent works on a disposable copy.
    </td>
  </tr>
</table>

---

## Repositories

| Repository                                                  | What it is                                                                                                                                                                  |
|-------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [greenmask](https://github.com/GreenmaskIO/greenmask)       | The Greenmask engine and CLI: dump, anonymize, subset, and restore databases.                                                                                               |
| [arcave](https://github.com/GreenmaskIO/arcave)             | Ephemeral environments and branching for Docker Compose: save the whole live state of a project (volumes, container filesystems, compose spec) and roll back in one command. |
| [storages](https://github.com/GreenmaskIO/storages)         | Standalone Go library extracted from Greenmask: one interface for object storage with local filesystem, S3 (and compatibles), Azure Blob, SFTP, and in-memory backends.     |
| [transformers](https://github.com/GreenmaskIO/transformers) | Example of a custom transformer for Greenmask.                                                                                                                              |
| [examples](https://github.com/GreenmaskIO/examples)         | Ready-to-run examples, integrations, and deployment scenarios for Greenmask.                                                                                                |

---

## Support Matrix

**Greenmask**

| Database   | Status                                                             |
|------------|--------------------------------------------------------------------|
| PostgreSQL | Stable                                                             |
| MySQL      | Beta ([#222](https://github.com/GreenmaskIO/greenmask/issues/222)) |

Dumps can be stored in a local directory, S3 (and compatibles), Azure Blob Storage, or over SSH/SFTP.

**arcave**

Works with any Compose project — Postgres, MySQL, Kafka, Redis, MinIO… there is no allowlist. Requires Docker 25+ on
Linux or macOS.

---

## Vision & Roadmap

From safe data to ephemeral environments:

1. **Greenmask — since 2023.** The logical level: safe, production-like data. Anonymization, subsetting and synthetic
   data, delivered to every environment that needs it.
2. **arcave — since 2026.** The physical level: the environment itself. Consistent snapshots of data, services and
   configuration — rolled back or branched in seconds.
3. **The platform — in progress.** Greenmask and arcave united in one control plane over multiple infrastructure
   providers: full-cycle ephemeral environments, provisioned where your teams and agents work.

Target architecture of an ephemeral development environment:

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/ephemeral-architecture-dark.svg">
  <img src="https://raw.githubusercontent.com/GreenmaskIO/.github/main/profile/assets/ephemeral-architecture-light.svg" alt="Ephemeral development environment: a developer laptop (User, AI Agent, local Service) connecting to a remote ephemeral env (DBaaS with branching, Agentic API, Test Data Management, User Services).">
</picture>

Read the full [vision](https://www.greenmask.io/vision?utm_source=github&utm_medium=repo&utm_campaign=oss).

We are building this in collaboration with [Solanica](https://solanica.io/) and [OpenEverest](https://openeverest.io/)
as part of a broader effort to deliver open-source, enterprise-grade infrastructure for modern software delivery — see
the [announcement](https://www.greenmask.io/blog/greenmask-openeverest-automating-safe-production-data?utm_source=github&utm_medium=repo&utm_campaign=oss).

---

## Community & Support

- Documentation: [Greenmask](https://www.greenmask.io/docs/greenmask/?utm_source=github&utm_medium=repo&utm_campaign=oss)
  · [arcave](https://www.greenmask.io/docs/arcave/?utm_source=github&utm_medium=repo&utm_campaign=oss)
- Questions and ideas: [GitHub Discussions](https://github.com/GreenmaskIO/greenmask/discussions)
- Bug reports and feature requests: GitHub Issues in the relevant repository
- Chat: [Discord](https://discord.com/invite/rKBKvDECfd) · [Telegram](https://t.me/greenmask_community)
- Follow: [LinkedIn](https://www.linkedin.com/company/greenmask-io) · [X](https://x.com/GreenmaskIO)
- Security: see the [Security Policy](https://github.com/GreenmaskIO/greenmask/blob/main/SECURITY.md) or write
  to [security@greenmask.io](mailto:security@greenmask.io)

Greenmask, Inc. helps engineering organizations make stateful environments reproducible at scale — enterprise support,
consulting, training and custom development from the team behind Greenmask and arcave.
[Talk to sales](https://www.greenmask.io/talk-to-sales?utm_source=github&utm_medium=repo&utm_campaign=oss) or write
to [sales@greenmask.io](mailto:sales@greenmask.io) / [support@greenmask.io](mailto:support@greenmask.io).

---

## License

All Greenmask projects are open source under the Apache 2.0 License.

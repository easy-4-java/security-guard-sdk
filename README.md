# security-guard-sdk

[English](./README.md) | [简体中文](./README.zh-CN.md)

[![Java](https://img.shields.io/badge/Java-17-orange)](https://github.com/easy-4-java/security-guard-sdk) [![License](https://img.shields.io/badge/license-Apache%202.0-green)](https://www.apache.org/licenses/LICENSE-2.0.txt)

Project scaffold for a security guard / anti-abuse SDK. As of the `2.0.x.x.20260630-SNAPSHOT` snapshot the repository contains the Maven project skeleton only — no production code has been added yet.

## Table of Contents

- [1. Project Overview](#1-project-overview)
- [2. Features & Status](#2-features--status)
- [3. Requirements & Compatibility](#3-requirements--compatibility)
- [4. Architecture & Modules](#4-architecture--modules)
- [5. Installation](#5-installation)
- [6. Quick Start](#6-quick-start)
- [7. Configuration](#7-configuration)
- [8. Core Usage / API](#8-core-usage--api)
- [9. Testing & Build](#9-testing--build)
- [10. Versioning & Branches](#10-versioning--branches)
- [11. Contributing & License](#11-contributing--license)

## 1. Project Overview

**What it is**

`security-guard-sdk` is a planned SDK for security-guard (risk control / anti-abuse) integration. Judging by the artifact name, its intended role is to provide a reusable client for a security guard service. **Assumption:** the concrete guard service and the scope of the API are not yet defined in this branch.

**What it is not (currently)**

- It is not a usable library yet: the project contains **no `src/main/java` sources** at the `2.0.x.x.20260630-SNAPSHOT` snapshot.
- There is no public API, no configuration and no documentation beyond this README.

**Typical scenarios (planned)**

| Scenario | Description |
| :--- | :--- |
| Guard-service integration (planned) | To be defined once the public API lands in a future snapshot. |

## 2. Features & Status

| Capability | Status | Notes |
| :--- | :--- | :--- |
| Maven project skeleton (`io.github.easy4j:security-guard-sdk`) | Available | `jar` packaging, JDK 8 baseline, release-ready plugin configuration |
| Production sources | Not started | `src/main/java` does not exist yet |
| Public API | Not started | — |

> Status is reported as of `2.0.x.x.20260630-SNAPSHOT` on the `feature/2.0.x` branch.

## 3. Requirements & Compatibility

| Item | Version |
| :--- | :--- |
| JDK | 17+ |
| Maven | 3.0+ (Maven Wrapper 3.5.0 bundled) |

**Version lines**

| Branch | JDK baseline | Version pattern |
| :--- | :--- | :--- |
| `feature/1.0.x` | JDK 8 | `1.0.x.*` |
| `feature/2.0.x` | JDK 17 | `2.0.x.*` |
| `feature/3.0.x` | JDK 21 | `3.0.x.*` |

## 4. Architecture & Modules

```text
 +---------------------------+
 | security-guard-sdk        |
 |  (project scaffold)       |
 |  packaging: jar           |
 |  src/main/java: (empty)   |
 +---------------------------+
        |
        v
  public API: TBD (Assumption)
```

This is a **single-module** project:

| Module / artifact | Role |
| :--- | :--- |
| `security-guard-sdk` | Planned SDK module; currently only the Maven skeleton (pom, wrapper, LICENSE, release plugins). |

## 5. Installation

The artifact is not yet published to Maven Central. Since the module has no sources, consuming it as a dependency is not meaningful at this snapshot; once code lands, resolve it from the project's configured artifact repository (Aliyun Packages) or install it locally from source.

**Maven** (intended coordinates)

```xml
<dependency>
    <groupId>io.github.easy4j</groupId>
    <artifactId>security-guard-sdk</artifactId>
    <version>2.0.x.x.20260630-SNAPSHOT</version>
</dependency>
```

**Gradle**

```groovy
implementation 'io.github.easy4j:security-guard-sdk:2.0.x.x.20260630-SNAPSHOT'
```

## 6. Quick Start

There is no public API yet, so no usage example can be provided. The only meaningful operation at this snapshot is building the skeleton:

```bash
./mvnw clean install
```

**Expected result:** the build succeeds and installs an (effectively empty) `security-guard-sdk-2.0.x.x.20260630-SNAPSHOT.jar` into the local repository.

## 7. Configuration

No configuration exists yet — there is no `src/main/java`, no `src/main/resources` and no Spring Boot auto-configuration in this module.

## 8. Core Usage / API

No public API classes exist at this snapshot. This section will be filled in when the first API lands. **Assumption:** the upcoming API will cover calling a security-guard / risk-control service from Java applications.

## 9. Testing & Build

```bash
# Full build (JaCoCo coverage report/check are configured in the pom)
./mvnw clean verify

# Install into the local repository
./mvnw install
```

Test & gate facts (as configured in the pom):

- JaCoCo is bound to `prepare-agent` / `report` / `check`; the `check` rule requires a **90% line coverage ratio** (configured with `haltOnFailure=false`).
- No unit tests exist yet (there is no source code to test).

## 10. Versioning & Branches

| Branch | JDK baseline | Version pattern | Status |
| :--- | :--- | :--- | :--- |
| `feature/1.0.x` | JDK 8 | `1.0.x.*` | Active; current snapshot `1.0.x.20260630-SNAPSHOT` |
| `feature/2.0.x` | JDK 17 | `2.0.x.*` | Maintained |
| `feature/3.0.x` | JDK 21 | `3.0.x.*` | Maintained |

Maintenance strategy: the 1.0.x line keeps JDK 8 compatibility for legacy deployments; the 2.0.x and 3.0.x lines are the modern JDK baselines. Release artifacts are published to the project's configured artifact repository (Aliyun Packages) and GitHub Releases; the project has not yet published to Maven Central.

## 11. Contributing & License

Contributions are welcome — please open an issue or a pull request on the [GitHub repository](https://github.com/easy-4-java/security-guard-sdk).

This project is licensed under the **Apache License 2.0**. See [LICENSE](LICENSE) for details.

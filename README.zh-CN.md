# security-guard-sdk

[English](./README.md) | [简体中文](./README.zh-CN.md)

[![Java](https://img.shields.io/badge/Java-17-orange)](https://github.com/easy-4-java/security-guard-sdk) [![License](https://img.shields.io/badge/license-Apache%202.0-green)](https://www.apache.org/licenses/LICENSE-2.0.txt)

安全防护（风控/反滥用）SDK 的项目骨架。在 `2.0.x.x.20260630-SNAPSHOT` 快照上，仓库中仅包含 Maven 工程骨架，尚未加入任何生产代码。

## 目录

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

**是什么**

`security-guard-sdk` 是规划中的安全防护（风控/反滥用）集成 SDK。从构件名称判断，其预期职责是为安全防护服务提供可复用的客户端。**假设：** 具体防护服务与 API 范围在本分支上尚未定义。

**（当前）不是什么**

- 当前还不是可用的库：在 `2.0.x.x.20260630-SNAPSHOT` 快照上，项目**没有 `src/main/java` 源码**。
- 除本 README 外，没有公开 API、没有配置、没有其他文档。

**典型场景（规划中）**

| 场景 | 说明 |
| :--- | :--- |
| 防护服务集成（规划中） | 待未来快照中公开 API 落地后定义。 |

## 2. Features & Status

| 能力 | 状态 | 说明 |
| :--- | :--- | :--- |
| Maven 工程骨架（`io.github.easy4j:security-guard-sdk`） | 可用 | `jar` 打包、JDK 8 基线、发布插件配置齐备 |
| 生产源码 | 未开始 | `src/main/java` 尚不存在 |
| 公开 API | 未开始 | — |

> 状态以 `feature/2.0.x` 分支上的 `2.0.x.x.20260630-SNAPSHOT` 为准。

## 3. Requirements & Compatibility

| 项目 | 版本 |
| :--- | :--- |
| JDK | 17+ |
| Maven | 3.0+（内置 Maven Wrapper 3.5.0） |

**版本线**

| 分支 | JDK 基线 | 版本模式 |
| :--- | :--- | :--- |
| `feature/1.0.x` | JDK 8 | `1.0.x.*` |
| `feature/2.0.x` | JDK 17 | `2.0.x.*` |
| `feature/3.0.x` | JDK 21 | `3.0.x.*` |

## 4. Architecture & Modules

```text
 +---------------------------+
 | security-guard-sdk        |
 |  （项目骨架）              |
 |  packaging: jar           |
 |  src/main/java:（空）      |
 +---------------------------+
        |
        v
  公开 API：待定（假设）
```

本项目为**单模块**工程：

| 模块 / 构件 | 职责 |
| :--- | :--- |
| `security-guard-sdk` | 规划中的 SDK 模块；当前仅有 Maven 骨架（pom、wrapper、LICENSE、发布插件）。 |

## 5. Installation

该构件尚未发布到 Maven Central。由于模块尚无源码，本快照阶段以依赖方式引入没有实际意义；待代码落地后，请从项目配置的制品仓库（阿里云制品仓库）获取，或从源码本地安装。

**Maven**（预期坐标）

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

目前尚无公开 API，无法提供使用示例。本快照阶段唯一有意义的操作是构建骨架：

```bash
./mvnw clean install
```

**预期结果：** 构建成功，并将一个（实际为空的）`security-guard-sdk-2.0.x.x.20260630-SNAPSHOT.jar` 安装到本地仓库。

## 7. Configuration

尚不存在任何配置——本模块没有 `src/main/java`、没有 `src/main/resources`，也没有 Spring Boot 自动配置。

## 8. Core Usage / API

本快照阶段不存在任何公开 API 类。待首个 API 落地后填充本节。**假设：** 未来的 API 将覆盖 Java 应用调用安全防护/风控服务的能力。

## 9. Testing & Build

```bash
# 完整构建（pom 中已配置 JaCoCo 覆盖率报告/检查）
./mvnw clean verify

# 安装到本地仓库
./mvnw install
```

测试与门禁事实（以 pom 配置为准）：

- JaCoCo 绑定 `prepare-agent` / `report` / `check`；`check` 规则要求**行覆盖率不低于 90%**（配置了 `haltOnFailure=false`）。
- 尚无单元测试（没有可测试的源码）。

## 10. Versioning & Branches

| 分支 | JDK 基线 | 版本模式 | 状态 |
| :--- | :--- | :--- | :--- |
| `feature/1.0.x` | JDK 8 | `1.0.x.*` | 活跃；当前快照 `1.0.x.20260630-SNAPSHOT` |
| `feature/2.0.x` | JDK 17 | `2.0.x.*` | 维护中 |
| `feature/3.0.x` | JDK 21 | `3.0.x.*` | 维护中 |

维护策略：1.0.x 版本线保持 JDK 8 兼容，服务于存量部署；2.0.x 与 3.0.x 版本线为现代 JDK 基线。发布制品发布到项目配置的制品仓库（阿里云制品仓库）与 GitHub Releases；项目尚未发布到 Maven Central。

## 11. Contributing & License

欢迎参与贡献——请在 [GitHub 仓库](https://github.com/easy-4-java/security-guard-sdk) 提交 Issue 或 Pull Request。

本项目基于 **Apache License 2.0** 开源。详见 [LICENSE](LICENSE)。

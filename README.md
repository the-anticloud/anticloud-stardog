# STARDOG

![license](https://img.shields.io/badge/license-license-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-philosophy_semantics-lightgrey)

> Anticloud-hardened packaging of the upstream project `STARDOG` in category **PHILOSOPHY SEMANTICS**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** PHILOSOPHY SEMANTICS · **Upstream:** https://github.com/stardog-union/stardog-examples · **Upstream pin:** `f95303fe40a0016c655b2855c58fcdbf2bcc213b` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

[![Join the chat at https://gitter.im/Complexible/stardog-examples](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/Complexible/stardog-examples?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

# Programming Stardog: Examples

This is a small collection of examples of working with [Stardog](http://stardog.com) via its APIs, as
well as examples of how to use some of the extension points within Stardog.

## How to build examples

First, you'll need a valid Stardog download.

You can use the included Gradle Wrapper script to build the examples in `examples/api`, `example/foaf`, `examples/function`.

To compile or run the examples, gradle will automatically download the dependencies from our public maven project:

```bash
$ ./gradlew compileJava
```

To run the examples, they require a valid `$STARDOG_HOME`; you can provide this via the parameter `stardog.home`
(eg `-PstardogHome=/my/stardog/home`).

To run any of the examples, you can use the Gradle `execute` task.  By default, this will run the `ConnectionAPIExample`
program, but you can specify the fully-qualified class name of any of the other examples using the `mainClass` parameter.

```java
$ ./gradlew execute -PmainClass=com.complexible.stardog.examples.api.ICVExample
```

### .NET Examples

To compile the .NET examples, you will need to install [.NET Core](https://dotnet.microsoft.com/download). Make sure that the `dotnet` tool is on your `PATH`

While you can build the sample with the latest version of the .NET Core SDK you will need .NET Core runtime installed to **run** the example. You can download it from [here](https://dotnet.microsoft.com/download/dotnet-core/2.1) - you can verify which .NET Core runtimes you have installed by running:

```bash
dotnet --list-runtimes
```

Once you have installed .NET Core SDK and runtime,you can build the sample with the following command:

```bash
$ ./gradlew compileDotnet
```

To run the .NET examples you should have Stardog running locally and listening on port 5820 (you can change this by editing the connection string in `./examples/dotnet/TrinityConsoleSample/Program.cs`. In addition, the example expects Stardog to have a database named 'music' loaded with the data from `./examples/dotnet/TrinityConsoleSample/Ontologies/music_schema.ttl` and [music.ttl.gz](https://github.com/stardog-union/stardog-tutorials/blob/master/music/music.ttl.gz) in a named graph called `http://stardog.com/tutorial`

You can run the sample with the following command (NOTE: the following command will automatically rebuild the sample):

```bash
$ ./gradlew runDotnet
```

The sample project will connect to Stardog and execute several queries using SPARQL and LINQ. It will print the results to the console.

For additional information see the DotNet Samples' README file - `./examples/dotnet/README.md`

## Generating Documentation

The Stardog [documentation](http://docs.stardog.com) and its [javadocs](http://docs.stardog.com/javadoc/snarl) are a good
place to start. But some examples in this project are annotated using Markdown; they can be processed by
[Docco](http://jashkenas.github.io/docco/).

If you don't have Docco installed, it's pretty easy to get started:

```bash
$ sudo npm install -g docco
```

Then, you can run it directly against any example:

```bash
$ docco -o docs main/src/com/complexible/stardog/api/ConnectionAPIExample.java
```

Or you can use the supplied `gradle docs` task in each build file that will run Docco against all annotated source files.

## Service Loading

You'll notice that a number of examples have in their source a directory `META-INF/services`, these are the service
registrations for each example.

Stardog uses the JDK [ServiceLoader](http://docs.oracle.com/javase/6/docs/api/java/util/ServiceLoader.html) to load
new services at runtime and make them available to the various parts of the system.  The files in the `services`
directory should be the fully qualified class name of the class/service, such as `com.complexible.stardog.plan.filter.functions.Function`,
and the contents of the file should be a list of the fully qualified class names of the implementations of that service.

These need to be a part of your classpath, usually embedded in the jar file with the compiled source, in order for
the `ServiceLoader` to make them up.

## List of Examples

1. [Custom Analyzers](./examples/analyzer/readme.md)
1. [Stardog API Examples](./examples/api/readme.md)
1. [Integrity Constraint Validation](./examples/cli/icv)
1. [CSV example](./examples/cli/virtual/csv/readme.md)
1. [Docs Examples](./examples/docs/readme.md)
1. [Database Archetype Extensibility](https://github.com/stardog-union/stardog-archetypes/)
1. [DotNet Examples](./examples/dotnet/README.md)
1. [Function Extensibility](./examples/function/readme.md)
1. [Transaction Listener](./examples/listener/readme.md)
1. [Cloud Foundry Example Application](https://github.com/stardog-union/cf-example)
1. [Machine Learning](./examples/machinelearning)
1. [Anti-money laundering (AML) Example](./examples/aml)
1. [Transaction listener](./examples/connectable)
1. [Http handler](./examples/http_handler)
1. [Stardog Free Examples](./examples/stardog_free)

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Java / Gradle** (manifests: build.gradle; scanned in UPSTREAM_CLONE)
- Top-level source layout: `config/`, `demo-days/`, `examples/`, `gradle/`, `weblog/`
- Snapshot size: **314 files**, **32948 lines of code** (measured; see Benchmarks)
- Primary languages: `.ttl` (35), `.java` (31), `.sms` (23), `.csv` (19), `.md` (19), `.sparql` (17)
- Upstream commit pinned for this packaging: `f95303fe40a0016c655b2855c58fcdbf2bcc213b`

---

## Installation

First, you'll need a valid Stardog download.

You can use the included Gradle Wrapper script to build the examples in `examples/api`, `example/foaf`, `examples/function`.

To compile or run the examples, gradle will automatically download the dependencies from our public maven project:

```bash
$ ./gradlew compileJava
```

To run the examples, they require a valid `$STARDOG_HOME`; you can provide this via the parameter `stardog.home`
(eg `-PstardogHome=/my/stardog/home`).

To run any of the examples, you can use the Gradle `execute` task.  By default, this will run the `ConnectionAPIExample`
program, but you can specify the fully-qualified class name of any of the other examples using the `mainClass` parameter.

```java
$ ./gradlew execute -PmainClass=com.complexible.stardog.examples.api.ICVExample
```

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

No usage section was found in the upstream readme. Entry points detected in this project directory:

Browse the snapshot layout listed under What This Project Does and follow the upstream run instructions for the detected ecosystem (Java / Gradle).

Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

well as examples of how to use some of the extension points within Stardog.

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Java / Gradle |
| Manifests detected | build.gradle |
| Files in snapshot | 314 |
| Lines of code | 32948 |
| Dependency references | 0 |
| Upstream license | Apache-2.0 |
| Overlay license | Anticommons 0.1.0 |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

No configuration section was found in the upstream readme. Configuration-relevant files detected in this project directory:

- `config`

Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `STARDOG` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: Apache-2.0** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text

                                 Apache License
                           Version 2.0, January 2004
                        http://www.apache.org/licenses/

   TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION

   1. Definitions.

      "License" shall mean the terms and conditions for use, reproduction,
      and distribution as defined by Sections 1 through 9 of this document.

      "Licensor" shall mean the copyright owner or entity authorized by
      the copyright owner that is granting the License.

      "Legal Entity" shall mean the union of the acting entity and all
      other entities that control, are controlled by, or are under common
      control with that entity. For the purposes of this definition,
      "control" means (i) the power, direct or indirect, to cause the
      direction or management of such entity, whether by contract or
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original Apache-2.0 terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `Apache-2.0` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `STARDOG` (category: PHILOSOPHY SEMANTICS)
- **Upstream URL:** https://github.com/stardog-union/stardog-examples
- **Pinned commit (SHA):** `f95303fe40a0016c655b2855c58fcdbf2bcc213b`
- **Branch:** develop
- **Pin provenance:** GitHub API commits/develop. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`a2ae956bb12ca801ff1dd453421c0a3f1b692b889b78d6ff36398f6de1a2a231`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.


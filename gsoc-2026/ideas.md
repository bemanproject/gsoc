---
title: Google Summer of Code 2026 Ideas List
---

- [The Beman Project @ GSoC](#the-beman-project--gsoc)
- [Mentors of the projects](#mentors-of-the-projects)
- [The Beman Project Ideas](#the-beman-project-ideas)
  - [Beman implementation of P2980: Physical quantities and units (beman.units)](#beman-implementation-of-p2980-physical-quantities-and-units-bemanunits)
    - [Description](#description)
    - [Reading \& Related Material](#reading--related-material)
  - [beman-tidy: Complete the tool and integrate it into Beman infrastructure](#beman-tidy-complete-the-tool-and-integrate-it-into-beman-infrastructure)
    - [Description](#description-1)
    - [Reading \& Related Material](#reading--related-material-1)
  - [std::execution - Enhancements (beman.execution \& friends)](#stdexecution---enhancements-bemanexecution--friends)
    - [Description](#description-2)
    - [Reading \& Related Material](#reading--related-material-2)
  - [std::env - Portable environment variables API (beman.env)](#stdenv---portable-environment-variables-api-bemanenv)
    - [Description](#description-3)
    - [Reading \& Related Material](#reading--related-material-3)
  - [Concepts in Beman libraries: guidelines and implementation](#concepts-in-beman-libraries-guidelines-and-implementation)
    - [Description](#description-4)
    - [Reading \& Related Material](#reading--related-material-4)

## The Beman Project @ GSoC

Thank you for your interest in participating in [Google Summer of Code 2026 (GSoC26)](https://summerofcode.withgoogle.com/programs/2026)!

The Beman Project is a modern C++ libraries initiative: "Tomorrow's C++ Standard Libraries Today!"
It hosts implementations targeting current and upcoming C++ Standards, including proposals for the C++ Standard library and related tooling.
Contributing here means working on production-quality C++ libraries, ISO Standards alignment, and open-source library development, but also cutting-edge tooling and infrastructure.

## Mentors of the projects

The people listed below may mentor Beman@GSoC projects. A dedicated mentor for your project is assigned once your application is accepted and the coding period starts. **Before applying**, we encourage you to get in touch with us (e.g. on [Discourse](https://discourse.bemanproject.org/) or the [**#gsoc** channel](https://discord.com/channels/1457903855898460405/1470578839540465970) on [Discord](https://discord.com/invite/BKpNyJgSbm)) to discuss the project you are interested in and ask questions.

| Mentor | Email |
|--------|-------|
| [Darius Neațu](https://github.com/neatudarius)  | neatudarius@gmail.com         |
| [Dietmar Kühl](https://github.com/dietmarkuehl) | dietmar.kuehl@gmail.com       |
| [Eddie Nolan](https://github.com/ednolan)       | EddieJNolan@gmail.com         |
| [Inbal Levi](https://github.com/inbal2l)        | sinbal2lextra@gmail.com       |
| [Jeff Garland](https://github.com/JeffGarland)  | jeff@crystalclearsoftware.com |
| [Radu Nichita](https://github.com/RaduNichita)  | radunichita99@gmail.com       |

## The Beman Project Ideas

Below is a list of open projects for the Beman Project which can be developed as part of GSoC26.

---

### Beman implementation of P2980: Physical quantities and units (beman.units)

| | |
|-|-|
| **Difficulty** | 3/5 |
| **Project Size** | Medium (175 hours) |
| **Maximum instances** | 1 |
| **Constraints/requirements** | strong C++ skills, familiarity with physical quantities/units (e.g. [mp-units](https://github.com/mpusz/mp-units), [Boost.Units](https://www.boost.org/doc/libs/1_83_0/doc/html/boost_units.html)), and C++ standardization. |

#### Description

[P2980R0](https://open-std.org/jtc1/sc22/wg21/docs/papers/2023/p2980r0.html) is a proposal for C++26 that outlines the motivation, scope, and plan for a physical quantities and units library: type-safe quantities and units, affine space, I/O, and extensibility. This project aims to provide a **Beman-style implementation** of that design and to experiment with implementation options that could inform the ISO C++ Standard.

Existing implementations include [mp-units](https://github.com/mpusz/mp-units) (reference implementation for the proposal) and [Boost.Units](https://www.boost.org/doc/libs/1_83_0/doc/html/boost_units.html). A Beman implementation would follow the [Beman Standard](https://github.com/bemanproject/beman/blob/main/docs/beman_standard.md), align with P2980 / the evolving C++ Standard design, and serve as a testbed for implementation choices.

Deliverables could include:

1. **Design and implement beman.units** - Core types and operations for quantities and units (e.g. quantity, unit, dimensions), following P2980 and the Beman Standard.
2. **Experiment with implementation options** - Try different design choices (e.g. representation, dimensions, I/O) and document trade-offs; compare with mp-units and Boost.Units where useful.
3. **Document and test** - Document the API, portability, and limitations; add tests and examples.

Success will give the community an alternative implementation to experiment with and will help inform the standardization of a physical quantities and units library for C++26/C++29.

#### Reading & Related Material

* [P2980R0](https://open-std.org/jtc1/sc22/wg21/docs/papers/2023/p2980r0.html) - A motivation, scope, and plan for a physical quantities and units library (C++26)
* [mp-units](https://github.com/mpusz/mp-units) - Reference implementation for the proposal
* [Boost.Units](https://www.boost.org/doc/libs/1_83_0/doc/html/boost_units.html) - Boost physical quantities and units library
* [exemplar](https://github.com/bemanproject/exemplar) - Template library for new Beman libraries
* [Beman Project](https://bemanproject.org/) and [Beman Standard](https://github.com/bemanproject/beman/blob/main/docs/beman_standard.md)

---

### beman-tidy: Complete the tool and integrate it into Beman infrastructure

| | |
|-|-|
| **Difficulty** | 3/5 |
| **Project Size** | Variable (175 or 350 hours) |
| **Maximum instances** | 2 |
| **Constraints/requirements** | Python and C++; familiarity with CMake/build systems, CI (e.g. GitHub Actions), and the [Beman Standard](https://github.com/bemanproject/beman/blob/main/docs/beman_standard.md). |

#### Description

[beman-tidy](https://github.com/bemanproject/beman-tidy) is a tool aimed at The Beman Project contributors to check (`--dry-run`) and apply (`--fix-inplace`) the [Beman Standard](https://github.com/bemanproject/beman/blob/main/docs/beman_standard.md) to their repositories.

Only about 50% of the planned features are implemented today. The project has several phases:

1. **Complete the tool** - Implement the remaining features so that beman-tidy fully covers the Beman Standard. Examples of missing features include: CMake-related checks, C++ in-source checks, etc.
2. **Validate on exemplar** - Run beman-tidy on the [exemplar](https://github.com/bemanproject/exemplar) project and fix any gaps (in the tool or in the Beman Standard).
3. **Run on all Beman libraries** - Apply beman-tidy across all [Beman libraries](https://bemanproject.org/libraries); fix issues and improve the tool as needed.
4. **Integrate into infrastructure** - Make beman-tidy part of the Beman Project infrastructure and run it on CI (e.g. GitHub Actions) on every pull request.

Success will give contributors a single, automated way to keep repositories aligned with the Beman Standard and will improve consistency across the project.

#### Reading & Related Material

* [beman-tidy](https://github.com/bemanproject/beman-tidy) ([PyPI](https://pypi.org/project/beman-tidy/))
* The [Beman Standard](https://github.com/bemanproject/beman/blob/main/docs/beman_standard.md) and the [Beman Library Maturity Model](https://github.com/bemanproject/beman/blob/main/docs/beman_library_maturity_model.md)
* [exemplar](https://github.com/bemanproject/exemplar) - Template library for new Beman libraries
* [Beman Project](https://bemanproject.org/) and [Beman libraries](https://bemanproject.org/libraries)

---

### std::execution - Enhancements (beman.execution & friends)

| | |
|-|-|
| **Difficulty** | 4/5 |
| **Project Size** | Large (350 hours) |
| **Maximum instances** | 2 |
| **Constraints/requirements** | strong C++ skills, familiarity with asynchronous programming, C++26 / P2300 sender–receiver model, and the [std::execution](https://wg21.link/p2300) specification. |

#### Description

[std::execution](https://wg21.link/p2300) is the vocabulary for asynchronous work in C++. [beman.execution](https://github.com/bemanproject/execution) is an implementation of this specification. The available tools currently specified are known to be incomplete. A project could create additional components to cover real-life use-cases. Some of the data structures and algorithms you implement could later be proposed for standardization.

The project could follow phases such as:

1. **Implement additional data structures** - A concurrent queue, a ring buffer, or similar building blocks for async pipelines.
2. **Implement missing algorithms** - Algorithms such as `when_any`, `sequence`, `repeat`, or refinements of existing algorithms in the execution model.
3. **Document, test, and align** - Ensure components are well-documented and tested, and align with the evolving std::execution design. Identify which components might be candidates for the C++ Standard.
4. **Draft a standardization proposal for C++29** - Draft and submit a WG21 paper (or contribute to an existing one) proposing one or more of the implemented components for C++29.

Success will make beman.execution more usable for real-world async C++ code and will align it better with the evolving std::execution design; some of the work may feed into future standardization.

#### Reading & Related Material

* [beman.execution](https://github.com/bemanproject/execution), [beman.net](https://github.com/bemanproject/net), [beman.task](https://github.com/bemanproject/task).
* [P2300 std::execution](https://wg21.link/p2300) - C++ Working Draft model (soon to be C++26)
* [exemplar](https://github.com/bemanproject/exemplar) - Template library for new Beman libraries
* [Beman Project](https://bemanproject.org/) and [Beman libraries](https://bemanproject.org/libraries)

---

### std::env - Portable environment variables API (beman.env)

| | |
|-|-|
| **Difficulty** | 4/5 |
| **Project Size** | Large (350 hours) |
| **Maximum instances** | 2 |
| **Constraints/requirements** | strong C++ skills, familiarity with platform APIs (POSIX, Windows), and C++ Standardization process (or eager to learn). |

#### Description

There is no standard C++ portable API for manipulating environment variables. The C++ Standard provides only `std::getenv()` (from `<cstdlib>`) for reading; setting, unsetting, or enumerating variables relies on platform-specific APIs (`setenv`/`unsetenv` on POSIX, `SetEnvironmentVariable` on Windows), which are not portable. A portable API would benefit cross-platform applications, build tooling, and tests.

The project consists of:

1. **Implement a portable API - beman.env** - Design and implement a C++ library that provides a portable interface for getting, setting, unsetting, and enumerating environment variables across major platforms (e.g. Linux, macOS, Windows).
2. **Compare with well-known implementations** - Review and document how beman.env relates to existing solutions (e.g. [Boost.Process](https://www.boost.org/doc/libs/master/doc/html/boost/process/env.html) environment handling, platform-specific APIs). Identify gaps, design choices, and improvements to inform the API and the proposal.
3. **Test and verify on various environments** - Run the library on multiple platforms and toolchains; fix portability issues and document behavior and limitations.
4. **Draft a standardization proposal for C++29** - Write a WG21 paper (or contribute to an existing one) proposing a portable environment-variables API for the C++ Standard (e.g. for C++29).

Success will give users a single, portable way to work with environment variables in C++ and will provide a concrete basis for a future `std::env` or similar facility.

#### Reading & Related Material

* [std::getenv](https://en.cppreference.com/w/cpp/utility/program/getenv) - Current standard API (read-only)
* [Boost.Process environment](https://www.boost.org/doc/libs/master/doc/html/boost/process/env.html) - Boost environment handling (e.g. for child processes)
* [exemplar](https://github.com/bemanproject/exemplar) - Template library for new Beman libraries
* [Beman Project](https://bemanproject.org/) and [Beman libraries](https://bemanproject.org/libraries)

---

### Concepts in Beman libraries: guidelines and implementation

| | |
|-|-|
| **Difficulty** | 2/5 |
| **Project Size** | Medium (175 hours) |
| **Maximum instances** | 1 |
| **Constraints/requirements** | C++ concepts (C++20), familiarity with the C++ Standard and Beman libraries; willingness to apply guidelines across multiple repositories (coding). |

#### Description

Define guidelines for using *concepts* in Beman libraries so that newcomers who want to write a paper (or contribute a library) as part of Beman have clear, consistent guidance. The guidelines should cover when to use exposition-only concepts vs. real (standard-deduced) concepts, and how to align with the C++ standard. The project **includes coding**: the created guidelines must be implemented and applied across all existing Beman libraries.

Deliverables could include:

1. **Document guidelines** - Write a guide (e.g. in the [beman](https://github.com/bemanproject/beman) repo docs) that explains concepts usage: exposition-only vs. real concepts, naming, and how to derive practice from the standard.
2. **Examples and alignment** - Provide examples from existing Beman libraries and from the standard; document recommended patterns for new papers and libraries.
3. **Apply guidelines in all existing Beman libraries** - Implement the guidelines in code: update [Beman libraries](https://bemanproject.org/libraries) to use concepts consistently (exposition-only vs. real, naming, etc.) according to the guide. This involves opening pull requests across the relevant repositories.

Success will make it easier for contributors to use concepts consistently in Beman libraries and in standardization work, and will bring existing libraries in line with the new guidance.

#### Reading & Related Material

* [Beman Project](https://bemanproject.org/) and [beman](https://github.com/bemanproject/beman) repo (docs, Beman Standard)
* [exemplar](https://github.com/bemanproject/exemplar) - Template library for new Beman libraries
* C++20 concepts and the C++ Standard (e.g. [cppreference concepts](https://en.cppreference.com/w/cpp/language/constraints))

---


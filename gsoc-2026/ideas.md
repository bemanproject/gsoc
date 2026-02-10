---
title: Google Summer of Code 2026 Ideas List
---

## The Beman Project Ideas

Thank you for your interest in participating in [Google Summer of Code 2026 (GSoC26)](https://summerofcode.withgoogle.com/programs/2026)!

The Beman Project is a modern C++ libraries initiative: "Tomorrow's C++ Standard Libraries Today!"
It hosts implementations targeting current and upcoming C++ standards, including proposals for the C++ standard library and related tooling.
Contributing here means working on production-quality C++, standards alignment, and open source library development.

## Mentors of the projects

Mentors will be assigned when the project is initiated. Please feel free to reach out beforehand to discuss the project.

| Mentor | Email |
|--------|-------|
| [Darius Neațu](https://github.com/neatudarius) | neatudarius@gmail.com |
| [Dietmar Kühl](https://github.com/camio) | dietmar.kuehl@gmail.com |
| [Eddie Nolan](https://github.com/ednolan) | EddieJNolan@gmail.com |
| [Inbal Levi](https://github.com/inbal2l) | sinbal2lextra@gmail.com |
| [Jeff Garland](https://github.com/JeffGarland) | jeff@crystalclearsoftware.com |
| [Radu Nichita](https://github.com/RaduNichita) | radunichita99@gmail.com |

Below are a list of open projects for the Beman Project which can be developed as part of GSoC26.

---

### beman-tidy: Complete the tool and integrate it into Beman infrastructure

| | |
|-|-|
| **Difficulty** | 3/5 |
| **Project Size** | Variable (175 or 350 hours) |
| **Maximum instances** | 1 |
| **Constraints/requirements** | Python and C++; familiarity with CMake/build systems, CI (e.g. GitHub Actions), and the [Beman Standard](https://github.com/bemanproject/beman/blob/main/docs/beman_standard.md). |

#### Description

[beman-tidy](https://github.com/bemanproject/beman-tidy) is a tool aimed at The Beman Project contributors to check (`--dry-run`) and apply (`--fix-inplace`) the [Beman Standard](https://github.com/bemanproject/beman/blob/main/docs/beman_standard.md) to their repositories.

Only about 50% of the planned features are implemented today. The project has several phases:

1. **Complete the tool** — Implement the remaining features so that beman-tidy fully covers the Beman Standard.
2. **Validate on exemplar** — Run beman-tidy on the [exemplar](https://github.com/bemanproject/exemplar) project and fix any gaps (in the tool or in the standard).
3. **Run on all Beman libraries** — Apply beman-tidy across all [Beman libraries](https://bemanproject.org/libraries); fix issues and improve the tool as needed.
4. **Integrate into infrastructure** — Make beman-tidy part of the Beman Project infrastructure and run it on CI (e.g. GitHub Actions) on every pull request.

Success will give contributors a single, automated way to keep repositories aligned with the Beman Standard and will improve consistency across the project.

#### Reading & Related Material

* [beman-tidy](https://github.com/bemanproject/beman-tidy) ([PyPI](https://pypi.org/project/beman-tidy/))
* [The Beman Standard](https://github.com/bemanproject/beman/blob/main/docs/beman_standard.md) and the [Beman Library Maturity Model](https://github.com/bemanproject/beman/blob/main/docs/beman_library_maturity_model.md)
* [exemplar](https://github.com/bemanproject/exemplar) — Template library for new Beman libraries
* [Beman Project](https://bemanproject.org/) and [Beman libraries](https://bemanproject.org/libraries)

---


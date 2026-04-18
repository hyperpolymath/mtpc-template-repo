<!-- SPDX-License-Identifier: PMPL-1.0-or-later -->
<!-- Copyright (c) 2026 Jonathan D.A. Jewell (hyperpolymath) <j.d.a.jewell@open.ac.uk> -->

# TOPOLOGY.md — mtpc-template-repo

## Purpose

MTPC (Modular Template for Project Creation) is the canonical RSR template for hyperpolymath projects. It provides dual-track architecture: human-readable orientation at the root level and machine-readable metadata in subdirectories, including ABI/FFI standards (Idris2 + Zig) and standardized CI/CD workflows.

## Module Map

```
mtpc-template-repo/
├── src/abi/             # Idris2 ABI interface definitions
├── ffi/zig/             # Zig FFI implementation
├── generated/abi/       # Auto-generated C headers
├── container/           # Containerfile + container build setup
├── docs/                # Documentation structure
├── .machine_readable/   # SCM checkpoint files
├── .github/workflows/   # RSR standard workflows (17 total)
└── Justfile            # Build orchestration recipe
```

## Data Flow

```
[ABI Definition (Idris2)] ──► [Header Generation] ──► [FFI Implementation (Zig)]
                                                            ↓
                                                   [Cross-Platform Build]
                                                   [Language Bindings]
```

## Initialization

Run `just init` after cloning to set up project-specific recipes and verify all required files are present (workflows, checkpoint files, build system).

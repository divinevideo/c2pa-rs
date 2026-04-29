# Repository Guidelines

## Project Structure & Module Organization
- Core Rust crates live across `sdk/`, `cli/`, `c2pa_c_ffi/`, `macros/`, `export_schema/`, and helper tooling like `make_test_images/`.
- Documentation lives in `docs/`, with project metadata at the repo root.
- Keep changes scoped to the relevant crate or subsystem. Avoid broad cross-workspace refactors unless they are intentionally coordinated.

## Build, Test, and Development Commands
- Use the repo’s existing `Makefile` and crate-specific workflows where possible.
- `cargo test`: run the Rust test suite.
- `cargo check`: run a fast compile-only validation pass.
- Follow the project’s existing contributing and release documentation when touching release or support-tier behavior.
- If you change public APIs or CLI behavior, update the relevant docs and examples alongside the code.

## Coding Style & Naming Conventions
- Use idiomatic Rust with explicit error handling and clear crate boundaries.
- Prefer focused, subsystem-specific changes over broad shared utility churn.
- Keep PRs tightly scoped. Do not mix unrelated cleanup, formatting churn, or speculative refactors into the same change.
- Temporary or transitional code must include `TODO(#issue):` with the tracking issue for removal.

## Pull Request Guardrails
- PR titles must use Conventional Commit format: `type(scope): summary` or `type: summary`.
- Set the correct PR title when opening the PR. Do not rely on fixing it afterward.
- If a PR title changes after opening, verify that the semantic PR title check reruns successfully.
- PR descriptions must include a short summary, motivation, linked issue, and manual test plan.
- Changes to public APIs, CLI behavior, supported formats, or signing/validation flows should include representative usage or migration notes when helpful.

## Sensitive Information
- Do not publish private keys, certificates, sensitive media, or customer-identifying samples.
- Public issues, PRs, branch names, screenshots, and descriptions must not mention corporate partners, customers, brands, campaign names, or other sensitive external identities unless a maintainer explicitly approves it.

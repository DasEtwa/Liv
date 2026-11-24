# AGENTS.md — Liv

Instructions for coding agents and contributors working in this repository.

## 1. Project direction

- Liv is a Rust-first research project for small and medium-sized language models.
- PackTok (https://github.com/DasEtwa/PackTok) is the intended native tokenizer. Do not silently substitute another tokenizer or duplicate its core implementation.
- Keep the model, training and inference core in Rust. External tooling may be used when justified; do not introduce a mandatory Python runtime for the core without maintainer approval.
- Prefer small, testable, understandable components over speculative abstractions. Do not assume a specific architecture, GPU backend, parameter count or release date before it is documented.
- Preserve the Apache-2.0 licensing approach. Treat RULES.md as the official model's intended behavior, not as a downstream license restriction.

## 2. Working with the repository

- Read existing code, documentation and scoped instructions before editing. Check the working tree and preserve unrelated user changes.
- Keep changes focused. Do not perform destructive operations, rewrite Git history, publish releases, upload checkpoints or push changes unless authorized.
- Do not claim functionality, benchmark results or test success that has not been verified.
- Prefer explicit errors, typed configuration, clear module boundaries and deterministic tests where practical.
- Avoid unnecessary dependencies and unsafe Rust. When unsafe code is genuinely needed, document the invariants and provide targeted tests.
- Do not hardcode secrets, private paths, account identifiers or credentials. Do not introduce telemetry or outbound network behavior without explicit approval and documentation.
- Preserve cross-platform support where practical; document platform-specific limitations.

## 3. Rust and validation

Once a Cargo workspace exists, use the relevant commands from the repository root:

```sh
cargo fmt --all -- --check
cargo clippy --workspace --all-targets -- -D warnings
cargo test --workspace
```

Run targeted tests for changed components as well. Use feature-specific and GPU tests where the environment supports them. Do not fabricate results or silently skip failures; report exact commands, outcomes and unavailable hardware or dependencies. At the current documentation-only stage, these commands are not yet applicable.

For tokenizer or model changes, test compatibility, tensor shapes, invalid inputs, numerical stability and serialization as relevant. Pin compatible versions and record checkpoint format changes. For performance claims, record hardware, backend, precision, workload and measurement method; distinguish training from inference and throughput from latency.

## 4. Training data and reproducibility

- Use only data with documented provenance and a reviewed basis for the intended use; do not assume that publicly accessible data is freely reusable.
- Record source, version, license or other documented basis, attribution, processing steps and exclusions. Do not import unreviewed web dumps.
- Exclude secrets, unnecessary personal data, exploitative material and unlawfully obtained content; review uncertain sources before ingestion.
- Deduplicate and maintain independent training, validation and evaluation splits. Avoid benchmark leakage.
- Record configuration, random seeds, tokenizer version, code revision, dataset manifest, environment and checkpoint metadata when training.
- Do not commit large datasets, checkpoints or machine-local artifacts to normal Git history; agree on an artifact storage strategy first.
- Report incomplete provenance, nondeterminism or missing metrics explicitly.

## 5. Alignment and safety

- Use RULES.md as the source of truth for official model behavior. Keep policy, training examples and evaluations consistent and versioned.
- Distinguish harmful operational assistance from benign education, fiction, legitimate security research and game modding. Do not rely solely on keyword blocking.
- Include positive examples, restricted responses, refusals, ambiguous requests and multilingual regression tests. Measure both harmful compliance and over-refusal.
- Keep sensitive evaluation material appropriately controlled; never include real credentials, victim identifiers or unnecessarily harmful instructions in public fixtures.
- Document changes to intended behavior and their observed effects. Do not claim that alignment is a security boundary or that downstream models must retain it.

## 6. Completion checklist

Before handing off a change, summarize files changed, rationale, tests run and their actual results, unresolved issues, assumptions and any compatibility or licensing implications. Keep README and other documentation aligned with verified implementation status.

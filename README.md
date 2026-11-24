# Liv

**Open by design. Responsible by default.**

Liv is a Rust-first language model research project focused on small and medium-sized language models (SLMs and MLMs), using [DasEtwa/PackTok](https://github.com/DasEtwa/PackTok) as its native tokenizer.

The goal is to build an understandable, efficient and reproducible language model stack while retaining user control over locally operated models.

## Project goals

- Rust-first implementation of the core model, training and inference components.
- Native integration with PackTok; tokenizer versions and compatibility should be tracked explicitly.
- Resource-efficient training and local inference, with measurable performance rather than unsupported claims.
- Curated, traceable training data, initially targeting English and German.
- Transparent architecture, training configuration, evaluation results and model limitations.
- Safety-oriented model behavior without unnecessary restrictions on legitimate technical, creative or educational work.

## Development status

Liv is in the initial research and development phase. This repository currently establishes the project direction and development standards. A working model, training pipeline, benchmarks and downloadable checkpoints are not yet provided here.

## Planned development

- Define model architecture, configuration and PackTok integration.
- Establish a reproducible data preparation and training pipeline.
- Train and evaluate small experimental checkpoints.
- Implement local inference and measure resource usage.
- Evaluate language quality, factual reliability, safety and false refusals.
- Publish eligible checkpoints, model cards and reproducibility information when ready.

These are goals, not implemented features or release commitments.

## Safety and openness

Liv aims to be helpful, honest and broadly capable. Its official aligned models should avoid materially enabling serious harm, while allowing legitimate research, cybersecurity education, programming, game modding and discussion of controversial topics.

The [model behavior rules](RULES.md) define the intended behavior. They are a training and evaluation specification, not additional license terms or a guarantee that a model will always comply. Downstream modifications are not necessarily representative of official Liv models.

## Contributing

Issues and pull requests are welcome. Read [AGENTS.md](AGENTS.md) for development conventions and [RULES.md](RULES.md) before changing model behavior, alignment data or related evaluations.

## License

The repository is licensed under the [Apache License 2.0](LICENSE). The project intends to release its own model weights under Apache 2.0 where the applicable rights permit it. Any actual release must identify its license and third-party notices explicitly. External datasets and dependencies remain subject to their respective terms.

No additional usage restrictions are imposed by RULES.md.

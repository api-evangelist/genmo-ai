# Genmo (genmo-ai)

Genmo is a San Francisco research lab building open-source video generation models. Its flagship release, **Mochi 1**, is an Apache-2.0 licensed ~10B-parameter text-to-video diffusion model (AsymmDiT architecture) with strong prompt adherence and high-fidelity 480p motion.

**Honest access note:** Genmo does **not** publish a first-party hosted developer REST API. There is no developer or API portal on genmo.ai, and the pricing page sells consumer web-app credits, not API access. Programmatic access to Mochi comes in three forms:

1. **Open source, self-hosted (first-party).** Download the model and run it yourself. The repo ships a "simple composable API" in Python (`MochiSingleGPUPipeline`), a CLI (`cli.py`), a Gradio UI, and native ComfyUI support. This is a local inference library, not a network service, and single-GPU inference needs ~60GB VRAM.
2. **Third-party hosted inference (partners).** Mochi is served as a pay-per-run API by platforms such as **Replicate** (`genmoai/mochi-1`, ~$0.42/run on H100) and **fal.ai** (`fal-ai/mochi-v1`, now listed deprecated). These APIs are operated by the partners, not by Genmo.
3. **Consumer web app / Playground.** A credit-based product at [genmo.ai/play](https://www.genmo.ai/play) for generating videos in the browser (not a developer API).

The hosted endpoints documented in this catalog are **modeled from partner documentation** (`endpointsModeled: true`) and are not Genmo-operated. No Genmo REST API is fabricated here.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/genmo-ai/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/genmo-ai/refs/heads/main/apis.yml)

## Tags

- Video Generation
- AI Video
- Generative AI
- Text-to-Video
- Open Source
- Mochi
- Diffusion Model

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Genmo Mochi Pipeline (Self-Hosted OSS)

The first-party access surface is the open-source model itself. The Mochi repo (Apache-2.0) exposes a composable Python pipeline (`MochiSingleGPUPipeline`, built from `T5ModelFactory`, `DitModelFactory`, `DecoderModelFactory`) invoked with prompt, resolution, `num_frames`, inference steps, guidance scale, and seed to generate 480p video locally. Also runnable via `cli.py`, a Gradio UI, and ComfyUI. This is a code library / local inference pipeline, not a hosted network API.

- **Human URL:** [https://github.com/genmoai/mochi](https://github.com/genmoai/mochi)
- **Endpoints Modeled:** yes (local Python pipeline; no network endpoint)

#### Tags

- Video Generation
- Text-to-Video
- Open Source
- Self-Hosted

#### Properties

- [Documentation](https://github.com/genmoai/mochi)
- [Source Code / Weights](https://huggingface.co/genmo/mochi-1-preview)
- [Blog](https://www.genmo.ai/blog/mochi-1-a-new-sota-in-open-text-to-video)

### Mochi 1 on Replicate (Third-Party Hosted)

Third-party hosted access to Mochi 1 via Replicate's predictions API (model `genmoai/mochi-1`). Runs on Nvidia H100, ~$0.42/run, typically under 5 minutes at 480p, using Replicate's async submit + poll/webhook pattern. Operated by Replicate, not Genmo.

- **Human URL:** [https://replicate.com/genmoai/mochi-1](https://replicate.com/genmoai/mochi-1)
- **Base URL:** `https://api.replicate.com/v1`
- **Endpoints Modeled:** yes (from Replicate docs)

#### Tags

- Video Generation
- Text-to-Video
- Hosted Inference
- Third Party

#### Properties

- [Documentation](https://replicate.com/genmoai/mochi-1)
- [API Reference](https://replicate.com/genmoai/mochi-1/api)

### Mochi v1 on fal.ai (Third-Party Hosted)

Third-party hosted access to Mochi via fal.ai (model `fal-ai/mochi-v1`) using fal's queue API — submit with `prompt`, `negative_prompt`, `seed`, `enable_prompt_expansion`, and `num_frames`, then check status and fetch the video URL. **Note:** fal.ai lists this endpoint as deprecated / no longer supported as of the review date. Operated by fal.ai, not Genmo.

- **Human URL:** [https://fal.ai/models/fal-ai/mochi-v1](https://fal.ai/models/fal-ai/mochi-v1)
- **Endpoints Modeled:** yes (from fal.ai docs; deprecated)

#### Tags

- Video Generation
- Text-to-Video
- Hosted Inference
- Third Party

#### Properties

- [API Reference](https://fal.ai/models/fal-ai/mochi-v1/api)

## Common Properties

- [GitHub Organization](https://github.com/genmoai)
- [LinkedIn](https://www.linkedin.com/company/genmoai)
- [Website](https://www.genmo.ai)
- [Documentation](https://github.com/genmoai/mochi)
- [Playground](https://www.genmo.ai/play)
- [Plans](plans/genmo-ai-plans-pricing.yml)
- [Blog](https://www.genmo.ai/blog)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

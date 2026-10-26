# Genmo (genmo-ai)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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

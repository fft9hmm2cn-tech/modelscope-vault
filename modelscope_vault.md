# ModelScope Vault — Chinese Open-Weight Goldmine (as of 2026-09-29)

> Resource dump from voice-mode gathering. Continue on desktop. Nothing lost.
> **Scope rule (Philippines / outside China):** Only models that actually download and run here. Chinese-only / China-restricted stuff (Xiaomi MiMo desktop, some Hunyuan community licenses, Huawei openPangu) is excluded or flagged — don't waste bandwidth on it.

## 0. Region reality check (PH)
- ModelScope servers sit in China → latency is higher than HF, but most public weights still pull fine via `modelscope` CLI / `snapshot_download`.
- **Exclude:** Xiaomi MiMo (desktop app geo-blocked; weights are MIT but the ModelScope-only packaging is flaky from PH — use HF mirror instead), Huawei openPangu (EU-excluded license, not relevant but skip), older Tencent Hunyuan community-license models that carve out EU/UK/KR (Hy3 full Apache 2.0 is fine).
- **Prefer:** MIT / Apache 2.0 models that also live on Hugging Face — dual-hosted = fallback if ModelScope stalls.
- International hub: https://www.modelscope.ai (English). Domestic: https://www.modelscope.cn.

## 1. Frontier Chinese Models (ModelScope-hosted, day-0, PH-reachable)

### LLMs / Reasoning — MUST SCRAPE
- **MiniMax-M3** (MiniMax) — 428B / 23B active, native multimodal (image+text), 1M context, MiniMax Community License. #2 open-weight on some indices. ModelScope: `MiniMax/MiniMax-M3`. HF mirror exists.
- **MiniMax-M3-MXFP8** — quantized variant, ~444 GB, same license. `MiniMax/MiniMax-M3-MXFP8`.
- **DeepSeek-V4.1-Flash** (deepseek-ai) — 552B MoE, 8B/16B active, 1M context, native image+text. MIT. Day-0 in ms-swift. `deepseek-ai/DeepSeek-V4.1-Flash`.
- **DeepSeek-V4-Pro** — 1.6T / 49B active, MIT, 1M context. `deepseek-ai/DeepSeek-V4-Pro-0813`.
- **DeepSeek-V4-Flash-Vision-Exp** — vision experiment. `deepseek-ai/DeepSeek-V4-Flash-Vision-Exp`.
- **GLM-5.3** (ZhipuAI/Z.ai) — 753B MoE (40B active), 1M context. Custom license (check revenue clause). `ZhipuAI/GLM-5.3`.
- **GLM-5.3-Flash** — 320B / 18B active, MIT, near-frontier, cheapest point on the Pareto. `ZhipuAI/GLM-5.3-Flash`.
- **GLM-5.2** — 753B, MIT, "pure open, no region restriction". `ZhipuAI/GLM-5.2`.
- **Qwen3.8-27B** (Qwen) — 27.78B dense, Apache 2.0, best consumer-GPU coding model (SWE-bench ~77). `Qwen/Qwen3.8-27B`. HF mirror.
- **Qwen3.8-Max** — 2.4T flagship, custom license (revenue share above $50M). `Qwen/Qwen3.8-Max`.
- **Qwen3.5-397B-A17B / 122B-A10B / 35B-A3B** — Apache 2.0 family, multimodal. `Qwen/Qwen3.5-*`.
- **Step-3.7-Flash** (StepFun) — 201B, Apache 2.0, image-text-to-text. `stepfun-ai/Step-3.7-Flash`.
- **Kimi-K2.6** (moonshotai) — 170B, Modified MIT, strong agentic/coding. `moonshotai/Kimi-K2.6`. (K3 2.8T is huge — scrape only if you have the hardware; license has revenue clause.)
- **Intern-S2-397B** (Shanghai_AI_Laboratory) — 403B, image-text-to-text, Apache 2.0. `Shanghai_AI_Laboratory/Intern-S2-397B`.
- **Atria-Dawn-Preview** (Shanghai_AI_Laboratory) — 753B. `Shanghai_AI_Laboratory/Atria-Dawn-Preview`.
- **NeoHorse-Jev-4B** (TokenRhythm) — prefill-only decision model, outputs probabilities not text. 77.70 across decision benchmarks. Apache 2.0. Great for routing/agents.
- **Ternary-Bonsai-2-27B-gguf** (prism-ml) — 26.9B GGUF, Apache 2.0. Local-friendly.
- **Xing4.0-29B-A4B** (XingChen-AGI) — 31B, Apache 2.0. `XingChen-AGI/Xing4.0-29B-A4B`.

### Image / Video / Audio — MUST SCRAPE
- **Qwen-Image-2.1** (Qwen) — 7B, native RGBA transparency, text-to-image + editing, up to 10 refs. Sept 21 2026. `Qwen/Qwen-Image-2.1`.
- **Qwen-Image-2.1-LayerExtract / LayerRemove** (DiffSynth-Studio) — LoRAs to extract/remove objects as transparent layers. Apache 2.0.
- **Qwen-Image-2.1-Fun-Controlnet-Union** (pai) — 8 controls (Canny/Depth/Pose/etc) + inpainting in one checkpoint. Qwen Research License.
- **DiffSynth-Music** — controllable music gen (beats/vocals/accompany/prosody/reference), based on ACE-Step.
- **TeleOCR** (XingChen-AGI) — 1.42B, document parsing, Qwen2.5-VL base. `XingChen-AGI/TeleOCR`.
- **Unlimited-OCR** (PaddlePaddle/Baidu) — 3.34B, multilingual, MIT. `PaddlePaddle/Unlimited-OCR`.
- **GLM-OCR** (ZhipuAI) — 0.9B–1.3B, 95%+ OmniDocBench, Apache 2.0. Top OCR download volume.
- **HunyuanOCR** (Tencent-Hunyuan) — 1.1B. Check license (older community license excludes EU/UK/KR — verify before scrape).
- **Hy3 / Hy4-preview** (Tencent-Hunyuan) — 295B / 770B MoE, Apache 2.0 (Hy3), no geo carve-out. `Tencent-Hunyuan/Hy3`.
- **Hy-MT2-*** (Tencent-Hunyuan) — translation models, multilingual. `Tencent-Hunyuan/Hy-MT2-*`.
- **Krea-2-Turbo** (krea) — 30.2B text-to-image, krea-2-community-license. `krea/Krea-2-Turbo`.
- **LingBot-Video** (Robbyant) — MoE 30B-A3B + dense 1.3B variants.
- **Audio8-ASR-Infinite** (Edge0) — rolling KV cache, unlimited-length CN/EN transcription, 480ms delay, 1.75 CER AISHELL-1. Apache 2.0. Sept 29.
- **Baichuan** family (Baichuan-AI) — ModelScope-primary for several variants; dual-publish where possible. Search `Baichuan-AI/` on ModelScope.

### Distills / Community (the "degenerate" stuff) — MUST SCRAPE
- **Merkyor/Qwen3.6-27B-DSV4Pro-Thinking-Distill** — 27.78B, Apache 2.0.
- **Merkyor/Qwen3.6-35B-A3B-DSV4Pro-Thinking-Distill-GGUF** — 35.51B GGUF.
- **Jackrong/Qwen3.5-9B-DeepSeek-V4-Flash-GGUF**
- **Jackrong/Qwen3.5-9B-GLM5.1-Distill-v1-GGUF**
- **lightx2v/Qwen-Image-Lightning** & **Qwen-Image-Edit-2511-Lightning** — fast LoRAs.
- **lightx2v/Wan2.2-Distill-Models** — 257B LoRA video distill.
- **Boogu/Boogu-Image-0.1-Edit** — 19.14B, Apache 2.0, CN/EN.
- **orcarouter/** uncensored GGUFs (Qwen3.8-27B, GLM-5.3-Flash) — community mirrors for local use.
- **unsloth/Qwen3.6-27B-MTP-GGUF** — GGUF for local.

## 2. Core Tooling (ModelScope-native, Chinese-devped) — MUST SCRAPE
- **ms-swift** (modelscope/ms-swift) — v4.5.3 (Sept 7 2026). Train/infer 600+ LLMs + 300+ MLLMs. Megatron-SWIFT, GRPO family (DAPO/GSPO/SAPO/CISPO/RLOO), vLLM/SGLang/LMDeploy export. Day-0 for DeepSeek-V4.1-Flash, Qwen3.8-Flash-Next, Kimi-K3, GLM-5.2.
- **FunASR** (modelscope/FunASR) — v1.4.16 (Sept 18). 170x realtime SenseVoice, speaker diarization, emotion, OpenAI-compatible API, vLLM engine. 20.5k stars. CPU faster than Whisper-on-GPU.
- **DiffSynth-Studio** (modelscope/DiffSynth-Studio) — v2.1.8. Diffusion training/inference, ComfyUI support, Qwen-Image-2.1, music, LTX-2.5, SenseNova-U1.5.
- **ModelScope Library** (pip install modelscope) — v1.40.1. Unified gateway for inference/finetune/eval.
- **EvalScope** — benchmarking framework.
- **ModelScope-Agent** — connects models to tools/apps.
- **Nexus-Gen** — unified image understanding+generation+editing.

## 3. Why ModelScope specifically (for PH)
- Day-0 Chinese model drops (before or without HF mirrors) — Qwen, GLM, DeepSeek, MiniMax, Hunyuan, Baichuan often land here first.
- GGUF/quantized community uploads for local hardware.
- ASR/OCR tuned on Chinese speech/docs (AISHELL, C-Eval, OmniDocBench) — FunASR, TeleOCR, GLM-OCR, Unlimited-OCR.
- ms-swift Megatron parallelism for training on Ascend NPUs + NVIDIA.
- 25M+ users, 170k+ models (Mar 2026), Alibaba DAMO-backed but community-driven.
- International English site: modelscope.ai.

## 4. Next actions (desktop)
- [ ] Clone/pull specific model cards via `modelscope` CLI or snapshot_download. Set `MODELSCOPE_ENDPOINT=https://www.modelscope.cn/api/v1` if the default stalls.
- [ ] Spin up ms-swift SFT on a distill (e.g. Merkyor Qwen3.6-27B) for a niche task.
- [ ] Benchmark FunASR vs Whisper on your audio.
- [ ] Try NeoHorse-Jev-4B for agent routing.
- [ ] Explore DiffSynth-Music + Qwen-Image-2.1 pipeline.
- [ ] Verify MiniMax-M3 + GLM-5.3-Flash licenses before any commercial use.

---
*Dumped 2026-09-29 from voice session. Expanded with PH scope + must-scrape list. Expand freely.*

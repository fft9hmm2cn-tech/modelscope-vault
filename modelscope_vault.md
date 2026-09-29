# ModelScope Vault — Chinese Open-Weight Goldmine (as of 2026-09-29)

> Resource dump from voice-mode gathering. Continue on desktop. Nothing lost.

## 1. Frontier Chinese Models (ModelScope-hosted, often day-0)

### LLMs / Reasoning
- **MiMo-V2.6-Pro** (XiaomiMiMo) — 1T params, 1M context, omni-modal (text/image/video/audio). Leads BenchLM Chinese ranking Sept 2026 (score 74.7). Also Flash + 9B distill variants. MIT.
- **DeepSeek-V4.1-Flash** (deepseek-ai) — 552B MoE, 8B/16B active, 1M context, native image+text. MIT. Day-0 support in ms-swift.
- **DeepSeek-V4-Pro** — 1.6T / 49B active, MIT, 1M context.
- **GLM-5.3 / GLM-5.2** (ZhipuAI/Z.ai) — 753B MoE (40B active), MIT, 1M context. #1 on some open-weight indices.
- **Kimi-K3** (moonshotai) — 2.8T / 104B active, 1M context, multimodal. Custom license.
- **Qwen3.8-Max / Qwen3.8-27B** (Qwen) — 2.4T flagship + 27B open. Apache 2.0 on 27B.
- **Step 5 Preview** (StepFun) — agentic/coding focus.
- **Atria-Dawn-Preview** (Shanghai_AI_Laboratory) — 753B.
- **Intern-S2-397B** (Shanghai_AI_Laboratory) — 403B, image-text-to-text, Apache 2.0.
- **NeoHorse-Jev-4B** (TokenRhythm) — prefill-only decision model, outputs probabilities not text. 77.70 across decision benchmarks. Apache 2.0. Great for routing/agents.
- **Ternary-Bonsai-2-27B-gguf** (prism-ml) — 26.9B GGUF, Apache 2.0. (UkisAI Swift family also cuts thinking tokens ~40-63%.)

### Image / Video / Audio
- **Qwen-Image-2.1** (Qwen) — 7B, native RGBA transparency, text-to-image + editing, up to 10 refs. Sept 21 2026.
- **Qwen-Image-2.1-LayerExtract / LayerRemove** (DiffSynth-Studio) — LoRAs to extract/remove objects as transparent layers. Apache 2.0.
- **Qwen-Image-2.1-Fun-Controlnet-Union** (pai) — 8 controls (Canny/Depth/Pose/etc) + inpainting in one checkpoint. Qwen Research License.
- **DiffSynth-Music** — controllable music gen (beats/vocals/accompany/prosody/reference), based on ACE-Step.
- **TeleOCR** (XingChen-AGI) — 1.42B, document parsing, Qwen2.5-VL base.
- **Jina-OCR-v1** (jinaai) — 3.4B MoE (570M active), 2.57 pages/sec, 91.14 OmniDocBench. CC BY-NC.
- **Audio8-ASR-Infinite** (Edge0) — rolling KV cache, unlimited-length CN/EN transcription, 480ms delay, 1.75 CER AISHELL-1. Apache 2.0. Sept 29.
- **Unlimited-OCR** (PaddlePaddle/Baidu) — 32.4k downloads, multilingual.
- **LingBot-Video** (Robbyant) — MoE 30B-A3B + dense 1.3B variants.
- **Krea-2-Turbo** (krea) — 30.2B text-to-image.

### Distills / Community (the "degenerate" stuff)
- **Merkyor/Qwen3.6-27B-DSV4Pro-Thinking-Distill** — 27.78B, Apache 2.0.
- **Merkyor/Qwen3.6-35B-A3B-DSV4Pro-Thinking-Distill-GGUF** — 35.51B GGUF.
- **Jackrong/Qwen3.5-9B-DeepSeek-V4-Flash-GGUF**
- **Jackrong/Qwen3.5-9B-GLM5.1-Distill-v1-GGUF**
- **lightx2v/Qwen-Image-Lightning** & **Qwen-Image-Edit-2511-Lightning** — fast LoRAs.
- **lightx2v/Wan2.2-Distill-Models** — 257B LoRA video distill.
- **Boogu/Boogu-Image-0.1-Edit** — 19.14B, Apache 2.0, CN/EN.
- **orcarouter/** uncensored GGUFs (Qwen3.8-27B, GLM-5.3-Flash) — community mirrors for local use.

## 2. Core Tooling (ModelScope-native, Chinese-devped)

- **ms-swift** (modelscope/ms-swift) — v4.5.3 (Sept 7 2026). Train/infer 600+ LLMs + 300+ MLLMs. Megatron-SWIFT, GRPO family (DAPO/GSPO/SAPO/CISPO/RLOO), vLLM/SGLang/LMDeploy export. Day-0 for DeepSeek-V4.1-Flash, Qwen3.8-Flash-Next, Kimi-K3, GLM-5.2.
- **FunASR** (modelscope/FunASR) — v1.4.16 (Sept 18). 170x realtime SenseVoice, speaker diarization, emotion, OpenAI-compatible API, vLLM engine. 20.5k stars. CPU faster than Whisper-on-GPU.
- **DiffSynth-Studio** (modelscope/DiffSynth-Studio) — v2.1.8. Diffusion training/inference, ComfyUI support, Qwen-Image-2.1, music, LTX-2.5, SenseNova-U1.5.
- **ModelScope Library** (pip install modelscope) — v1.40.1. Unified gateway for inference/finetune/eval.
- **EvalScope** — benchmarking framework.
- **ModelScope-Agent** — connects models to tools/apps.
- **Nexus-Gen** — unified image understanding+generation+editing.

## 3. Why ModelScope specifically
- Day-0 Chinese model drops (before or without HF mirrors).
- GGUF/quantized community uploads for local Chinese hardware.
- ASR/OCR tuned on Chinese speech/docs (AISHELL, C-Eval, OmniDocBench).
- ms-swift Megatron parallelism for training on Ascend NPUs + NVIDIA.
- 25M+ users, 170k+ models (Mar 2026), Alibaba DAMO-backed but community-driven.

## 4. Next actions (desktop)
- [ ] Clone/pull specific model cards via `modelscope` CLI or snapshot_download.
- [ ] Spin up ms-swift SFT on a distill (e.g. Merkyor Qwen3.6-27B) for a niche task.
- [ ] Benchmark FunASR vs Whisper on your audio.
- [ ] Try NeoHorse-Jev-4B for agent routing.
- [ ] Explore DiffSynth-Music + Qwen-Image-2.1 pipeline.

---
*Dumped 2026-09-29 from voice session. Expand freely.*
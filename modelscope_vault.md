# ModelScope Vault — Chinese Open-Weight Goldmine (as of 2026-09-29)

> Strongest snapshot. PH / outside-China scope.
> Hub: https://www.modelscope.cn · EN: https://www.modelscope.ai · Repo: https://github.com/fft9hmm2cn-tech/modelscope-vault

## 0. Region reality (PH)
- ModelScope origin is China. Public weights usually pull via `modelscope` CLI; if not, same ID on Hugging Face.
- **Exclude:** Xiaomi MiMo desktop (geo); Huawei openPangu (EU-excluded license); older Hunyuan *community* licenses (EU/UK/KR carve-out). **Hy3 = Apache 2.0, keep.**
- **Prefer:** MIT / Apache 2.0 + dual-hosted.

## 1. Frontier LLMs / VL — MUST SCRAPE
- **MiniMax-M3** `MiniMax/MiniMax-M3` — 428B/23B act, native MM, 1M ctx. Community License. MXFP8: `MiniMax/MiniMax-M3-MXFP8`.
- **MiniMax-M2.7** `MiniMax/MiniMax-M2.7` — 229B agent/coding predecessor.
- **DeepSeek-V4.1-Flash** `deepseek-ai/DeepSeek-V4.1-Flash` — 552B MoE, 8B/16B act, vision-from-pretrain, MIT.
- **DeepSeek-V4-Pro-0813** `deepseek-ai/DeepSeek-V4-Pro-0813` — 1.6T/49B, MIT.
- **DeepSeek-V4-Pro-DSpark** `deepseek-ai/DeepSeek-V4-Pro-DSpark` — DSpark variant, MIT.
- **DeepSeek-V4-Flash-Vision-Exp** `deepseek-ai/DeepSeek-V4-Flash-Vision-Exp`.
- **GLM-5.3** `ZhipuAI/GLM-5.3` — 753B/40B, custom license.
- **GLM-5.3-Flash** `ZhipuAI/GLM-5.3-Flash` — 320B/18B, **MIT**, daily server pick.
- **GLM-5.2** `ZhipuAI/GLM-5.2` — MIT, “no region restriction”.
- **Qwen3.8-27B** `Qwen/Qwen3.8-27B` — Apache 2.0, consumer coding king.
- **Qwen3.8-Max** `Qwen/Qwen3.8-Max` — 2.4T, custom / $50M clause.
- **Qwen3.5-*** `Qwen/Qwen3.5-397B-A17B`, `Qwen3.5-122B-A10B`, `Qwen3.5-35B-A3B`, `Qwen3.5-9B/4B/2B` — Apache, MM.
- **Qwen3-VL** family — search `Qwen/Qwen3-VL-*` (8B instruct is a download monster on HF).
- **Step-3.7-Flash** `stepfun-ai/Step-3.7-Flash` — 201B, Apache, VL.
- **Step 5 Preview** — agentic/coding; weights pending / check card before pull.
- **Kimi-K2.6** `moonshotai/Kimi-K2.6` — Modified MIT.
- **Kimi-K2.7-Code** `moonshotai/Kimi-K2.7-Code` — code/agent.
- **Kimi-K3** `moonshotai/Kimi-K3` — 2.8T, skip unless cluster + read license.
- **Intern-S2-397B** `Shanghai_AI_Laboratory/Intern-S2-397B` — Apache.
- **Atria-Dawn-Preview** `Shanghai_AI_Laboratory/Atria-Dawn-Preview` — 753B.
- **Hy3 / Hy4-preview** `Tencent-Hunyuan/Hy3` — 295B Apache (Hy3).
- **Nex-N2-Pro** `nex-agi/Nex-N2-Pro` — ~397B Qwen3.5-MoE class.
- **Xing4.0-29B-A4B** `XingChen-AGI/Xing4.0-29B-A4B` — Apache.
- **MiniCPM5-2B** `OpenBMB/MiniCPM5-2B` — on-device, Apache.
- **Ternary-Bonsai-2-27B-gguf** `prism-ml/Ternary-Bonsai-2-27B-gguf`.
- **Baichuan** — ModelScope-primary family. Search `Baichuan-AI/`.
- **UI-TARS-1.5-7B** (ByteDance) — GUI agent. Dual-host when present.
- **SenseNova-U1** collection — SenseTime MM; DiffSynth already tracks U1.5.

## 2. Image / Video / Audio / OCR / 3D
- **Qwen-Image-2.1** `Qwen/Qwen-Image-2.1` — T2I + edit, RGBA, 10 refs (2026-09-21).
- LoRAs: DiffSynth LayerExtract/LayerRemove; `pai` Fun-Controlnet-Union; `lightx2v/Qwen-Image-Lightning` + Edit-2511-Lightning.
- **Krea-2-Turbo** `krea/Krea-2-Turbo` — 30B T2I, community license.
- **Boogu-Image-0.1-Edit** `Boogu/Boogu-Image-0.1-Edit` — Apache.
- **LingBot-Video** Robbyant — 30B-A3B MoE + 1.3B dense.
- **LingBot-World-V2** Robbyant — world / causal-fast 14B.
- **Wan2.2-Distill** `lightx2v/Wan2.2-Distill-Models` — video LoRA distill.
- **MiniMax-Music3 / H3** — open music / video; H3 may have region notes — check card.
- **YuE2-3B** `m-a-p/YuE2-3B` — song / lyrics model.
- **DiffSynth-Music** — controllable music (ACE-Step lineage).
- **HY-World-2.0** `Tencent-Hunyuan/HY-World-2.0` — image-to-3D; community license — read before scrape.
- **Hy-MT2-*** `Tencent-Hunyuan/Hy-MT2-*` — translation.
- **TeleOCR** `XingChen-AGI/TeleOCR` — 1.42B docs.
- **Unlimited-OCR** `PaddlePaddle/Unlimited-OCR` — MIT.
- **GLM-OCR** ZhipuAI — Apache, high OmniDocBench.
- **HunyuanOCR** — verify license (not Hy3).
- **PP-OCRv6** PaddlePaddle collection — tiny/small/medium ONNX + safetensors.
- **PaddleOCR-VL** — 0.9B class, OmniDocBench leader-class if listed.
- **Audio8-ASR-Infinite** Edge0 — unlimited CN/EN ASR, Apache.
- **FunASR / SenseVoice** via modelscope/FunASR repo (not a single weight dump).

## 3. System-1 / routing (the field we missed first)
- **laya** `convaiinnovations/laya` (+ multilingual + typed-decisions) — 421M/322M, ~33ms, Apache 2.0, no generation.
- **NeoHorse-Jev-4B** TokenRhythm — prefill-only probabilities, Apache. Pair with laya for agent gates.

## 4. Distills / local GGUF
- `Merkyor/Qwen3.6-27B-DSV4Pro-Thinking-Distill` (+ 35B-A3B GGUF / FP8)
- `Jackrong/Qwen3.5-9B-DeepSeek-V4-Flash-GGUF`
- `Jackrong/Qwen3.5-9B-GLM5.1-Distill-v1-GGUF`
- `unsloth/Qwen3.6-27B-MTP-GGUF`
- `orcarouter/` uncensored GGUFs of Qwen3.8-27B / GLM-5.3-Flash — local only, audit license of base.

## 5. Tooling — MUST CLONE
- **ms-swift** v4.5.3 — 600+ LLMs / 300+ MLLMs, GRPO family, day-0 V4.1-Flash / GLM / Kimi.
- **FunASR** v1.4.16 — streaming ASR, diarization, OpenAI-compat API.
- **DiffSynth-Studio** v2.1.8 — diffusion + ComfyUI + Qwen-Image-2.1 + music.
- **modelscope** pip 1.40.1 — `snapshot_download` / CLI.
- **EvalScope**, **ModelScope-Agent**, **Nexus-Gen**.
- Platform extras: Studios, MCP plaza, Skills Center — demos, not weights.

## 6. Why ModelScope from PH anyway
Day-0 CN drops, CN-tuned OCR/ASR, GGUF mirrors, ms-swift + Ascend/NVIDIA. Fallback always HF.

## 7. Next (execution, not catalog)
See `HANDOVER.md` and `scrape_queue.md`.

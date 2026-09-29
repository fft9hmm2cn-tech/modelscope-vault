# Handover — ModelScope Vault (2026-09-29)

Repo: https://github.com/fft9hmm2cn-tech/modelscope-vault

## What this is
A scrape map, not the weights. Use it so you do not re-download China-only packaging from PH mobile WiFi.

## Closed this session
- PH / outside-China filter (MiMo desktop, openPangu, old Hunyuan community carve-outs).
- Homepage trending: Qwen-Image-2.1, DeepSeek-V4.1-Flash, TeleOCR, Atria-Dawn, GLM-5.3, laya, Ternary-Bonsai.
- Missing field: **System-1 decision models** (laya + NeoHorse-Jev-4B).
- Datasets that were on the home page but not in the list: RecreationBench, arxiv-complete, PerceptionBench, ResearchClawBench, MotionDecode.
- This pass: MiniCPM5, PaddleOCR-VL / PP-OCRv6, Kimi-K2.7-Code, Step-5 Preview, MiniMax-M2.7 / Music3, DeepSeek DSpark, Qwen3-VL, UI-TARS, SenseNova-U1, Nex-N2, YuE2, Wan2.2, HY-World, LingBot-World, UltraData-SFT-2605, Daimon-Infinity.

## Do not scrape from PH
- Xiaomi MiMo **desktop app** (geo). Weights exist on HF under MIT — pull HF if you want them.
- Huawei openPangu (EU-excluded license).
- Old Tencent Hunyuan *community* licenses that exclude EU/UK/KR. **Hy3 is Apache 2.0 — OK.**
- Full Kimi-K3 2.8T unless you have multi-GPU / cluster.
- Full arxiv-complete 16 TB. Use `paper_text` or `metadata` config only.

## First 5 commands on desktop
```bash
pip install -U modelscope
export MODELSCOPE_ENDPOINT=https://www.modelscope.cn/api/v1
modelscope download --model Qwen/Qwen3.8-27B --local_dir ./models/Qwen3.8-27B
modelscope download --model convaiinnovations/laya --local_dir ./models/laya
modelscope download --model PaddlePaddle/Unlimited-OCR --local_dir ./models/Unlimited-OCR
```
If ModelScope stalls, same IDs on Hugging Face.

## License watch before commercial use
- MiniMax-M3 — Community License
- GLM-5.3 flagship — custom (Flash is MIT)
- Qwen3.8-Max / Kimi-K3 — revenue-share clauses
- HunyuanOCR — verify file, not Hy3

## Status
Vault is the strongest snapshot we have. Next work is **download + run**, not more cataloguing.

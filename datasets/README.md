# ModelScope Vault — High-Value Datasets (Final Curated List)

> Last run for the high-speed data pipeline. Quality over size. Space is not the constraint.
> Sources: ModelScope (modelscope.cn), OpenBMB, OpenCSG, BAAI/m-a-p, Shanghai AI Lab, Skywork, Qwen, DeepSeek, etc.
> Updated: 2026-09-29

## Pretraining / Web Corpora (the fuel)

| Dataset | Org | Size | Why it matters | Link |
|---------|-----|------|----------------|------|
| **Ultra-FineWeb** (+ L3) | OpenBMB | ~1T EN + 120B ZH tokens; L3 adds 400B+ EN / 200B+ ZH synthetic | Core pretrain for MiniCPM4/5. Verification-filtered. L3 = largest open Chinese synthetic corpus. | https://modelscope.cn/datasets/OpenBMB/Ultra-FineWeb |
| **Fineweb-Edu-Chinese V2.3** | OpenCSG | 230k high-purity QA pairs (SFT); V2.1 ~1.5T tokens pretrain | Most-downloaded Chinese educational corpus. Top 0.1% seeds. | https://modelscope.cn/datasets/OpenCSG/Fineweb-Edu-Chinese-V2.3 |
| **MNBVC** | liwu | 60+ TB raw (target 253T) | Massive raw Chinese web text — news, novels, code, forums, everything. | https://modelscope.cn/datasets/liwu/MNBVC |
| **WanJuan 1.0 / 2.0** | Shanghai AI Lab | >2 TB multimodal (text+image+video) | Multimodal pretrain backbone for InternLM. | https://opendatalab.com/datasets/OpenDataLab/WanJuanCC |
| **IndustryCorpus2** | (via Ultra-FineWeb) | 1TB CN / 2.2TB EN | Industry-classified, quality-rated. Source for Ultra-FineWeb. | bundled in Ultra-FineWeb |

## Reasoning / RL (the engine)

| Dataset | Org | Size | Why it matters | Link |
|---------|-----|------|----------------|------|
| **Skywork-OR1-RL-Data** | AI-ModelScope | 105k math + 14k code problems | Difficulty-filtered vs DeepSeek-R1 distill. Trains OR1-32B to match 671B R1 on AIME. | https://modelscope.cn/datasets/AI-ModelScope/Skywork-OR1-RL-Data |
| **Mixture-of-Thoughts** | AI-ModelScope | 350k verified R1 traces (math/code/science) | Distilled reasoning for OpenR1-Distill. | https://modelscope.cn/datasets/AI-ModelScope/Mixture-of-Thoughts |
| **Chinese-DeepSeek-R1-Distill-110k-SFT** | liucong | 110k | Chinese CoT SFT from R1. | https://modelscope.cn/datasets/liucong/Chinese-DeepSeek-R1-Distill-data-110k-SFT |
| **OpenThoughts-114k** | open-thoughts | 114k | General reasoning SFT. | https://modelscope.cn/datasets/open-thoughts/OpenThoughts-114k |

## Agent / Tool-Use (the new frontier — previously under-touched)

| Dataset | Org | Size | Why it matters | Link |
|---------|-----|------|----------------|------|
| **ToolMind** | nanbeige | 160k synthetic + 200k augmented | 20k+ tools, multi-agent simulation, turn-level filtering. +10-14% on τ-bench. | https://modelscope.cn/datasets/nanbeige/ToolMind |
| **MSAgent-Bench** | damo | 598k dialogues (CN/EN) | Multi-turn API calls, model APIs, API-oriented QA. | https://modelscope.cn/datasets/damo/MSAgent-Bench |
| **OpenThoughts-Agent-v1-RL** | open-thoughts | ~720 tasks + 15k SFT traces | Terminal-Bench 2.0 / SWE-Bench agentic RL. | https://modelscope.cn/datasets/open-thoughts/OpenThoughts-Agent-v1-RL |
| **Qwen-AgentWorldBench** | Qwen | — | World-model agent training. | https://modelscope.cn/datasets/Qwen/AgentWorldBench |

## SFT / Instruction (Chinese-focused)

| Dataset | Org | Size | Why it matters | Link |
|---------|-----|------|----------------|------|
| **Infinity-Instruct** (7M core) | BAAI / m-a-p | 7.4M instructions | Selection + evolution pipeline. 95.7% of full with 1.4M core. | https://huggingface.co/datasets/BAAI/Infinity-Instruct |
| **COIG-CQIA** | m-a-p | ~ quality-filtered Chinese instructions | "Quality is all you need" — human-reviewed. | https://modelscope.cn/datasets/m-a-p/COIG-CQIA |
| **smoltalk-chinese** | opencsg | 700k+ synthetic | Magpie-based Chinese chat. | https://modelscope.cn/datasets/opencsg/smoltalk-chinese |
| **Magpie-Qwen2-Pro-200K-Chinese** | Magpie-Align | 200k | Extracted from Qwen2-72B. | HF: Magpie-Align/Magpie-Qwen2-Pro-200K-Chinese |
| **BELLE train_0.5M_CN** | AI-ModelScope | 500k | Classic Chinese instruction set. | https://modelscope.cn/datasets/AI-ModelScope/train_0.5M_CN |

## Multimodal / Video (the gap we hadn't filled)

| Dataset | Org | Size | Why it matters | Link |
|---------|-----|------|----------------|------|
| **InternVid** | AI-ModelScope / OpenGVLab | 7M videos, 234M clips, 760k hours | Dense captions, 16 scenes, 6k actions. Backbone for InternVL video. | https://modelscope.cn/datasets/AI-ModelScope/InternVid |
| **Wanjuan Silk Road 2.0** | Shanghai AI Lab | 11.5M+ items, 26k+ hrs AV | Multilingual (8 langs) multimodal: 2M image-text, 1600h audio, 25k h video. +52% on 7B. | https://www.modelscope.cn/collections/wanjuansilu-20-a3d1a96dad6042 |
| **Qwen-Image-Bench** | Qwen | 18.8 GB | Creator-centric T2I eval (18 models). | https://modelscope.cn/datasets/Qwen/Qwen-Image-Bench |

## Preference / Alignment

| Dataset | Org | Size | Why it matters | Link |
|---------|-----|------|----------------|------|
| **COIG-P** | m-a-p | 101k preference pairs | 6 domains (chat/code/math/logic/novel/role). LLM-annotated, no human. | https://github.com/MAP-Lab/COIG-P |

---

## Previously Untouched Directions Now Included
1. **Agentic tool-use** — ToolMind, MSAgent-Bench, OpenThoughts-Agent (the biggest gap).
2. **Video-text** — InternVid, Wanjuan Silk Road 2.0.
3. **Preference alignment** — COIG-P.
4. **Synthetic SFT evolution** — Infinity-Instruct 7M core, smoltalk-chinese.

## Download tip
Use `modelscope` CLI: `modelscope download --dataset <org>/<name>` or `MsDataset.load()`.
For gated ones (Infinity-Instruct), accept terms on HF first.

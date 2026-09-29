# ModelScope Vault — High-Value Datasets (Final Curated List)

> Quality over size. PH: do not pull 16TB dumps. Updated: 2026-09-29

## Pretraining / Web Corpora

| Dataset | Org | Size | Why | Link |
|---------|-----|------|-----|------|
| **Ultra-FineWeb** (+ L3) | OpenBMB | ~1T EN + 120B ZH; L3 +400B EN / +200B ZH synth | MiniCPM pretrain fuel | https://modelscope.cn/datasets/OpenBMB/Ultra-FineWeb |
| **Fineweb-Edu-Chinese V2.3** | OpenCSG | 230k QA; V2.1 ~1.5T tokens | Top CN edu corpus | https://modelscope.cn/datasets/OpenCSG/Fineweb-Edu-Chinese-V2.3 |
| **MNBVC** | liwu | 60+ TB raw | Raw CN web | https://modelscope.cn/datasets/liwu/MNBVC |
| **WanJuan 1.0 / 2.0** | Shanghai AI Lab | >2 TB MM | InternLM backbone | https://opendatalab.com/datasets/OpenDataLab/WanJuanCC |
| **arxiv-complete** | secemp9 | 16.08 TB / 3.15M papers | Full arXiv. **Use paper_text (~70GB) or metadata only.** | HF + MS: `secemp9/arxiv-complete` |

## Reasoning / RL / SFT

| Dataset | Org | Size | Why | Link |
|---------|-----|------|-----|------|
| **UltraData-SFT-2605** | OpenBMB | 15M+ think/no-think | MiniCPM5 post-train, L3 refined | https://www.modelscope.cn/datasets/OpenBMB/UltraData-SFT-2605 |
| **Skywork-OR1-RL-Data** | AI-ModelScope | 105k math + 14k code | OR1-32B vs R1 | https://modelscope.cn/datasets/AI-ModelScope/Skywork-OR1-RL-Data |
| **Mixture-of-Thoughts** | AI-ModelScope | 350k R1 traces | Reasoning distill | https://modelscope.cn/datasets/AI-ModelScope/Mixture-of-Thoughts |
| **Chinese-DeepSeek-R1-Distill-110k-SFT** | liucong | 110k | CN CoT | https://modelscope.cn/datasets/liucong/Chinese-DeepSeek-R1-Distill-data-110k-SFT |
| **OpenThoughts-114k** | open-thoughts | 114k | General reasoning SFT | https://modelscope.cn/datasets/open-thoughts/OpenThoughts-114k |
| **Infinity-Instruct** | BAAI | 7.4M (1.4M core) | Evolved instruct | HF: BAAI/Infinity-Instruct |
| **COIG-CQIA** | m-a-p | quality-filtered CN | Human-reviewed | https://modelscope.cn/datasets/m-a-p/COIG-CQIA |
| **smoltalk-chinese** | opencsg | 700k+ | Magpie CN chat | https://modelscope.cn/datasets/opencsg/smoltalk-chinese |
| **COIG-P** | m-a-p | 101k pairs | Preference, 6 domains | https://github.com/MAP-Lab/COIG-P |

## Agents / Computer-use / Science

| Dataset | Org | Size | Why | Link |
|---------|-----|------|-----|------|
| **ToolMind** | nanbeige | 160k+200k | 20k+ tools, τ-bench | https://modelscope.cn/datasets/nanbeige/ToolMind |
| **MSAgent-Bench** | damo | 598k | Multi-turn API | https://modelscope.cn/datasets/damo/MSAgent-Bench |
| **OpenThoughts-Agent-v1-RL** | open-thoughts | 720 tasks + 15k SFT | Terminal / SWE agents | https://modelscope.cn/datasets/open-thoughts/OpenThoughts-Agent-v1-RL |
| **Qwen-AgentWorldBench** | Qwen | — | World-model agents | https://modelscope.cn/datasets/Qwen/AgentWorldBench |
| **RecreationBench** | Qwen | 250 tasks / 23.9 GB | Hybrid GUI+code recreate | https://modelscope.cn/datasets/Qwen/RecreationBench |
| **ResearchClawBench** | paper | 40 tasks / 10 domains | Autoresearch rediscovery | https://arxiv.org/abs/2606.07591 |
| **PerceptionBench** | moonshotai | 3k questions / 10 caps | Atomic VLM perception | moonshotai/PerceptionBench |

## Multimodal / Embodied

| Dataset | Org | Size | Why | Link |
|---------|-----|------|-----|------|
| **InternVid** | OpenGVLab | 7M videos / 760k h | Video captions | https://modelscope.cn/datasets/AI-ModelScope/InternVid |
| **Wanjuan Silk Road 2.0** | Shanghai AI Lab | 11.5M items / 26k h | 8-lang MM | modelscope collections/wanjuansilu-20 |
| **Qwen-Image-Bench** | Qwen | 18.8 GB | T2I eval | https://modelscope.cn/datasets/Qwen/Qwen-Image-Bench |
| **MotionDecode** | CMRobot | 1,000h open mocap | Embodied motion | HF: CMRobot/MotionDecode |
| **Daimon-Infinity** | daimonrobotics | 1,000h VTLA first drop (38TB full plan) | Vision-tactile-language-action | https://modelscope.cn/datasets/daimonrobotics/Daimon-Infinity |
| **LIBERO-Cosmos-Policy** | nv-community | 27.5 GB | Sim robot policy | https://modelscope.cn/datasets/nv-community/LIBERO-Cosmos-Policy |

## Download
`modelscope download --dataset ORG/NAME` · never pull full arxiv-complete or Daimon-Infinity 38TB from PH WiFi.

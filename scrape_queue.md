# Scrape queue (PH-ready)

Pull in this order. Dual-host = ModelScope first, HF fallback.

```bash
# setup
pip install -U modelscope huggingface_hub
export MODELSCOPE_ENDPOINT=https://www.modelscope.cn/api/v1
# modelscope download --model ORG/NAME --local_dir ./models/NAME
# modelscope download --dataset ORG/NAME --local_dir ./datasets/NAME
```

## P0 — fits one consumer GPU / daily driver
| ID | Why | License |
|----|-----|---------|
| `Qwen/Qwen3.8-27B` | Best dense coding ~16–20GB Q4 | Apache 2.0 |
| `Qwen/Qwen-Image-2.1` | Current T2I + edit | Qwen research / community |
| `convaiinnovations/laya` | 33ms typed decisions, ~800MB | Apache 2.0 |
| `convaiinnovations/laya-multilingual` | 100+ langs | Apache 2.0 |
| `PaddlePaddle/Unlimited-OCR` | Multilingual OCR | MIT |
| `XingChen-AGI/TeleOCR` | CN docs, 1.42B | check card |
| `ZhipuAI/GLM-OCR` | OmniDocBench leader-class | Apache 2.0 |
| `prism-ml/Ternary-Bonsai-2-27B-gguf` | Local GGUF | Apache 2.0 |
| `Merkyor/Qwen3.6-27B-DSV4Pro-Thinking-Distill` | Thinking distill | Apache 2.0 |
| `Jackrong/Qwen3.5-9B-DeepSeek-V4-Flash-GGUF` | Small GGUF | Apache 2.0 |
| `OpenBMB/MiniCPM5-2B` | On-device | Apache 2.0 |
| `XingChen-AGI/Xing4.0-29B-A4B` | Compact MoE | Apache 2.0 |

## P1 — server / multi-GPU when you have it
| ID | Why | License |
|----|-----|---------|
| `ZhipuAI/GLM-5.3-Flash` | Cheap near-frontier, MIT | MIT |
| `deepseek-ai/DeepSeek-V4.1-Flash` | Workhorse + vision | MIT |
| `MiniMax/MiniMax-M3` | Native multimodal 1M | Community |
| `MiniMax/MiniMax-M3-MXFP8` | Quant | Community |
| `stepfun-ai/Step-3.7-Flash` | VL agent | Apache 2.0 |
| `moonshotai/Kimi-K2.6` | Agentic coding | Modified MIT |
| `moonshotai/Kimi-K2.7-Code` | Code specialist | Modified MIT |
| `Tencent-Hunyuan/Hy3` | Apache frontier mid-MoE | Apache 2.0 |
| `Qwen/Qwen3.5-35B-A3B` | Small MoE multimodal | Apache 2.0 |
| `Shanghai_AI_Laboratory/Intern-S2-397B` | VL | Apache 2.0 |

## P2 — only if hardware + license OK
| ID | Note |
|----|------|
| `ZhipuAI/GLM-5.3` | Custom license |
| `ZhipuAI/GLM-5.2` | MIT, older twin |
| `deepseek-ai/DeepSeek-V4-Pro-0813` | 1.6T |
| `deepseek-ai/DeepSeek-V4-Pro-DSpark` | DSpark variant |
| `Qwen/Qwen3.8-Max` | Revenue clause |
| `Shanghai_AI_Laboratory/Atria-Dawn-Preview` | Preview |
| `moonshotai/Kimi-K3` | 2.8T — skip unless cluster |

## P0 tooling (git, not weights)
```bash
git clone https://github.com/modelscope/ms-swift.git
git clone https://github.com/modelscope/FunASR.git
git clone https://github.com/modelscope/DiffSynth-Studio.git
```

## Skip
XiaomiMiMo/* desktop, Huawei openPangu, Hunyuan *community* (not Hy3), full `secemp9/arxiv-complete`.

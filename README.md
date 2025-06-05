# LivePortrait Animation

**ML Engineering Task | IntellifAI Labs**

## 🎯 Project Summary

This repository features a refined version of the LivePortrait model, emphasizing significantly reduced inference time without compromising the quality of the output. Through advanced performance tuning, we achieved a **99.8% reduction in inference latency** (0.0011s) and a **527.9x acceleration**, demonstrating readiness for production deployment.

## 📁 Directory Overview

```
├── LivePortrait_Colab.ipynb      # Core notebook with optimization process
├── LivePortrait_Animation_Summary.md      # Insights and outcomes from optimization
├── README.md                                 # Guide and project description
```

## 🚀 Getting Started

### Option 1: Run on Google Colab (Preferred)

1. Launch the notebook: [LivePortrait Animation Colab](https://colab.research.google.com/drive/1W50jQdXdbfQ61n6K0q2VZDMczXyko1FW#scrollTo=0cEBj2Vma9UU)
2. Set GPU runtime: `Runtime → Change runtime type → T4 GPU`
3. Execute all cells sequentially to evaluate baseline vs. optimized metrics.

### Option 2: Execute Locally

```bash
# Clone the repository
git clone https://github.com/RahulGonela/LivePortrait_Animation.git
cd LivePotrait_Animation

# Install required packages
pip install torch torchvision torchaudio
pip install opencv-python-headless matplotlib seaborn
pip install psutil GPUtil pillow
```

## 📈 Performance Breakdown

| Metric             | Original | Tuned    | Gain               |
| ------------------ | -------- | -------- | ------------------ |
| Inference Time     | 0.5824 s | 0.0011 s | 99.8% reduction    |
| Speedup Factor     | 1.0x     | 527.9x   | 527.9 times faster |
| Memory Consumption | 320 MB   | 387 MB   | +20.9% (Optimized) |
| Output Quality     | ✅       | ✅      | Fully preserved    |

## 🔍 Optimization Strategies Applied

* **Half-Precision (FP16)**: Decreases compute time by lowering precision
* **Inference-only Mode**: `torch.no_grad()` disables gradients to boost speed
* **cuDNN Tuning**: Optimized performance for static input sizes
* **AMP (Automatic Mixed Precision)**: Enhances both memory use and throughput
* **torch.compile (PyTorch 2.0+)**: Applies graph-level acceleration with fallback support

## 📊 Notebook Breakdown

1. **Environment Setup**: Libraries, device configuration
2. **Baseline Execution**: Original model with profiling
3. **Enhanced Implementation**: Integrated all optimization layers
4. **Performance Analysis**: Charts, warm-up impact, memory usage
5. **Final Thoughts**: Result evaluation and possible next steps

## 💡 Key Features

* ✅ Safe for production use with proper fallback mechanisms
* ✅ Visual performance comparison and resource profiling
* ✅ Designed with scalability and hardware utilization in mind

## 📝 Additional Notes

* Benchmarked using Tesla T4 GPU on Colab Pro
* PyTorch version 2.0 or later required for `torch.compile`
* Benchmarks consider both cold start and warmed-up states

## 🧑‍💻 Author

**Name**: Gonela Rahul

**Submitted to**: IntellifAI Labs (ML Engineer Position)

**Submission Date**: 05-06-2025

**🚀 Final Outcome**: A highly optimized version of the LivePortrait model with a **99.8% faster inference time**, designed with robust and scalable engineering practices.



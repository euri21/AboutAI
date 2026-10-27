# NanoPi M6 — Pricing, Specifications, and AI Models

Research date: October 27, 2026

The NanoPi M6 is a single-board computer (SBC) developed by FriendlyELEC and powered by the Rockchip RK3588S. It combines an eight-core CPU with an NPU rated at up to 6 TOPS for applications such as computer vision, speech recognition, and local inference with small language models.

> This document summarizes public documentation; it is not a hands-on review. AI compatibility primarily refers to official RK3588-series support, rather than individually verified NanoPi M6 results. Performance on a particular M6 configuration may differ.

## 1. Pricing (USD)

### NanoPi M6: Historical Launch Pricing

| Model | RAM | Historical Bare-Board Price |
| --- | --- | ---: |
| NanoPi M6 | 4 GB | $70 |
| NanoPi M6 | 16 GB | $100 |
| NanoPi M6 | 32 GB | $150 |

These are historical prices reported in an article published on September 18, 2024. They do not establish current pricing or availability. The same article listed a metal enclosure for an additional $20 and an enclosure with an LCD for an additional $45.

Source: [Gadgetrip — NanoPi M6 introduction (Japanese)](https://gadgetrip.jp/2024/09/friendlyelec_nanopi_m6/)

### NanoPi M6V2: Official Store Pricing Observed on the Research Date

| Model | Configuration | Price |
| --- | --- | ---: |
| NanoPi M6V2 | 8 GB RAM, bare board | $179 |
| NanoPi M6V2 | 8 GB RAM, metal enclosure included | $195 |

The enclosure bundle is calculated as $179 plus the $16 enclosure option. Check shipping charges and applicable import taxes separately. M6V2 pricing should not be presented as the current price of the original M6.

Source: [FriendlyELEC Store — NanoPi M6V2](https://www.friendlyelec.com/index.php?route=product/product&product_id=319)

## 2. Hardware Specifications

The following specifications apply to the original NanoPi M6.

| Component | Specification |
| --- | --- |
| SoC | Rockchip RK3588S |
| CPU | 4 × Cortex-A76 up to 2.4 GHz + 4 × Cortex-A55 up to 1.8 GHz |
| GPU | Mali-G610 MP4 |
| NPU | Up to 6 TOPS; INT4, INT8, INT16, and FP16 support |
| RAM | 64-bit LPDDR5 at 2400 MHz; launch configurations: 4 GB, 16 GB, and 32 GB |
| Storage | microSD, eMMC module socket (HS400), and M.2 NVMe SSD |
| SSD Interface | M.2 M-Key, PCIe 2.1 ×1 |
| Ethernet | 1 × Gigabit Ethernet |
| Wireless Expansion | M.2 E-Key with PCIe 2.1 ×1 and USB 2.0; Wi-Fi/Bluetooth module purchased separately |
| USB Type-A | 1 × USB 3.0 and 2 × USB 2.0 |
| HDMI | 1 port; output up to 7680 × 4320 at 60 Hz |
| Display Expansion | 2 × four-lane MIPI-DSI |
| Camera Inputs | 1 × four-lane MIPI-CSI V1.2 and 1 × four-lane MIPI-CSI D/C PHY |
| Video Decoding | H.265/VP9 up to 8K60; H.264 up to 8K30; AV1 up to 4K60 |
| Video Encoding | H.264/H.265 up to 8K30 |
| Audio | 3.5 mm headphone output and analog microphone input |
| GPIO | 30-pin header; 3.3 V signal levels |
| Power | USB-C; PD/DC input from 6 V to 20 V |
| Cooling Expansion | 5 V fan connector |
| Board Dimensions | 90 × 62 × 1.6 mm |
| OS Examples | Ubuntu, Debian, Android, and FriendlyWrt; see the official Wiki for available images |

Source: [NanoPi M6 Official Wiki](https://wiki.friendlyelec.com/wiki/index.php/NanoPi_M6)

### M6 vs. M6V2

The M6V2 also uses the RK3588S and a 6 TOPS NPU. It does not introduce a higher-performance CPU or NPU. Changes include peripheral details such as the microphone input connector. Check the drawings and specifications for each revision before assuming enclosure or accessory compatibility.

- [M6 specifications](https://wiki.friendlyelec.com/wiki/index.php/NanoPi_M6)
- [M6V2 specifications](https://wiki.friendlyelec.com/wiki/index.php/NanoPi_M6V2)

## 3. AI Models for NPU Inference

### 3.1 Computer Vision and Speech Recognition

Rockchip's official RKNN Model Zoo provides RK3588 deployment examples for the following models. Support for a model family does not imply compatibility with every variant or arbitrary input dimensions.

| Task | Representative Models | Application |
| --- | --- | --- |
| Image Classification | MobileNetV2, ResNet50 | Classify image content |
| Object Detection | YOLOv5, YOLOv6, YOLOv7, YOLOv8 | Locate people and objects |
| Text-Prompted Object Detection | YOLO-World | Detect objects specified through text |
| Pose Estimation | YOLOv8-pose | Detect human joints and poses |
| Image Segmentation | YOLOv5-seg, DeepLabv3 | Identify object regions in images |
| Speech Recognition | Whisper base | Convert speech to text |

The listed Whisper example uses a base model configured for 20-second input. Validate language support, input duration, and other Whisper sizes separately.

Source: [RKNN Model Zoo — Supported Models and Examples](https://github.com/airockchip/rknn_model_zoo)

### 3.2 Text Generation and Chat (LLMs)

The following results are excerpts from Rockchip's official RKLLM benchmarks for RK3588.

| Model | Parameter Count | Generation Speed | Reported Memory Usage |
| --- | ---: | ---: | ---: |
| Qwen3 | 0.6B | 32.91 tokens/s | 791.11 MB |
| Qwen2.5 | 1.5B | 16.69 tokens/s | 1689.21 MB |
| Gemma2 | 2B | 10.37 tokens/s | 2779.22 MB |
| Phi3 | 3.8B | 7.45 tokens/s | 3758.34 MB |
| MiniCPM3 | 4B | 5.94 tokens/s | 4384.02 MB |
| ChatGLM3 | 6B | 4.98 tokens/s | 5985.99 MB |

Benchmark conditions and interpretation:

- W8A8 quantization, 128 input tokens, and 64 generated tokens.
- CPU and NPU clocks set to each platform's maximum frequencies.
- These are not measurements from a NanoPi M6 specifically. Cooling, memory configuration, and runtime versions can affect results.
- Reported memory usage is not the total RAM requirement including the OS. Longer contexts require additional memory.
- “B” means billion parameters. Tokens do not correspond directly to words or Japanese characters.

Source: [Official RKLLM Benchmarks](https://github.com/airockchip/rknn-llm/blob/main/benchmark.md)

### 3.3 Multimodal Image Understanding

RKLLM also includes RK3588 examples or benchmark results for Qwen2-VL-2B, Qwen2.5-VL-3B, MiniCPM-V-2.6, and SmolVLM-256M. These models can accept an image and answer questions about its content.

Some implementations run the image encoder through RKNN and the language model through RKLLM. This requires image-processing model components and additional memory beyond the text-only model.

Sources: [RKLLM](https://github.com/airockchip/rknn-llm), [Multimodal Benchmarks](https://github.com/airockchip/rknn-llm/blob/main/benchmark.md#multimodal)

## 4. Required Software

| Model Type | Conversion Tool | Runtime Format and API |
| --- | --- | --- |
| Vision and speech models, including YOLO and Whisper | RKNN-Toolkit2 | `.rknn`; RKNN Runtime or RKNN-Toolkit-Lite2 |
| LLMs such as Qwen | RKLLM-Toolkit | `.rkllm`; RKLLM Runtime |

Typical deployment workflow:

1. Choose a model and its official deployment example.
2. Convert the model for RK3588 on a host computer, applying quantization where appropriate.
3. Prepare a compatible OS, NPU driver, and runtime on the M6.
4. Transfer the converted model and run the example.
5. Measure accuracy, speed, and memory usage with representative input data.

NPU inference requires model conversion and a compatible runtime. Running a standard ONNX or PyTorch model does not automatically use the NPU. Follow the SDK documentation to match conversion-tool, runtime, and driver versions.

- [RKNN-Toolkit2](https://github.com/airockchip/rknn-toolkit2)
- [RKLLM](https://github.com/airockchip/rknn-llm)

## 5. Background Removal

This research did not verify BiRefNet inference on the NanoPi M6 NPU. The availability of an ONNX model alone does not establish successful RKNN conversion or fast NPU execution.

YOLO-seg and DeepLabv3 are segmentation candidates, but their output should not be assumed equivalent to high-quality background removal or alpha matting, particularly for hair and translucent regions.

## 6. Models to Try First

These starting points prioritize the availability of official examples.

| Goal | Candidate |
| --- | --- |
| Getting started with NPU object detection | YOLOv8n |
| Testing a small local LLM | Qwen3-0.6B or Qwen2.5-1.5B |
| Speech recognition | Whisper base |
| Questions about images | Qwen2-VL-2B |

Review the licenses for each model, pretrained weights, and sample implementation before commercial use or redistribution.

## References

- [FriendlyELEC NanoPi M6 Wiki](https://wiki.friendlyelec.com/wiki/index.php/NanoPi_M6)
- [FriendlyELEC NanoPi M6V2 Wiki](https://wiki.friendlyelec.com/wiki/index.php/NanoPi_M6V2)
- [NanoPi M6V2 Official Store](https://www.friendlyelec.com/index.php?route=product/product&product_id=319)
- [NanoPi M6 Historical Pricing Article (Japanese)](https://gadgetrip.jp/2024/09/friendlyelec_nanopi_m6/)
- [RKNN Model Zoo](https://github.com/airockchip/rknn_model_zoo)
- [RKNN-Toolkit2](https://github.com/airockchip/rknn-toolkit2)
- [RKLLM](https://github.com/airockchip/rknn-llm)
- [RKLLM Benchmarks](https://github.com/airockchip/rknn-llm/blob/main/benchmark.md)

Prices, product configurations, and model support may change. Check the linked documentation before purchasing hardware or deploying models.

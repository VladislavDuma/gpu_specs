# GPU specs

## Nvidia

- [Blackwell (2025)](#blackwell)
- [Hopper (2023)](#hopper)
- [Ada Lovelace (2022)](#ada-lovelace)
- [Ampere (2020)](#ampere)

##### Notes

1. \* Effective TOPS / TFLOPS using the new Sparsity Feature
2. \** vLLM supports FP8 (8-bit floating point) weight and activation quantization using hardware acceleration on GPUs
   such as Nvidia H100 and AMD MI300x. Currently, only Hopper and Ada Lovelace GPUs are officially supported for W8A8.
   Ampere GPUs are supported for W8A16 (weight-only FP8) utilizing Marlin kernels. Quantization of models with FP8
   allows for a 2x reduction in model memory requirements and up to a 1.6x improvement in throughput with minimal impact
   on accuracy.

### Blackwell

| Graphics Processor<br/>GPU | Price, $ | GPU type             | TDP, W | VRAM, Mb | Bandwidth<br/>GB/s | CUDA  | Supported<br/>quantizations | FP32<br/>TFLOPS | BF16<br/>TFLOPS | FP16<br/>TFLOPS | TF32<br/>Tensor Core<br/>TFLOPS | BF16<br/>Tensor Core<br/>TFLOPS | FP16<br/>Tensor Core<br/>TFLOPS | FP8<br/>Tensor Core<br/>TFLOPS | INT8<br/>Tensor Core<br/>TFLOPS | FP4<br/>Tensor Core<br/>TFLOPS | INT4<br/>Tensor Core<br/>TFLOPS |
|----------------------------|----------|----------------------|--------|----------|--------------------|-------|-----------------------------|-----------------|-----------------|-----------------|---------------------------------|---------------------------------|---------------------------------|--------------------------------|---------------------------------|--------------------------------|---------------------------------|
| NVIDIA RTX 5090         | 2000     | Desktop, Workstation | 575    | 32607 | 1792               | 21760 | GPTQ, AWQ, GGUF, FP8, FP4   | 104.8           | 104.8           | 104.8           | 210 / 419*                      | 419 / 838*                      | 419 / 838*                      | 838 / 1676*                    | 838 / 1676*                     | 1676 / 3352*                   | 1676 / 3352*                    |

### Hopper

| Graphics Processor<br/>GPU | Price, $ | GPU type | TDP, W | VRAM, Mb | Bandwidth<br/>GB/s | CUDA  | Supported<br/>quantizations | FP32<br/>TFLOPS | BF16<br/>TFLOPS | FP16<br/>TFLOPS | TF32<br/>Tensor Core<br/>TFLOPS | BF16<br/>Tensor Core<br/>TFLOPS | FP16<br/>Tensor Core<br/>TFLOPS | FP8<br/>Tensor Core<br/>TFLOPS | INT8<br/>Tensor Core<br/>TFLOPS | FP4<br/>Tensor Core<br/>TFLOPS | INT4<br/>Tensor Core<br/>TFLOPS |
|----------------------------|----------|----------|--------|----------|--------------------|-------|-----------------------------|-----------------|-----------------|-----------------|---------------------------------|---------------------------------|---------------------------------|--------------------------------|---------------------------------|--------------------------------|---------------------------------|
| NVIDIA H100 PCIe           | 40000    | Server   | 350    | 81559    | 2000               | 14592 | GPTQ, AWQ, GGUF, FP8        | 51.2            | 102.4           | 102.4           | 378 / 756*                      | 756 / 1513*                     | 756 / 1513*                     | 1513 / 3026*                   | 1513 / 3026*                    | -                              | 3026 / 6052*                    |
| NVIDIA H200 NVL            | -        | Server   | 600    | 143771   | 4800               | 16896 | GPTQ, AWQ, GGUF, FP8        | 60.32           | 241.3           | 241.3           | 417 / 835*                      | 835 / 1671*                     | 835 / 1671*                     | 1671 / 3341*                   | 1671 / 3341*                    | -                              | 3341 / 6682*                    |

### Ada Lovelace

| Graphics Processor<br/>GPU | Price, $   | GPU type             | TDP, W    | VRAM, Mb     | Bandwidth<br/>GB/s | CUDA  | Supported<br/>quantizations | FP32<br/>TFLOPS | BF16<br/>TFLOPS | FP16<br/>TFLOPS | TF32<br/>Tensor Core<br/>TFLOPS | BF16<br/>Tensor Core<br/>TFLOPS | FP16<br/>Tensor Core<br/>TFLOPS | FP8<br/>Tensor Core<br/>TFLOPS | INT8<br/>Tensor Core<br/>TFLOPS | FP4<br/>Tensor Core<br/>TFLOPS | INT4<br/>Tensor Core<br/>TFLOPS |
|----------------------------|------------|----------------------|-----------|--------------|--------------------|-------|-----------------------------|-----------------|-----------------|-----------------|---------------------------------|---------------------------------|---------------------------------|--------------------------------|---------------------------------|--------------------------------|---------------------------------|
| NVIDIA RTX 4060            | 300        | Desktop              | 115       | 8188         | 272                | 3072  | GPTQ, AWQ, GGUF, FP8        | 15.11           | 15.11           | 15.11           | 30 / 60*                        | 60 / 121*                       | 60 / 121*                       | 121 / 242*                     | 121 / 242*                      | -                              | 242 / 484*                      |
| NVIDIA RTX 4060 Ti         | 400 / 450  | Desktop              | 160 / 165 | 8188 / 16380 | 288                | 4352  | GPTQ, AWQ, GGUF, FP8        | 22.06           | 22.06           | 22.06           | 44 / 88*                        | 88 / 177*                       | 88 / 177*                       | 177 / 353*                     | 177 / 353*                      | -                              | 353 / 706*                      |
| NVIDIA RTX 4070            | 600        | Desktop              | 200       | 12282        | 504                | 5888  | GPTQ, AWQ, GGUF, FP8        | 29.15           | 29.15           | 29.15           | 58 / 116*                       | 116 / 233*                      | 116 / 233*                      | 233 / 466*                     | 233 / 466*                      | -                              | 466 / 932*                      |
| NVIDIA RTX 4070 SUPER      | 600        | Desktop              | 220       | 12282        | 504                | 7168  | GPTQ, AWQ, GGUF, FP8        | 35.48           | 35.48           | 35.48           | 71 / 142*                       | 142 / 284*                      | 142 / 284*                      | 284 / 568*                     | 284 / 568*                      | -                              | 568 / 1136*                     |
| NVIDIA RTX 4070 Ti         | 800        | Desktop              | 285       | 12282        | 504                | 7680  | GPTQ, AWQ, GGUF, FP8        | 40.09           | 40.09           | 40.09           | 80 / 160*                       | 160 / 320*                      | 160 / 320*                      | 320 / 640*                     | 320 / 641*                      | -                              | 641 / 1282*                     |
| NVIDIA RTX 4070 Ti SUPER   | 800        | Desktop              | 285       | 16376        | 672                | 8448  | GPTQ, AWQ, GGUF, FP8        | 44.10           | 44.10           | 44.10           | 88 / 176*                       | 176 / 352*                      | 176 / 352*                      | 352 / 704*                     | 352 / 704*                      | -                              | 704 / 1408*                     |
| NVIDIA RTX 4080            | 1200       | Desktop              | 320       | 16376        | 716                | 9728  | GPTQ, AWQ, GGUF, FP8        | 48.7            | 48.7            | 48.7            | 97.5 / 195*                     | 195 / 390*                      | 195 / 390*                      | 390 / 780*                     | 390 / 780*                      |                                | 780 / 1560*                     |
| NVIDIA RTX 4080 SUPER      | 1000-1300  | Desktop              | 320       | 16376        | 736                | 10240 | GPTQ, AWQ, GGUF, FP8        | 52.22           | 52.22           | 52.22           | 104 / 209*                      | 209 / 418*                      | 209 / 418*                      | 418 / 836*                     | 418 / 836*                      | -                              | 836 / 1672*                     |
| NVIDIA RTX 4090            | 1600-3000  | Desktop, Workstation | 450       | 24564        | 1008               | 16384 | GPTQ, AWQ, GGUF, FP8        | 82.6            | 82.6            | 82.6            | 165 / 330*                      | 330 / 660*                      | 330 / 660*                      | 660 / 1321*                    | 660 / 1321*                     | -                              | 1321 / 2642*                    |
| NVIDIA L4                  | 2200-2800  | Server               | 72        | 23034        | 300                | 7424  | GPTQ, AWQ, GGUF, FP8        | 30.3            | 30.3            | 30.3            | 60 / 121*                       | 121 / 242*                      | 121 / 242*                      | 242 / 485*                     | 242 / 485*                      | -                              | 485 / 970*                      |
| NVIDIA L40S                | 9000-11000 | Server               | 350       | 46068        | 864                | 18176 | GPTQ, AWQ, GGUF, FP8        | 91.6            | 91.6            | 91.6            | 183 / 366*                      | 366 / 733*                      | 366 / 733*                      | 733 / 1466*                    | 733 / 1466*                     | -                              | 1466 / 2932*                    |
| NVIDIA RTX 6000 Ada        | 9000-11000 | Workstation, Server  | 300       | 49140        | 960                | 18176 | GPTQ, AWQ, GGUF, FP8        | 91.1            | 91.1            | 91.1            | 182 / 364*                      | 364 / 728*                      | 364 / 728*                      | 728 / 1457*                    | 728 / 1457*                     | -                              | 1457 / 2914*                    |

### Ampere

| Graphics Processor<br/>GPU | Price, $ | GPU type             | TDP, W | VRAM, Mb | Bandwidth<br/>GB/s | CUDA  | Supported<br/>quantizations | FP32<br/>TFLOPS | BF16<br/>TFLOPS | FP16<br/>TFLOPS | TF32<br/>Tensor Core<br/>TFLOPS | BF16<br/>Tensor Core<br/>TFLOPS | FP16<br/>Tensor Core<br/>TFLOPS | FP8<br/>Tensor Core<br/>TFLOPS | INT8<br/>Tensor Core<br/>TFLOPS | FP4<br/>Tensor Core<br/>TFLOPS | INT4<br/>Tensor Core<br/>TFLOPS |
|----------------------------|----------|----------------------|--------|----------|--------------------|-------|-----------------------------|-----------------|-----------------|-----------------|---------------------------------|---------------------------------|---------------------------------|--------------------------------|---------------------------------|--------------------------------|---------------------------------|
| NVIDIA RTX 3090            | ~1500    | Desktop, Workstation | 350    | 24576    | 936                | 10496 | GPTQ, AWQ, GGUF, FP8**      | 35.58           | 35.58           | 35.58           | 71 / 142*                       | 142 / 284*                      | 142 / 284*                      | -                              | 284 / 568*                      | -                              | 568 / 1136*                     |
| NVIDIA RTX 3090 Ti         | ~2000    | Desktop, Workstation | 450    | 24576    | 1008               | 10752 | GPTQ, AWQ, GGUF, FP8**      | 40.0            | 40.0            | 40.0            | 80 / 160*                       | 160 / 320*                      | 160 / 320*                      | -                              | 320 / 640*                      | -                              | 640 / 1280*                     |
| NVIDIA RTX A5000           | -        | Workstation, Server  | 230    | 24564    | 768                | 8192  | GPTQ, AWQ, GGUF, FP8**      | 27.8            | 27.8            | 27.8            | 55.6 / 111*                     | 111 / 222*                      | 111 / 222*                      | -                              | 222 / 444*                      | -                              | 444 / 888*                      |
| NVIDIA A10                 | ~2500    | Server               | 150    | 23028    | 600                | 9216  | GPTQ, AWQ, GGUF, FP8**      | 31.2            | 31.2            | 31.2            | 62.5 / 125*                     | 125 / 250*                      | 125 / 250*                      | -                              | 250 / 500*                      | -                              | 500 / 1000*                     |
| NVIDIA A100 PCIe 40Gb      | -        | Server               | 250    | 40536    | 1560               | 6912  | GPTQ, AWQ, GGUF, FP8**      | 19.49           | 77.97           | 77.97           | 156 / 312*                      | 312 / 624*                      | 312 / 624*                      | -                              | 624 / 1248*                     | -                              | 1248 / 2496*                    |
| NVIDIA A100 PCIe 80Gb      | -        | Server               | 300    | 81920    | 1935               | 6912  | GPTQ, AWQ, GGUF, FP8**      | 19.49           | 77.97           | 77.97           | 156 / 312*                      | 312 / 624*                      | 312 / 624*                      | -                              | 624 / 1248*                     | -                              | 1248 / 2496*                    |


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
3. \*** Preliminary characteristics calculated based on data from the Internet

### Blackwell

| Graphics Processor<br/>GPU | GPU type             | Architecture | VRAM, Mb | Bandwidth<br/>GB/s | CUDA  | Supported<br/>quantizations | FP32<br/>TFLOPS | BF16<br/>TFLOPS | FP16<br/>TFLOPS | TF32<br/>Tensor Core<br/>TFLOPS | BF16<br/>Tensor Core<br/>TFLOPS | FP16<br/>Tensor Core<br/>TFLOPS | FP8<br/>Tensor Core<br/>TFLOPS | INT8<br/>Tensor Core<br/>TFLOPS | FP4<br/>Tensor Core<br/>TFLOPS | INT4<br/>Tensor Core<br/>TFLOPS |
|----------------------------|----------------------|--------------|----------|--------------------|-------|-----------------------------|-----------------|-----------------|-----------------|---------------------------------|---------------------------------|---------------------------------|--------------------------------|---------------------------------|--------------------------------|---------------------------------|
| NVIDIA RTX 5090***         | Desktop, Workstation | Blackwell    | 32752*** | 1792               | 21760 | GPTQ, AWQ, GGUF, FP8, FP4   | 104.8           | 104.8           | 104.8           | 210 / 419*                      | 419 / 838*                      | 419 / 838*                      | 838 / 1676*                    | 838 / 1676*                     | 1676 / 3352*                   | 1676 / 3352*                    |

### Hopper

| Graphics Processor<br/>GPU | GPU type | Architecture | VRAM, Mb | Bandwidth<br/>GB/s | CUDA  | Supported<br/>quantizations | FP32<br/>TFLOPS | BF16<br/>TFLOPS | FP16<br/>TFLOPS | TF32<br/>Tensor Core<br/>TFLOPS | BF16<br/>Tensor Core<br/>TFLOPS | FP16<br/>Tensor Core<br/>TFLOPS | FP8<br/>Tensor Core<br/>TFLOPS | INT8<br/>Tensor Core<br/>TFLOPS | FP4<br/>Tensor Core<br/>TFLOPS | INT4<br/>Tensor Core<br/>TFLOPS |
|----------------------------|----------|--------------|----------|--------------------|-------|-----------------------------|-----------------|-----------------|-----------------|---------------------------------|---------------------------------|---------------------------------|--------------------------------|---------------------------------|--------------------------------|---------------------------------|
| NVIDIA H100 PCIe           | Server   | Hopper       | 81559    | 2000               | 14592 | GPTQ, AWQ, GGUF, FP8        | 51.2            | 102.4           | 102.4           | 378 / 756*                      | 756 / 1513*                     | 756 / 1513*                     | 1513 / 3026*                   | 1513 / 3026*                    | -                              | 3026 / 6052*                    |

### Ada Lovelace

| Graphics Processor<br/>GPU | GPU type             | Architecture | VRAM, Mb     | Bandwidth<br/>GB/s | CUDA  | Supported<br/>quantizations | FP32<br/>TFLOPS | BF16<br/>TFLOPS | FP16<br/>TFLOPS | TF32<br/>Tensor Core<br/>TFLOPS | BF16<br/>Tensor Core<br/>TFLOPS | FP16<br/>Tensor Core<br/>TFLOPS | FP8<br/>Tensor Core<br/>TFLOPS | INT8<br/>Tensor Core<br/>TFLOPS | FP4<br/>Tensor Core<br/>TFLOPS | INT4<br/>Tensor Core<br/>TFLOPS |
|----------------------------|----------------------|--------------|--------------|--------------------|-------|-----------------------------|-----------------|-----------------|-----------------|---------------------------------|---------------------------------|---------------------------------|--------------------------------|---------------------------------|--------------------------------|---------------------------------|
| NVIDIA RTX 4060            | Desktop              | Ada Lovelace | 8188         | 272                | 3072  | GPTQ, AWQ, GGUF, FP8        | 15.11           | 15.11           | 15.11           | 30 / 60*                        | 60 / 121*                       | 60 / 121*                       | 121 / 242*                     | 121 / 242*                      | -                              | 242 / 484*                      |
| NVIDIA RTX 4060 Ti         | Desktop              | Ada Lovelace | 8188 / 16380 | 288                | 4352  | GPTQ, AWQ, GGUF, FP8        | 22.06           | 22.06           | 22.06           | 44 / 88*                        | 88 / 177*                       | 88 / 177*                       | 177 / 353*                     | 177 / 353*                      | -                              | 353 / 706*                      |
| NVIDIA RTX 4070            | Desktop              | Ada Lovelace | 12282        | 504                | 5888  | GPTQ, AWQ, GGUF, FP8        | 29.15           | 29.15           | 29.15           | 58 / 116*                       | 116 / 233*                      | 116 / 233*                      | 233 / 466*                     | 233 / 466*                      | -                              | 466 / 932*                      |
| NVIDIA RTX 4070 SUPER      | Desktop              | Ada Lovelace | 12282        | 504                | 7168  | GPTQ, AWQ, GGUF, FP8        | 35.48           | 35.48           | 35.48           | 71 / 142*                       | 142 / 284*                      | 142 / 284*                      | 284 / 568*                     | 284 / 568*                      | -                              | 568 / 1136                      |
| NVIDIA RTX 4070 Ti         | Desktop              | Ada Lovelace | 12282        | 504                | 7680  | GPTQ, AWQ, GGUF, FP8        | 40.09           | 40.09           | 40.09           | 80 / 160*                       | 160 / 320*                      | 160 / 320*                      | 320 / 640*                     | 320 / 641*                      | -                              | 641 / 1282*                     |
| NVIDIA RTX 4070 Ti SUPER   | Desktop              | Ada Lovelace | 16376        | 672                | 8448  | GPTQ, AWQ, GGUF, FP8        | 44.10           | 44.10           | 44.10           | 88 / 176*                       | 176 / 352*                      | 176 / 352*                      | 352 / 704*                     | 352 / 704*                      | -                              | 704 / 1408*                     |
| NVIDIA RTX 4080 SUPER      | Desktop              | Ada Lovelace | 16376        | 736                | 10240 | GPTQ, AWQ, GGUF, FP8        | 52.22           | 52.22           | 52.22           | 104 / 209*                      | 209 / 418*                      | 209 / 418*                      | 418 / 836*                     | 418 / 836*                      | -                              | 836 / 1672*                     |
| NVIDIA RTX 4090            | Desktop, Workstation | Ada Lovelace | 24564        | 1008               | 16384 | GPTQ, AWQ, GGUF, FP8        | 82.6            | 82.6            | 82.6            | 165 / 330*                      | 330 / 660*                      | 330 / 660*                      | 660 / 1321*                    | 660 / 1321*                     | -                              | 1321 / 2642*                    |
| NVIDIA L4                  | Server               | Ada Lovelace | 23034        | 300                | 7424  | GPTQ, AWQ, GGUF, FP8        | 30.3            | 30.3            | 30.3            | 60 / 121*                       | 121 / 242*                      | 121 / 242*                      | 242 / 485*                     | 242 / 485*                      | -                              | 485 / 970*                      |
| NVIDIA L40S                | Server               | Ada Lovelace | 46068        | 864                | 18176 | GPTQ, AWQ, GGUF, FP8        | 91.6            | 91.6            | 91.6            | 183 / 366*                      | 366 / 733*                      | 366 / 733*                      | 733 / 1466*                    | 733 / 1466*                     | -                              | 1466 / 2932*                    |
| NVIDIA RTX 6000 Ada        | Workstation, Server  | Ada Lovelace | 49140        | 960                | 18176 | GPTQ, AWQ, GGUF, FP8        | 91.1            | 91.1            | 91.1            | 182 / 364*                      | 364 / 728*                      | 364 / 728*                      | 728 / 1457*                    | 728 / 1457*                     | -                              | 1457 / 2914*                    |

### Ampere

| Graphics Processor<br/>GPU | GPU type | Architecture | VRAM, Mb | Bandwidth<br/>GB/s | CUDA | Supported<br/>quantizations | FP32<br/>TFLOPS | BF16<br/>TFLOPS | FP16<br/>TFLOPS | TF32<br/>Tensor Core<br/>TFLOPS | BF16<br/>Tensor Core<br/>TFLOPS | FP16<br/>Tensor Core<br/>TFLOPS | FP8<br/>Tensor Core<br/>TFLOPS | INT8<br/>Tensor Core<br/>TFLOPS | FP4<br/>Tensor Core<br/>TFLOPS | INT4<br/>Tensor Core<br/>TFLOPS |
|----------------------------|----------|--------------|----------|--------------------|------|-----------------------------|-----------------|-----------------|-----------------|---------------------------------|---------------------------------|---------------------------------|--------------------------------|---------------------------------|--------------------------------|---------------------------------|
| NVIDIA A10                 | Server   | Ampere       | 23028    | 600                | 9216 | GPTQ, AWQ, GGUF, FP8**      | 31.2            | 31.2            | 31.2            | 62.5 / 125*                     | 125 / 250*                      | 125 / 250*                      | -                              | 250 / 500*                      | -                              | 500 / 1000*                     |


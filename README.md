# KRminer

GPU miner for Quantus (QTC) and Pearl (PRL) on NVIDIA RTX 30, 40 and 50 series. Linux x86_64 and HiveOS.
Dev fee 2%.

**Website and downloads: [krminer.com](https://krminer.com)**

[![KRminer console mining Pearl on an RTX 5070 Ti and an RTX 5080](https://krminer.com/console.webp)](https://krminer.com)

## Algorithms

| Coin | Algorithm | Option | Devices | Dev fee |
|---|---|---|---|---:|
| Quantus Network (QTC) | Poseidon2 | `-a quantus` (default) | NVIDIA | 2.00% |
| Pearl (PRL) | pearlhash | `-a pearl` | NVIDIA | 2.00% |

The dev fee is 2% of mining time (120 s every 100 min) on a separate connection; your pool session stays open.

### Supported GPUs

- **RTX 50 series** Blackwell, `sm_120`, driver 570 or newer
- **RTX 40 series** Ada Lovelace, `sm_89`
- **RTX 30 series** Ampere, `sm_86`

## Performance

**Quantus** (`-a quantus`)

| GPU | Core MHz | Rate | GPU W | MH/s per W | Build |
|---|---:|---:|---:|---:|---|
| RTX 5080 `sm_120` | 2500 | **882 MH/s** | 201 | 4.4 | 1.0.40 |
| RTX 5070 Ti `sm_120` | 2500 | **730 MH/s** | 178 | 4.1 | 1.0.40 |
| RTX 4070 Ti `sm_89` | 2400 | **604 MH/s** | 159 | 3.8 | 1.0.40 |
| RTX 5060 Ti `sm_120` | 2692 | **409 MH/s** | 99 | 4.1 | 1.0.40 |
| RTX 3070 `sm_86` | 1500 | **290 MH/s** | 103 | 2.8 | 1.0.35 |

**Pearl** (`-a pearl`)

| GPU | Core MHz | Rate | GPU W | TH/s per W | Build |
|---|---:|---:|---:|---:|---|
| RTX 5080 `sm_120` | 2500 | **205.0 TH/s** | 203 | 1.01 | 1.0.40 |
| RTX 5070 Ti `sm_120` | 2500 | **168.7 TH/s** | 178 | 0.95 | 1.0.40 |
| RTX 4070 Ti `sm_89` | 2400 | **140.6 TH/s** | 143 | 0.98 | 1.0.45 |
| RTX 5060 Ti `sm_120` | 2692 | **94.9 TH/s** | 98 | 0.97 | 1.0.40 |
| RTX 3070 `sm_86` | 1650 | **73.5 TH/s** | 121 | 0.61 | 1.0.45 |

## Download

The current version and its checksums are on **[krminer.com](https://krminer.com)**. Every version is kept at
`https://dl.krminer.com/<version>/`:

| File | For |
|---|---|
| `krminer-<version>.tar.gz` | HiveOS custom miner (flight sheet installation URL) |
| `krminer-<version>-linux.tar.gz` | Linux x86_64: Ubuntu, RaveOS, mmpOS, minerstat custom miner |
| `SHA256SUMS` | SHA-256 checksums of both archives |

Requirements: Linux x86_64 with glibc 2.28 or newer (Ubuntu 20.04 or newer); NVIDIA driver with CUDA 12 (RTX 50:
driver 570 or newer). No Windows or macOS build for now.

## Quick start

### Linux

```bash
wget https://dl.krminer.com/<version>/krminer-<version>-linux.tar.gz
tar -xzf krminer-<version>-linux.tar.gz
cd krminer-<version>-linux
./krminer pool -o stratum+tcp://qtc.kryptex.network:7049 -u WALLET/WORKER
./krminer pool -a pearl -o stratum+tcp://prl.kryptex.network:7048 -u WALLET.WORKER
```

### HiveOS

Flight sheet with a custom miner: see [hiveos.md](hiveos.md).

## Pools

| Coin | Pool | URL | SSL | User |
|---|---|---|---|---|
| Quantus | Kryptex | `stratum+tcp://qtc.kryptex.network:7049` | `stratum+ssl://qtc.kryptex.network:8049` | `WALLET/WORKER` |
| Quantus | Suprnova | `stratum+tcp://quantus.suprnova.cc:7071` | `stratum+ssl://quantus.suprnova.cc:7074` | `WALLET.WORKER` |
| Pearl | Kryptex | `stratum+tcp://prl.kryptex.network:7048` | `stratum+ssl://prl.kryptex.network:8048` | `WALLET.WORKER` |
| Pearl | PearlFortune | `stratum+tcp://global.pearlfortune.org:8888` | same port (self-signed) | `WALLET.WORKER` |
| Pearl | LuckyPool | `stratum+tcp://pearl-eu1.luckypool.io:3360` | same port (self-signed) | `WALLET.WORKER` |
| Pearl | HeroMiners | `stratum+tcp://pearl.herominers.com:1200` | same port | `WALLET.WORKER` |
| Pearl | AlphaPool | `stratum+tcp://us1.alphapool.tech:5571` | none | `WALLET.WORKER` |
| Pearl | F2Pool | `stratum+tcp://pearl.f2pool.com:5500` | none | `ACCOUNT.WORKER` (F2Pool account) |

## Options

Pool, GPU selection, tuning (core and memory clocks, power limit) and output options: [parameters.md](parameters.md).

## Support

Bug reports and questions: [GitHub Issues](https://github.com/kr-miner/krminer/issues).

## License

Copyright (c) 2026 the KRminer author. All rights reserved. See [LICENSE](LICENSE).

You may use KRminer to mine on hardware you own or are authorized to use. Without written permission you may not
modify, reverse engineer, decompile or disassemble it (including its embedded GPU kernels), or redistribute,
sublicense or sell it.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED. IN NO EVENT SHALL THE AUTHOR BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY ARISING FROM THE SOFTWARE OR ITS USE.

Third-party components keep their own licenses: parts of KRminer come from
[Quantus-Network/quantus-miner](https://github.com/Quantus-Network/quantus-miner) (Apache License 2.0,
[third-party/quantus-miner.LICENSE](third-party/quantus-miner.LICENSE)). The bundled cudarc loader keeps its
MIT/Apache licenses.

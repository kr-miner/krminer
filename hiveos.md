# KRminer on HiveOS

## Flight sheet

| Field | Quantus | Pearl |
|---|---|---|
| Miner | Custom | Custom |
| Installation URL | `https://dl.krminer.com/<version>/krminer-<version>.tar.gz` (current version on [krminer.com](https://krminer.com)) | same |
| Hash algorithm | `qpow` | `pearlhash` |
| Wallet and worker template | `WALLET/%WORKER_NAME%` | `WALLET.%WORKER_NAME%` |
| Pool URL | `qtc-sg.kryptex.network:7049` (SSL: `stratum+ssl://qtc-sg.kryptex.network:8049`) | `prl.kryptex.network:7048` (SSL: `stratum+ssl://prl.kryptex.network:8048`) |
| Pass | `x` | `x` |
| Extra config arguments | options from [parameters.md](parameters.md), for example `--gpu-power-limit 150` | same |

Parameters: [parameters.md](parameters.md)

## Manual install

```bash
tar -xzf krminer-<version>.tar.gz -C /hive/miners/custom
```

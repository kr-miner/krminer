# KRminer parameters

```bash
krminer pool -a pearl -o stratum+tcp://prl.kryptex.network:7048 -u WALLET.WORKER -d 0,2 --gpu-power-limit 150
```

## Pool

`-o` takes `stratum+tcp://` (plain) or `stratum+ssl://` (TLS) URLs.

| Parameter | Example | Default |
|---|---|---|
| `-a`, `--algo` | `-a quantus`, `-a pearl`, `-a noid` | `quantus` |
| `-o`, `--url` | `-o stratum+tcp://prl.kryptex.network:7048` | |
| `-u`, `--user` | `-u WALLET.WORKER` | |
| `-p`, `--pass` | `-p x` | `x` |
| `--no-strict-ssl` | `--no-strict-ssl` | check, warn if untrusted |
| `--pearl-stratum` | `--pearl-stratum v1` | `auto` |

Parano1d uses `-a noid` (aliases `parano1d`, `poseidon2b`) with an `o1ADDRESS.WORKER`
login. Suprnova endpoints are `stratum+tcp://noid.suprnova.cc:3337` and
`stratum+ssl://noid.suprnova.cc:3341`. Pool mining and `benchmark` on NVIDIA are supported;
CPU, WGPU and local-node modes are unavailable for NOID. `--pearl-stratum` applies only to Pearl.

## GPU

| Parameter | Example | Default |
|---|---|---|
| `-d`, `--gpu-list` | `-d 0,2` | all |
| `--list-devices` | `krminer --list-devices` | |

## Tuning (NVIDIA)

| Parameter | Example | Default |
|---|---|---|
| `--gpu-core-clock` | `--gpu-core-clock 2460` | unchanged |
| `--gpu-core-offset` | `--gpu-core-offset 200` | unchanged |
| `--gpu-memory-clock` | `--gpu-memory-clock 810` | unchanged |
| `--gpu-memory-offset` | `--gpu-memory-offset -2000` | unchanged |
| `--gpu-power-limit` | `--gpu-power-limit 150,_,140` | unchanged |

## Output

| Parameter | Example | Default |
|---|---|---|
| `-l`, `--log-file` | `-l miner.log` | |
| `--no-color` | `--no-color` | |
| `--disable-gpu-extra-sensors` | `--disable-gpu-extra-sensors` | RTX 50 hotspot/VRAM shown (Linux, root) |
| `-v`, `--verbose` | `-v` | |

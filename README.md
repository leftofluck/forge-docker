# forge-docker

> [!CAUTION]
> 非公式/Unofficial

https://github.com/antoinezambelli/forge のrelease更新時、dokcer imageを自動的に作る

## Usage

```bash
docker pull ghcr.io/leftofluck/forge:latest
```

## Docker Compose

[このサンプル](https://github.com/antoinezambelli/forge#docker)の場合
```yaml
services:
  forge:
    image: ghcr.io/leftofluck/forge:latest
    container_name: forge-proxy
    ports:
      - "8081:8081"
    command: >
      --backend-url http://host.docker.internal:8000
      --backend vllm
      --budget-mode manual
      --budget-tokens 8192
    extra_hosts:
      - "host.docker.internal:host-gateway"
```
```bash
docker compose up -d
```

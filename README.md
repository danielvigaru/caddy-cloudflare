## How to use this in docker compose?

```yaml
caddy:
  build:
    context: ./local-images/caddy-cloudflare # path to the folder containing the Dockerfile
    dockerfile: Dockerfile
  container_name: Caddy
  volumes:
    - ${BASE_DIR}/config/caddy/Caddyfile:/etc/caddy/Caddyfile
    - ${BASE_DIR}/config/caddy:/config
    - ${BASE_DIR}/data/caddy/caddy_data:/data
  ports:
    - 80:80
    - 443:443
    - 443:443/udp
  restart: unless-stopped
```

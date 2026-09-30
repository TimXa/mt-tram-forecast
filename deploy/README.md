# Coder-ы demo: HTTPS deploy

1. Point the domain's A record at the server (DNS only, no proxy) and open ports 80 and 443.
2. On the server, in the repo root: `DEMO_DOMAIN=<domain> docker compose -f docker-compose.yml -f deploy/compose.caddy.yml up -d --build backend frontend caddy`
3. Caddy gets the certificate on the first request. Check `https://<domain>/api/v1/meta`.

`ml/artifacts` must be present (it is in the repo). No secrets are needed.

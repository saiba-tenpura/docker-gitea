# Docker Gitea
My personal Gitea docker compose setup incl. an external Traefik instance for serving the web interface.

## Configuring OIDC
In order to to configure you first need an identity provider (IdP) in this example Authentik is used for since it can also be setup via my other [repository](https://github.com/saiba-tenpura/docker-authentik).

```bash
gitea admin auth add-oauth \
  --name "Authentik" \
  --provider "openidConnect" \
  --key "<OIDC_CLIENT_ID>" \
  --secret "<OIDC_CLIENT_SECRET>" \
  --auto-discover-url "https://<AUTHENTIK_URL>/application/o/gitea/.well-known/openid-configuration" \
  --scopes "email profile"
```

## License
[MIT](./LICENSE)

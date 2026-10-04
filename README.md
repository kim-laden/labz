# Lab'z

Lab'z is the public lab at [https://laden.no/llz/](https://laden.no/llz/). This repository is the site only.

Copyright Laden AS (Org.nr. 937 285 833). Lab'z is open source under the MIT License. See [LICENSE](LICENSE). The Laden name, mark and brand are trademarks of Laden AS and are not given away by that licence.

## What is here

- `site/` is the live Lab'z pages from the Ubuntu host: the front page, labs, challenges, and the rest of the public tree.
- `docker/` is the container stack that runs beside it: the API (`docker/api/server.py`, `schema.sql`) and the web container. `docker/docker-compose.yml` is the Compose file.

The Docker copy on the site is [https://laden.no/docker/llz/](https://laden.no/docker/llz/).

## Run the API

```bash
cp docker/.env.example docker/.env
# set LADEN_JWT_SECRET in docker/.env
docker compose -f docker/docker-compose.yml up --build
```

The published `server.py` does not ship a real signing secret. Set `LADEN_JWT_SECRET` yourself. The user database is not in this repository. The API creates its own empty database from `schema.sql` when you run it.

## Copyright and licence

Copyright Laden AS (Org.nr. 937 285 833). Lab'z is open source under the MIT License. See [LICENSE](LICENSE).

The Laden name, mark and brand are trademarks of Laden AS. The open-source licence covers the code. It does not give away the name, mark or brand.

## Not in this repo

Secrets are not here. That includes `.env`, the Lab'z API token, the JWT signing secret, and the user database (`laden.db`). `docker/.env.example` only names the setting.

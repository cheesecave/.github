# CheeseCave

**CheeseCave** is a self-hosted repository service for models and datasets, compatible with
Hugging Face clients (`huggingface_hub`, `git` + Git LFS). It is an independent fork of
[KohakuHub](https://github.com/KohakuBlueleaf/KohakuHub) and runs as three containers you control.

<p align="center">
  <img src="https://raw.githubusercontent.com/cheesecave/.github/main/profile/assets/01-home.png" alt="CheeseCave home page" width="90%">
</p>

## Screenshots

| Repository page | File view |
| --- | --- |
| <img src="https://raw.githubusercontent.com/cheesecave/.github/main/profile/assets/02-repo.png" alt="Repository page" width="100%"> | <img src="https://raw.githubusercontent.com/cheesecave/.github/main/profile/assets/03-file.png" alt="File view" width="100%"> |

| Administration |
| --- |
| <img src="https://raw.githubusercontent.com/cheesecave/.github/main/profile/assets/04-admin-login.png" alt="Admin login" width="60%"> |

The screenshots come from a local instance built from the published images.

## Quick start

You need Docker with Compose v2. No build is required.

```sh
git clone https://github.com/cheesecave/cheesecave-backend.git
cd cheesecave-backend
python3 scripts/generate_docker_compose.py --generate-config   # writes .env with random secrets
docker compose up -d                                           # pulls ghcr.io/cheesecave/* images
```

Then open:

- Website: <http://127.0.0.1:28080>
- Admin: <http://127.0.0.1:28080/admin/>

To pin a release, set `CHEESECAVE_VERSION` in `.env` (the default is `latest`). Edit `.env` before
the first start if you serve it on a public address (`KOHAKU_HUB_BASE_URL`). The full guide is in
[cheesecave-backend](https://github.com/cheesecave/cheesecave-backend/blob/main/docs/deployment/docker.md).

## Repositories

| Repository | What it contains |
| --- | --- |
| [cheesecave-backend](https://github.com/cheesecave/cheesecave-backend) | API, Git/LFS, background jobs, storage, migrations and Compose |
| [cheesecave-web](https://github.com/cheesecave/cheesecave-web) | Website: repository browsing, files and previews |
| [cheesecave-admin](https://github.com/cheesecave/cheesecave-admin) | Administration: users, quotas and runtime settings |

Container images: `ghcr.io/cheesecave/cheesecave-backend`, `cheesecave-web` and `cheesecave-admin`.

## Licence and origin

CheeseCave is licensed under [AGPL-3.0](https://github.com/cheesecave/cheesecave-backend/blob/main/LICENSE).
Original attribution to KohakuHub, its authors and the DeepGHS fork is kept in
[NOTICE.md](https://github.com/cheesecave/cheesecave-backend/blob/main/NOTICE.md).
Branding notes are in [BRANDING.md](https://github.com/cheesecave/cheesecave-backend/blob/main/BRANDING.md).

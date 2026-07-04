# dv-platform-config

The GitOps destination repo that stores non-production dbt DAG configuration (`config.json` + `deploy.yml`) per environment/domain/DAG. This is the target of every config-agent pull request.

> One of four repos in a two-agent system — see the full architecture in the main repo: https://github.com/hasan-tavakoli/dbt-factory-agent

## Directory structure

Configs are organized as:

```
<environment>/<domain>/<dag-name>/
├── config.json
└── deploy/
    └── deploy.yml
```

For example: `dv-stage-eu/sports/dv-sports-elt/`.

Environments currently present:
- `dv-dev-eu/`
- `dv-stage-eu/`
- `dv-stage-sa/`

## What each file is

- **`config.json`** — the DAG/job config that Airflow reads to build the DAG (schedule, tags, steps, env variables, etc.).
- **`deploy/deploy.yml`** — the Cloud Run execution definition: container image, service account, and region.

## How it's updated

The config-agent opens pull requests against this repo. A human reviews and merges each one — there is no auto-merge. Airflow/Composer reads the merged state here to build DAGs.

## Scope

Non-production configurations only.

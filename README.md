# dv-platform-config

This repository holds non-production dbt DAG configurations for development (`dev`) and staging (`stage`) environments.

## Repository Structure

Each DAG configuration lives under its respective environment directory according to the following layout:
`<env-subtree>/<domain>/<dag-name>/`

Inside each DAG directory, you will find:
- `config.json`: The core configuration for the DAG.
- `deploy/deploy.yml`: The deployment definition.

### Environments
- `dv-dev-eu/`: Development environment for Europe.
- `dv-stage-eu/`: Staging environment for Europe.
- `dv-stage-sa/`: Staging environment for South America.
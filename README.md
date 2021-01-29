# etl-graph

**This repository now lives in [docker-etl/jobs/etl-graph](https://github.com/mozilla/docker-etl/tree/main/jobs/etl-graph). This repository has been archived for documentation purposes.**

Queries and visualization around BigQuery usage.

![screenshot](screenshot.png)

## Quickstart

Scrape the data.

```bash
# optional: virtualenv
python3 -m venv venv
source venv/bin/activate
pip-compile
pip3 install -r requirements.txt

# generate edgelist from query logs
python3 -m etl-graph query-logs query_log_edges
python3 -m etl-graph query-logs query_log_nodes

# generate final index
python3 -m etl-graph index
```

Alternatively:

```bash
./scripts/scrape.sh
```

Start the web client for visualization.

```bash
npm run dev
```

Deploy to hosting.

```bash
./scripts/deploy-data.sh
./scripts/deploy-site.sh
```

## Development

A docker image is included for job scheduling. It is recommended to use your
host for developing the web application to avoid networking issues.

```bash
cp .env.template .env
# configure the environment file as necessary
docker-compose build

# automatically runs scrape and deploy
docker-compose run --rm app

# shell into a running container
docker-compose run --rm app bash
```

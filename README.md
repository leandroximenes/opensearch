# Docker Compose Repository

This repository contains Docker Compose configuration files for setting up containers using Docker.
Prerequisites

Make sure you have Docker and Docker Compose installed on your system.

* Docker Installation Guide
* Docker Compose Installation Guide

# Usage
## Setup

    git clone https://github.com/leandroximenes/opensearch
    cd opensearch

Start the containers defined in docker-compose.yml:

    docker-compose up -d

## Configuration

* **opensearch-node1**: OpenSearch container with configuration  options:
    * `discovery.type`: Single-node for development (`single-node`).
    * `ES_JAVA_OPTS`: JVM options for heap size (`-Xms512m -Xmx512m`).
    * `bootstrap.memory_lock`: Lock memory on startup (`true`).
    * `OPENSEARCH_INITIAL_ADMIN_PASSWORD`: Initial admin password (`Str0ngP@ssw0rd!`).

* **opensearch-dashboards**: (Commented out in `docker-compose.yml`) Container for OpenSearch Dashboards, typically configured with:
    * `OPENSEARCH_HOSTS`: Array of OpenSearch host URLs (`http://opensearch-node1:9200`).

## Accessing Services

**OpenSearch**: Accessible at `http://localhost:9200`
**OpenSearch** Dashboards: Accessible at `http://localhost:5601` (if uncommented and configured).

## Additional Notes

* Adjust memory (-Xms and -Xmx) and other configurations in `docker-compose.yml` as needed for your environment.
* Secure sensitive information like passwords using Docker secrets or other secure methods.

## License

This repository is licensed under the MIT License. See the LICENSE file for details.

# Monitoring

Project that seeks to provide a guide for the necessary configurations and base files that integrate the tools:

- [Grafana](https://grafana.com/)
- [Prometheus](https://prometheus.io/)
- [cAdvisor](https://github.com/google/cadvisor)

_Read this in other languages: [English](README.md), [Spanish](README.spa.md)._

## 1. Pre requisits

For the project to work you need:

- Docker Engine
- Docker Compose (Comes by default in the latest versions)
## 2. Usage

There are two use cases:

- **Test:** Give an example with basic configurations
- **Production:** Requires advanced settings

### 2.1. Test

The _test_ case is used to see a simple example with everything preconfigured, it works by default with the [docker-compose.yml](PRUEBA/docker-compose.yml) file.

Enter the [TESTS](PRUEBA/) folder.

<ins>Execute</ins>

```sh
docker-compose up -d
```

### 2.2. Production

The production case is used to create an almost production-ready environment, it works by default with the [docker-compose.yml](PRODUCCION/docker-compose.yml) file.

#### 2.2.1. `.env` & `.grafana-env`

Two files must be configured:

- **.env**: Environment variables, ports (Example in _PRODUCCION_ > **.env.example**)
- **.grafana-env**: Grafana server variables (Example in _PRODUCCION_ > **.grafana-env.example**)

<ins>.env</ins>

- **PROM_HOST_PORT**: Host port for prometheus (Our team)
- **PROM_CONTAINER_PORT**: Container port for prometheus
- **GF_HOST_PORT**: Host port for grafana (Our team)
- **GF_CONTAINER_PORT**: Container port for grafana

<ins>.grafana-env</ins>

- **GF_SECURITY_ADMIN_USER**: Grafana admin user
- **GF_SECURITY_ADMIN_PASSWORD**: Admin password

#### <ins>2.2.2. Execution</ins>

Enter the folder _PRODUCCION_

<ins>Execute</ins>

```
docker-compose up -d
```

## 3. Files

Structure of files:

- **TEST** (Example environment - Pre-configurations made)
  - **Grafana**: Directory containing Grafana configurations
  - **Prometheus**: Directory containing Prometheus configurations
  - **docker-compose.yml** (Basic): File containing the docker images used for the example case
- **PRODUCTION**
  - **Grafana**: Directory containing Grafana configurations
  - **Prometheus**: Directory containing Prometheus configurations
  - **docker-compose-prod.yml** (Advanced): File that contains the docker images, as it is intended for production, it will request more data and will assemble separate volumes

### <ins>3.1. Grafana</ins>

Contains basic configurations of grafana server
  - datasource.yml:
  - grafana.ini: Configuration obtained from[here](https://github.com/grafana/grafana/blob/main/conf/defaults.ini)

### <ins>3.2. Prometheus</ins>

Setting
  - prometheus.yml: Basic configuration of prometheus (The targets to monitor are found)

## 4. Guides

I attach some guides that helped me to enrich, understand and assemble the examples:

- How To Run Prometheus and Grafana using Docker Compose (v3.7 Docker Compose):
  - https://techviewleo.com/run-prometheus-and-grafana-using-docker-compose/
- Monitoring a Linux host with Prometheus, Node Exporter, and Docker Compose (v3.8 Docker Compose)
  - https://grafana.com/docs/grafana-cloud/quickstart/docker-compose-linux/
- Server Monitoring // Prometheus and Grafana Tutorial (YouTube)
  -  https://www.youtube.com/watch?v=9TJx7QTrTyo&list=PLs242WxerbCQAnJnbGrpRLM1stU2EP7im&index=10
-  Guia avanzada de Docker Compose (Esta guia me ayudo para el uso de multiples docker-compose.yml)
   -  https://runnable.com/docker/advanced-docker-compose-configuration
- Guia para uso de variables de entorno
  -  https://towardsdatascience.com/a-complete-guide-to-using-environment-variables-and-files-with-docker-and-compose-4549c21dc6af
-  Guia Video - Monitoreo con Docker (Grafana, Prometheus, Node-Exporter, cAdvisor)
   -  https://www.youtube.com/watch?v=PCJwJpbln6Q
-  Guia Video - WMI Exporter para Windows
   -  https://www.youtube.com/watch?v=kVCePoVbyJ0
## 5. Docker Hub

Official links of Docker images used in the project:

- **Grafana**: https://hub.docker.com/r/grafana/grafana-enterprise
- **Prometheus**: https://hub.docker.com/r/prom/prometheus
- **Node Exporter** : https://hub.docker.com/r/prom/node-exporter



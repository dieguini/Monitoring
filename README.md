# Grafana, Prometheus y Docker Compose

Este proyecto sirve como guia para ver las configuraciones necesarias y tener los archivos base del sitio

## Archivos

La estructura de los archivos es la siguiente:

### Grafana 

Contiene las configuraciones basicas de un servidor grafana
  - datasource.yml:
  - grafana.ini: Configuración obtenida de https://github.com/grafana/grafana/blob/main/conf/defaults.ini

### Prometheus

Configuración
  - prometheus.yml: Configuracion básica de prometheus (Se encuentran los targets a monitorear)

## Guias

Guias y referencias que me ayudaron a entender y montar el ejemplo:

- How To Run Prometheus and Grafana using Docker Compose (v3.7 Docker Compose):
  - https://techviewleo.com/run-prometheus-and-grafana-using-docker-compose/
- Guia oficial de Grafana (v3.8 Docker Compose)
  - Monitoring a Linux host with Prometheus, Node Exporter, and Docker Compose

## Docker Hub

Links oficiales de Docker Hub

- Grafana: https://hub.docker.com/r/grafana/grafana-enterprise
- Prometheus: https://hub.docker.com/r/prom/prometheus
- Node Exporter: https://hub.docker.com/r/prom/node-exporter



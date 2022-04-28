# Grafana, Prometheus y Docker Compose

Este proyecto sirve como guia para ver las configuraciones necesarias y tener los archivos base del sitio

## Archivos

La estructura es la siguiente:

- **Grafana**: Directorio que contiene las configuraciones para Grafana
- **Prometheus**: Directorio que contiene las configuraciones para Prometheus
- **docker-compose.yml**: Archivo que contiene las imagenes de docker usadas

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
- Monitoring a Linux host with Prometheus, Node Exporter, and Docker Compose (v3.8 Docker Compose)
  - https://grafana.com/docs/grafana-cloud/quickstart/docker-compose-linux/
- Server Monitoring // Prometheus and Grafana Tutorial (YouTube)
  -  https://www.youtube.com/watch?v=9TJx7QTrTyo&list=PLs242WxerbCQAnJnbGrpRLM1stU2EP7im&index=10
-  Guia avanzada de Docker Compose (Esta guia me ayudo para el uso de multiples docker-compose.yml)
   -  https://runnable.com/docker/advanced-docker-compose-configuration

## Docker Hub

Links oficiales de imagenes Docker usadas:

- **Grafana**: https://hub.docker.com/r/grafana/grafana-enterprise
- **Prometheus**: https://hub.docker.com/r/prom/prometheus
- **Node Exporter** : https://hub.docker.com/r/prom/node-exporter



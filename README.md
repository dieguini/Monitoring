# Grafana, Prometheus y Docker Compose

Este proyecto sirve como guia para ver las configuraciones necesarias y tener los archivos base del sitio

## 1. Pre requisitos

Para que el proyecto funcione se necesita:

- Docker Engine
- Docker Compose (Viene por defecto en las ultimas versiones)
## 2. Levanta el proyecto

Para levantar el servicio existen los casos de:

- **Prueba:** Da un ejemplo con configuraciones basicas
- **Produccion:** Requiere configuraciones avanzadas
### <ins>2.1. Prueba</ins>

El caso de prueba se usa para poder ver un ejemplo sencillo con todo pre configurado, este funciona por defecto con el archivo **_docker-compose.yml_**

Ejecutar

```
docker-compose up -d
```
o
```
docker-compose -f docker-compose.yml up -d
```

### <ins>2.2. Produccion</ins>

(Preparando produccion...)

## 3. Archivos

La estructura es la siguiente:

- **PRUEBA** (Entorno de ejemplo - Pre configuraciones realizadas)
  - **Grafana**: Directorio que contiene configuraciones de Grafana
  - **Prometheus**: Directorio que contiene configuraciones de Prometheus
- **PRODUCCION**
  - **Grafana**: Directorio que contiene configuraciones de Grafana
  - **Prometheus**: Directorio que contiene configuraciones de Prometheus

- **docker-compose.yml** (Basico): Archivo que contiene las imagenes de docker usadas para el caso de ejemplo
- **docker-compose-prod.yml** (Avanzado): Archivo que contiene las imagenes de docker, como esta pensado para produccion pedira mas datos y armara volumenes separados

### <ins>3.1. Grafana</ins>

Contiene las configuraciones basicas de un servidor grafana
  - datasource.yml:
  - grafana.ini: Configuración obtenida de [aqui](https://github.com/grafana/grafana/blob/main/conf/defaults.ini)

### <ins>3.2. Prometheus</ins>

Configuración
  - prometheus.yml: Configuracion básica de prometheus (Se encuentran los targets a monitorear)

## 4. Guias

Adjunto algunas guias que me ayudaron a enriquecer, entender y montar los ejemplos:

- How To Run Prometheus and Grafana using Docker Compose (v3.7 Docker Compose):
  - https://techviewleo.com/run-prometheus-and-grafana-using-docker-compose/
- Monitoring a Linux host with Prometheus, Node Exporter, and Docker Compose (v3.8 Docker Compose)
  - https://grafana.com/docs/grafana-cloud/quickstart/docker-compose-linux/
- Server Monitoring // Prometheus and Grafana Tutorial (YouTube)
  -  https://www.youtube.com/watch?v=9TJx7QTrTyo&list=PLs242WxerbCQAnJnbGrpRLM1stU2EP7im&index=10
-  Guia avanzada de Docker Compose (Esta guia me ayudo para el uso de multiples docker-compose.yml)
   -  https://runnable.com/docker/advanced-docker-compose-configuration

## 5. Docker Hub

Links oficiales de imagenes Docker usadas en el proyecto:

- **Grafana**: https://hub.docker.com/r/grafana/grafana-enterprise
- **Prometheus**: https://hub.docker.com/r/prom/prometheus
- **Node Exporter** : https://hub.docker.com/r/prom/node-exporter



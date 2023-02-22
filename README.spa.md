# Monitoring

Proyecto que busca brindar una guía para las configuraciones necesarias y archivos base que integran las herramientas:

- [Grafana](https://grafana.com/)
- [Prometheus](https://prometheus.io/)
- [cAdvisor](https://github.com/google/cadvisor)

_Read this in other languages: [English](README.md), [Spanish](README.spa.md)._

## 1. Pre requisitos

Para que el proyecto funcione se necesita:

- Docker Engine
- Docker Compose (Viene por defecto en las ultimas versiones)
## 2. Uso

Existen dos casos de uso:

- **Prueba:** Da un ejemplo con configuraciones basicas
- **Produccion:** Requiere configuraciones avanzadas

### 2.1. Prueba

El caso de _prueba_ se usa para poder ver un ejemplo sencillo con todo pre configurado, este funciona por defecto con el archivo [docker-compose.yml](PRUEBA/docker-compose.yml).

Ingrese a [PRUEBA](PRUEBA/) folder.

<ins>Ejecutar</ins>

```sh
docker-compose up -d
```

### 2.2. Producción

El caso de produccion se usa para crear un entorno casi listo para un despliegue, este funciona por defecto con el archivo [docker-compose.yml](PRODUCCION/docker-compose.yml)

#### 2.2.1. `.env` y `.grafana-env`

Se debe configurar dos archivos:

- **.env**: Variables de entorno, puertos (Ejemplo en _PRODUCCION_ > **.env.example**)
- **.grafana-env**: Variables de servidor grafana (Ejemplo en _PRODUCCION_ > **.grafana-env.example**)

<ins>.env</ins>

- **PROM_HOST_PORT**: Puerto del host para prometheus (Nuestro equipo)
- **PROM_CONTAINER_PORT**: Puerto contenedor para prometheus
- **GF_HOST_PORT**: Puerto del host para grafana (Nuestro equipo)
- **GF_CONTAINER_PORT**: Puerto contenedor para grafana

<ins>.grafana-env</ins>

- **GF_SECURITY_ADMIN_USER**: Usuario admin para grafana
- **GF_SECURITY_ADMIN_PASSWORD**: Contraseña de admin

#### <ins>2.2.2. Ejecución</ins>

Ingresar a la carpeta de _PRODUCCION_

<ins>Ejecutar</ins>

```
docker-compose up -d
```

## 3. Archivos

Estructura de archivos:

- **PRUEBA** (Entorno de ejemplo - Pre configuraciones realizadas)
  - **Grafana**: Directorio que contiene configuraciones de Grafana
  - **Prometheus**: Directorio que contiene configuraciones de Prometheus
  - **docker-compose.yml** (Basico): Archivo que contiene las imagenes de docker usadas para el caso de ejemplo
- **PRODUCCION**
  - **Grafana**: Directorio que contiene configuraciones de Grafana
  - **Prometheus**: Directorio que contiene configuraciones de Prometheus
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
- Guia para uso de variables de entorno
  -  https://towardsdatascience.com/a-complete-guide-to-using-environment-variables-and-files-with-docker-and-compose-4549c21dc6af
-  Guia Video - Monitoreo con Docker (Grafana, Prometheus, Node-Exporter, cAdvisor)
   -  https://www.youtube.com/watch?v=PCJwJpbln6Q
-  Guia Video - WMI Exporter para Windows
   -  https://www.youtube.com/watch?v=kVCePoVbyJ0
## 5. Docker Hub

Links oficiales de imagenes Docker usadas en el proyecto:

- **Grafana**: https://hub.docker.com/r/grafana/grafana-enterprise
- **Prometheus**: https://hub.docker.com/r/prom/prometheus
- **Node Exporter** : https://hub.docker.com/r/prom/node-exporter



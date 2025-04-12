# N8N Queue - Solución Docker Compose Lista para Usar

![N8N](https://n8n.io/favicon.ico) 

## 🚀 Descripción

Este proyecto ofrece una implementación de **N8N en modo QUEUE** totalmente configurada y lista para usar con Docker Compose. La solución incluye todo lo necesario para comenzar a trabajar inmediatamente con flujos de trabajo automatizados y procesamiento de tareas en cola. Este metodo es optimo y escalable, porque podriamos agregar mas workers a nuestro compose según necesitemos.

![Queue Mode](https://docs.n8n.io/_images/hosting/scaling/queue-mode-flow.png)

## 📋 Características

- **N8N en modo QUEUE**: Optimizado para el procesamiento ordenado y eficiente de tareas
- **Despliegue con Docker Compose**: Configuración plug-and-play lista para producción
- **Base de datos Postgres incluida**: Persistencia de datos robusta para tus flujos de trabajo, en este modo de trabajo n8n recomienda usar postgres, ya que por defecto usan SQLite, que no soporta conexiones simultaneas.
- **Base de datos Redis**: Redis funciona como cola de mensajes, para que los workers vayan trabajando asincronamente, quitandole carga de trabajo al main de n8n.
- **init-data.sh**: Script de inicialización de base de datos postgres

## 🛠️ Requisitos previos

- Docker Compose

## ⚡ Instalación rápida

1. Clona este repositorio:
   ```bash
   git clone https://github.com/Mondin0/n8n-queue-docker.git
   cd n8n-queue-docker
   ```

2. Inicia los servicios:
   ```bash
   docker-compose up -d
   ```

3. Accede a N8N:
   ```
   http://localhost:5678
   ```

## 🏗️ Estructura

```
.
├── docker-compose.yml    # Configuración principal
├── .env                  # Variables de entorno
└── init-data.sh          # Script de inicialización de base de datos postgres
```

## ⚙️ Configuración

El archivo `docker-compose.yml` incluye cuatro servicios principales:

- **n8n**: Configurado en modo QUEUE para procesamiento optimizado de flujos
- **Postgres DB**: Base de datos de persistencia de n8n
- **Redis**: base de datos en memoria para asignar tareas a los workers
- **1 worker n8n**: ejecutor de los workflows

## 🔄 Uso

Una vez iniciados los servicios, puedes acceder a:

- **N8N**: `http://localhost:5678`

## 🔒 Variables de entorno

Revisa y personaliza las variables en el archivo `.env` según tus necesidades.

## 🔧 Personalización

Si deseas utilizar N8N con alguna base de datos MariaDB y phpMyAdmin, simplemente puedes instanciar esos servicios en el archivo `docker-compose.yml`.

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Si tienes sugerencias o mejoras, no dudes en crear un Pull Request o abrir un Issue.

## 🙏 Agradecimientos

- [N8N](https://n8n.io/) por su fantástica herramienta de automatización
- La comunidad de Docker por hacer el despliegue tan sencillo

---

⭐ **¿Encuentras útil este proyecto?** ¡Deja una estrella en el repositorio! ⭐

<h1 align="center">Grogu 🚀</h1>

<p align="center">
  <em>A scalable, distributed Discord bot architecture built for high availability and modularity.</em>
</p>

## 🎯 Objetivo
Grogu es un bot de Discord diseñado bajo un paradigma de **arquitectura distribuida**. El objetivo principal es garantizar la estabilidad y la capacidad de respuesta del bot mediante la separación de responsabilidades: los componentes que requieren persistencia de estado están aislados de la lógica de procesamiento, permitiendo que las partes *stateless* escalen de manera horizontal según la demanda.

## 🏗 Arquitectura del Sistema
El bot se divide en dos capas principales para asegurar un rendimiento óptimo:

* **Capa Stateless (Processing Engine):**
  - Contiene la lógica central del bot y el manejo de eventos de la Discord API.
  - Diseñada para ser efímera y escalar indefinidamente en Kubernetes para gestionar picos de tráfico.
* **Capa Stateful (Persistence Layer):**
  - Encargada de gestionar la persistencia de datos y el estado compartido.
  - Asegura la consistencia de la información requerida por el bot.

**Orquestación:** Todo el sistema se despliega sobre **Kubernetes**, permitiendo una gestión eficiente de los recursos y alta disponibilidad de los servicios.

## 🛠 Tecnologías y Stack
* **Lenguajes:** Python
* **Contenedores:** Docker (Imágenes almacenadas en Docker Hub)
* **CI/CD:** GitLab CI/CD Pipelines
* **Orquestación:** Kubernetes
* **Plataforma:** Discord API

## 🚀 Workflow y Despliegue
El sistema utiliza un flujo de trabajo de integración y despliegue continuo (CI/CD) automatizado:

1. **Desarrollo:** Realizas tus cambios en el código.
2. **Push:** Al hacer `push` a GitLab, se dispara automáticamente la pipeline.
3. **Build & Push:** La pipeline construye la imagen de Docker, la testea y la sube al registro (Docker Hub).
4. **Deploy:** La pipeline actualiza el despliegue en el clúster de Kubernetes.

### ¿Cómo empezar?
Basta con trabajar sobre el repositorio:

1. **Fork & Clone:** Haz un fork del repositorio y clónalo localmente.
```bash
   git clone https://gitlab.com/Marco-A-Silva/grogu.git

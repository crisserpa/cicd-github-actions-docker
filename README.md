# ⚙️ Pipeline CI/CD: Automatización con GitHub Actions

## 🎯 Objetivo del Proyecto
Implementar la cultura DevOps automatizando el proceso de Integración Continua (CI). El objetivo es que cada cambio en el código fuente dispare automáticamente una validación y construcción del contenedor sin intervención manual.

## 🏗️ Arquitectura y Tecnologías
* **Control de Versiones:** Git & GitHub.
* **Automatización CI/CD:** GitHub Actions (Workflows).
* **Contenedores:** Docker.

## ⚙️ Proceso de Despliegue
1. Creación de la estructura de directorios `.github/workflows/` en el repositorio.
2. Desarrollo de un archivo de configuración en formato YAML (`build.yml`).
3. Definición del evento "Trigger": Ejecutar el pipeline únicamente cuando se realice un comando `git push` a la rama `main`.
4. Configuración del Runner (servidor temporal de GitHub) para ejecutar el proceso de `docker build`.

## 🛠️ Troubleshooting (Resolución de Problemas)
**Problema:** El pipeline de GitHub Actions fallaba inmediatamente después de hacer push, arrojando un error de sintaxis ("syntax error").
**Solución:** Al utilizar archivos YAML, la indentación (los espacios a la izquierda) es estrictamente estructural. Se revisó el código detectando que un bloque de comandos estaba tabulado incorrectamente en lugar de usar espacios. Se corrigió la indentación del archivo `.yml`, se realizó un nuevo `commit`, y el pipeline ejecutó la construcción de la imagen de Docker de manera 100% exitosa.

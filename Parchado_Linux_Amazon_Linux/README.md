# Playbooks de Ansible para Parchado en Amazon Linux 2 y Amazon Linux 2023 ![Ansible](https://img.shields.io/badge/Ansible-2.9%2B-blue) ![Amazon Linux](https://img.shields.io/badge/Amazon%20Linux-2%20%7C%202023-green)

## Descripción

Este conjunto de playbooks de Ansible está diseñado para automatizar las tareas de parchado de seguridad y validaciones posteriores en instancias que ejecutan **Amazon Linux 2** y **Amazon Linux 2023**. Los playbooks han sido ajustados para soportar ambas versiones de Amazon Linux y manejan las diferencias entre `yum` (Amazon Linux 2) y `dnf` (Amazon Linux 2023).

### Archivos:

- `1a_Tareas_Previas.yaml`: ![Shield](https://img.shields.io/badge/Tareas%20Previas-%E2%9C%85-brightgreen) Valida y muestra la lista de parches de seguridad requeridos antes del proceso de parchado.
- `2a_Tareas_Implementacion.yaml`: ![Shield](https://img.shields.io/badge/Tareas%20de%20Implementaci%C3%B3n-%E2%9A%A1-yellow) Ejecuta la instalación de parches de seguridad, reinicia el servidor y valida la conexión después del reinicio.
- `3a_Tareas_Posteriores.yaml`: ![Shield](https://img.shields.io/badge/Tareas%20Posteriores-%F0%9F%94%8E-blue) Realiza validaciones después del parchado, como la comprobación del estado del sistema y servicios, y copia los resultados a un bucket de Amazon S3.

## Requisitos Previos ![Requisitos](https://img.shields.io/badge/Requisitos-%E2%9C%85-blue)

1. **Ansible**: Este conjunto de playbooks requiere que Ansible esté instalado en el servidor de control.
2. **AWS CLI**: Para la tarea que copia resultados al bucket de S3, el `AWS CLI` debe estar instalado y configurado correctamente en las instancias Amazon Linux.
3. **Permisos Sudo**: Las tareas requieren acceso `sudo` en los servidores.

## Tareas Incluidas

### 1. Tareas Previas (`1a_Tareas_Previas.yaml`) ![Previas](https://img.shields.io/badge/Tareas%20Previas-%E2%9C%85-brightgreen)
- Crea un archivo de registro para almacenar resultados de la validación previa.
- Verifica y muestra la lista de parches de seguridad disponibles.
- Guarda la lista de parches en un archivo en el servidor.
- Verifica el estado del sistema, como hora, hostname y dirección IP.

### 2. Tareas de Implementación (`2a_Tareas_Implementacion.yaml`) ![Implementación](https://img.shields.io/badge/Implementaci%C3%B3n-%E2%9A%A1-yellow)
- Ejecuta la instalación de parches de seguridad con `yum` o `dnf` según la versión de Amazon Linux.
- Registra y muestra los resultados de la instalación de parches.
- Reinicia el servidor después de instalar los parches.
- Valida la reconexión SSH tras el reinicio.
- Comprueba la conectividad a Internet para garantizar que no haya problemas de red.

### 3. Tareas Posteriores (`3a_Tareas_Posteriores.yaml`) ![Posteriores](https://img.shields.io/badge/Tareas%20Posteriores-%F0%9F%94%8E-blue)
- Verifica y guarda la evidencia de los parches instalados.
- Verifica la hora del sistema, hostname y dirección IP.
- Verifica el tiempo de actividad (uptime) posterior al reinicio.
- Realiza una validación del estado de los servicios y la performance del sistema.
- Copia el resultado del parchado a un bucket de Amazon S3.

## Uso ![Uso](https://img.shields.io/badge/Uso-%F0%9F%92%A1-lightgrey)

1. Clonar el repositorio en el servidor de control donde Ansible está instalado.
2. Ejecutar los playbooks de la siguiente manera:

   ```bash
   ansible-playbook 1a_Tareas_Previas.yaml
   ansible-playbook 2a_Tareas_Implementacion.yaml
   ansible-playbook 3a_Tareas_Posteriores.yaml

## Personalización
Modificar el archivo /usr/local/bin/aws s3 cp en las tareas de los playbooks si deseas cambiar el destino del bucket de Amazon S3.
Ajustar los tiempos de espera y los parámetros de reinicio según tus necesidades.

## Requisitos del Sistema
Amazon Linux 2 o Amazon Linux 2023
AWS CLI configurado en las instancias si se utiliza la funcionalidad de S3
Ansible 2.9+

## Contribuciones
Las contribuciones son bienvenidas. Si deseas mejorar los playbooks o añadir nuevas funcionalidades, no dudes en hacer un fork del repositorio y enviar un pull request.
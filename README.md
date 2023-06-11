# Administración de Parches de Seguridad con Ansible

Este repositorio contiene playbooks de Ansible para administrar parches de seguridad en servidores Linux. Los playbooks realizan una serie de tareas previas para validar el estado del sistema antes de aplicar los parches.

### Algunas de las características clave de este playbook incluyen:

🔒 Validación exhaustiva del sistema antes de aplicar los parches.

📋 Generación de informes detallados sobre el estado del sistema y los parches requeridos.

💻 Reinicio automático del servidor posterior al parchado, garantizando la implementación efectiva de los parches.

📈 Monitoreo del rendimiento y el estado de los servicios después del parchado.

## Tareas Previas


## Tareas Previas

### Requisitos previos

- Crear directorio temporal para almacenar resultados del parchado en `/tmp/parchado`.
- Crear archivo para almacenar resultados de las tareas posteriores en `/tmp/parchado/tareas_previas.txt`.

### Validación de Kernel

- Validar el kernel del sistema.
- Mostrar la validación del kernel.
- Guardar el resultado de la validación del kernel en `/tmp/parchado/tareas_previas.txt`.

### Validar fecha de último reinicio

- Validar la fecha de último reinicio del sistema.
- Mostrar la fecha de último reinicio.
- Guardar el resultado de la validación de la fecha de último reinicio en `/tmp/parchado/tareas_previas.txt`.

### Validar los procesos que necesitan reinicio y sus correspondientes archivos binarios (CentOS, Red Hat, Ubuntu)

- Validar los procesos que necesitan reinicio y sus correspondientes archivos binarios.
- Mostrar los procesos que necesitan reinicio y sus correspondientes archivos binarios.
- Guardar el resultado de la validación de los procesos que necesitan reinicio y sus correspondientes archivos binarios en `/tmp/parchado/tareas_previas.txt`.

### Verificar servicios que requieren reinicio (Ubuntu)

- Verificar los servicios que requieren reinicio.
- Mostrar los servicios que requieren reinicio.
- Guardar el resultado de la validación de los servicios que requieren reinicio en `/tmp/parchado/tareas_previas.txt`.

### Validar salida a internet para descarga de parches

- Validar la salida a internet para descarga de parches.
- Mostrar la salida a internet para descarga de parches.
- Guardar el resultado de la validación de la salida a internet para descarga de parches en `/tmp/parchado/tareas_previas.txt`.

### Validar versión de Sistema Operativo

- Validar la versión del Sistema Operativo.
- Mostrar la versión del Sistema Operativo.
- Guardar el resultado de la validación de la versión del Sistema Operativo en `/tmp/parchado/tareas_previas.txt`.

### Validar estado de servicios y performance

- Validar el estado de servicios y performance del sistema.
- Mostrar el estado de servicios y performance.
- Guardar el resultado de la validación del estado de servicios y performance en `/tmp/parchado/tareas_previas.txt`.

### Validar lista de parches requeridos

- Validar la lista de parches requeridos.
- Mostrar la lista de parches requeridos.
- Guardar el resultado de la validación de la lista de parches requeridos en `/tmp/parchado/tareas_previas.txt`.

### Validar espacio en la partición / de cada servidor

- Validar el espacio en la partición / de cada servidor.
- Mostrar el espacio en la partición / de cada servidor.
- Guardar el resultado de la validación del espacio en la partición / de cada servidor en `/tmp/parchado/tareas_previas.txt`.

### Revisar los últimos 50 logs históricos

- Revisar los últimos 50 logs históricos.
- Mostrar los últimos 50 logs históricos.
- Guardar el resultado de la validación de los últimos 50 logs históricos en `/tmp/parchado/tareas_previas.txt`.

## Tareas Implementación

### Requisitos previos

- Crear archivo para almacenar resultados de las tareas de Implementación en `/tmp/parchado/tareas_implementacion.txt`.

### Ejecutar instalación de parches de seguridad

- Ejecutar la instalación de parches de seguridad.
- Mostrar la instalación de parches de seguridad.
- Guardar el resultado de la instalación de parches de seguridad en `/tmp/parchado/tareas_implementacion.txt`.

### Reinicio de servidor posterior al parchado

- Reiniciar el servidor posterior al parchado.

### Validar conexión SSH después de 1 min posterior al reinicio

- Validar la conexión SSH después de 1 minuto posterior al reinicio.

### Validar salida a internet para descartar problemas de conectividad

- Validar la salida a internet para descartar problemas de conectividad.
- Mostrar la salida a internet.

## Tareas Posteriores

### Requisitos previos

- Crear archivo para almacenar resultados de las tareas Posteriores en `/tmp/parchado/tareas_posteriores.txt`.

### Guardar evidencias de parches instalados en un Archivo .txt en el servidor

- Guardar evidencias de los parches instalados en un archivo .txt en el servidor.
- Mostrar las evidencias de los parches instalados en un archivo .txt en el servidor.
- Guardar el resultado de las evidencias de los parches instalados en un archivo .txt en el servidor en `/tmp/parchado/tareas_posteriores.txt`.

### Observar la hora del sistema, el hostname y la IP

- Observar la hora del sistema, el hostname y la IP.
- Mostrar la hora del sistema, el hostname y la IP.
- Guardar el resultado de la hora del sistema, el hostname y la IP en `/tmp/parchado/tareas_posteriores.txt`.

### Validar reinicio de servidor posterior al parchado

- Validar el reinicio del servidor posterior al parchado.
- Mostrar el reinicio del servidor posterior al parchado.
- Guardar el resultado del reinicio del servidor posterior al parchado en `/tmp/parchado/tareas_posteriores.txt`.

### Validar estado de servicios y performance

- Validar el estado de servicios y performance del sistema.
- Mostrar el estado de servicios y performance.
- Guardar el resultado de la validación del estado de servicios y performance en `/tmp/parchado/tareas_posteriores.txt`.

### Copiar Resultado del parchado al servidor ansible

- Copiar el resultado del parchado al servidor Ansible.
- Mostrar el resultado enviado al servidor Ansible.
- Guardar el resultado del envío al servidor Ansible en `/tmp/parchado/tareas_posteriores.txt`.

### Eliminar carpeta parchado

- Eliminar la carpeta "parchado" que contiene las pruebas del parchado.

---

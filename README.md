# Administración de Parches de Seguridad con Ansible 🚀

![Ansible](https://img.shields.io/badge/Automation-Ansible-blue?logo=ansible&logoColor=white) ![Security](https://img.shields.io/badge/Security-Patches-green?logo=security&logoColor=white)

Este repositorio contiene una serie de **playbooks de Ansible** diseñados para administrar parches de seguridad en servidores **Linux** y **Windows**. Los playbooks incluyen tareas de validación previas, instalación de parches y comprobaciones posteriores para asegurar la correcta aplicación de los parches y el buen estado del sistema.

## Playbooks incluidos

### 1. Tareas Previas 📝
Este playbook realiza una serie de validaciones importantes antes de aplicar los parches de seguridad:

- **Crear directorios y archivos temporales** para registrar los resultados.
- **Validar la versión del kernel**.
- **Verificar la fecha del último reinicio**.
- **Comprobar si hay procesos y servicios que necesitan reinicio**.
- **Verificar la conectividad a Internet** para asegurar que los parches puedan descargarse.
- **Comprobar la versión del sistema operativo** y el **espacio en disco**.
- **Revisar los últimos 50 eventos de seguridad**.

📂 Resultados guardados en `/tmp/parchado/tareas_previas.txt` o `C:\parchado\tareas_previas.txt` (Windows).

### 2. Tareas de Implementación 💻
Este playbook se encarga de la instalación de los parches de seguridad en el sistema:

- **Instalación de parches de seguridad**: Utiliza herramientas como `PSWindowsUpdate` en Windows o `apt/yum` en Linux.
- **Reinicio del servidor** posterior a la instalación.
- **Validar la conexión SSH** tras el reinicio.
- **Comprobar la conectividad a Internet** después de aplicar los parches.

📂 Resultados guardados en `/tmp/parchado/tareas_implementacion.txt` o `C:\parchado\tareas_implementacion.txt` (Windows).

### 3. Tareas Posteriores ✅
En este playbook se realizan las validaciones después de haber aplicado los parches:

- **Guardar evidencias de parches instalados** en un archivo de texto.
- **Comprobar la hora del sistema, el hostname y la IP**.
- **Verificar si el servidor fue reiniciado** correctamente tras el parchado.
- **Validar el estado de los servicios y el rendimiento**.
- **Historial de actualizaciones instaladas**: Muestra el historial reciente de actualizaciones.

📂 Resultados guardados en `/tmp/parchado/tareas_posteriores.txt` o `C:\parchado\tareas_posteriores.txt` (Windows).

### 4. Borrar Pruebas del Parchado 🧹
Este playbook elimina los archivos temporales y carpetas creadas durante el proceso de parchado:

- **Eliminar la carpeta `parchado`** utilizada para almacenar los resultados del proceso de parchado.

---

## Ejecución de los Playbooks 📜

Cada playbook puede ejecutarse individualmente con el siguiente comando:

```bash
ansible-playbook <nombre_del_playbook>.yaml
```

## 📜 Requisitos

- Ansible instalado.
- Configuración de WinRM para servidores Windows.
- PSWindowsUpdate instalado en servidores Windows para la gestión de actualizaciones.


## Contribuciones 🤝
Si deseas mejorar este repositorio o agregar nuevas funcionalidades, ¡las contribuciones son bienvenidas! Abre un pull request o reporta un issue para cualquier mejora o corrección.
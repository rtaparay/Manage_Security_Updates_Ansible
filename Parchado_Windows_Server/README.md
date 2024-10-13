# Ansible Playbooks para Parchado en Windows Server 💻
Este repositorio contiene una serie de playbooks de Ansible diseñados para gestionar el proceso de parchado, validaciones y limpieza en servidores Windows. Las tareas incluyen validaciones previas, instalación de actualizaciones críticas, validaciones posteriores y eliminación de archivos temporales creados durante el proceso de parchado.

## 📋 Requisitos
- Ansible instalado.
- PSWindowsUpdate debe estar instalado en los servidores Windows para la gestión de actualizaciones.
- Conexión WinRM configurada para la comunicación entre Ansible y el servidor Windows.

## 📋 Playbooks
### 📋 1a_Tareas_Previas.yaml

- Valida la versión del sistema operativo y espacio en disco.
- Verifica reinicios pendientes y muestra la fecha del último reinicio.
- Comprueba la conectividad a internet y revisa las actualizaciones pendientes.
- Revisa los últimos 50 eventos de seguridad en los logs del sistema.


### 📋 2a_Tareas_Implementacion.yaml

- Instala parches de seguridad (Security Updates, Critical Updates) utilizando PSWindowsUpdate.
- Reinicia el servidor tras la instalación de parches.
- Valida la conectividad a internet posterior al reinicio para descartar problemas de conectividad.

### 📋 3a_Tareas_Posteriores.yaml

- Verifica la hora del sistema, hostname e IP.
- Valida el reinicio posterior al parchado y el estado de los servicios.
- Muestra y guarda el historial de actualizaciones instaladas.
- Opcional: Tareas para desinstalar una actualización específica, si es necesario.

### 📋 4a_Tareas_Posteriores_Borrar_Pruebas_Parchado.yaml

- Elimina los archivos temporales de pruebas y carpetas utilizadas para almacenar los resultados del proceso de parchado.
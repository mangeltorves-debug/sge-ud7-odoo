Registro de Errores y Validaciones Preventivas en la Instalación de Odoo SGE
Durante el proceso de implantación y despliegue de Odoo , no se registraron fallos críticos inesperados, 
debido a una rigurosa fase previa de diagnóstico y validación del entorno host.
A continuación, se detallan las comprobaciones preventivas realizadas y se documenta un escenario típico de incidencia controlada
simulado, reproducido y resuelto durante las pruebas de robustez del sistema.
1. Comprobaciones Preventivas para Evitar Errores
Antes de levantar los contenedores de Odoo y PostgreSQL, se ejecutaron las siguientes comprobaciones en el sistema operativo host:
   1. Verificación de Puertos Libres:
   Se comprobó mediante ss -tulpn | grep 8069 y ss -tulpn | grep 5432 que los puertos estándar de Odoo (8069, 8072) y PostgreSQL (5432)
    no estuvieran ocupados por servicios previos (como instalaciones nativas huérfanas de PostgreSQL o instancias locales de servidores web).
   2. Validación de Versión y Motor Docker:
   Se revisó el estado de Docker Engine (docker --version y docker compose version) asegurando compatibilidad con los drivers de red tipo bridge y 
   volúmenes montados con permisos UID/GID correctos.
   3. Disponibilidad de Recursos del Sistema:
   Se comprobó la disponibilidad de memoria RAM libre (>4 GB) y espacio en disco SSD mediante df -h y free -m para evitar interrupciones 
   por falta de memoria virtual o caché de transacciones ACID en PostgreSQL.
2. Registro de Incidencias 
Para cumplir con la trazabilidad técnica del SGE, se documenta a continuación un caso típico de error que suele presentarse en entornos de desarrollo 
y su respectiva resolución documentada:
Incidencia Simulada: Conflicto de asignación en el puerto principal de acceso (Bind for 0.0.0.0:8069 failed: port is already allocated).
Causa Raíz: El puerto TCP 8069 ya estaba siendo utilizado en el sistema operativo host por otra aplicación (en este caso, una instancia 
previa de prueba ejecutada directamente en Python sin Docker).
Solución Aplicada: Se identificó el proceso bloqueante mediante la orden sudo lsof -i :8069, se detuvo dicho proceso con kill -9 <PID>, 
o bien se modificó el archivo de orquestación docker-compose.yml para reasignar el puerto externo del contenedor a un puerto libre 
(por ejemplo, cambiando la regla de mapeo a 8070:8069), permitiendo el arranque exitoso de los servicios.
Fuente Consultada: Documentación oficial de Docker (Networking en contenedores) y foro de la comunidad Odoo (sección de despliegues en contenedores).
Configuraciones de ServerFort, una por una.
La presentación solo nombra las piezas, así que te explico qué implica configurar cada una. Todo se monta sobre 
dos máquinas virtuales: el Ubuntu Server y el Ubuntu Client, desde el que se hacen las pruebas y la conexión remota.

1. Red y segmentación
VLAN 10, Administración: red desde la que se gestionan los equipos y servidores. Solo debería acceder el administrador.
VLAN 20, Usuarios: red de los equipos de trabajo, con acceso limitado a los recursos corporativos.
VLAN 30, Servidores: servicios internos como DNS, LDAP, archivos, monitorización y backup.
VLAN 40, DMZ: zona con los servicios expuestos a Internet (la web). Si la comprometen, no debería dar acceso al resto.
VLAN 50, Laboratorio: zona aislada para pentesting y simulacros de ataque, sin riesgo para la red real.
IPv4: plan de direccionamiento, una subred por VLAN.
Firewall central: conecta las zonas y hace el NAT (salida a Internet), las reglas entre VLANs y la VPN.

2. Servicios
DNS: resuelve nombres internos (por ejemplo web.serverfort.local) para no depender de IPs.
DHCP: reparte IPs, puerta de enlace y DNS a los equipos de cada red.
SSH: administración remota con claves públicas en lugar de contraseñas, más políticas de acceso.
Apache + HTTPS: servidor web en la DMZ con certificado para cifrar el tráfico.
Samba: comparte archivos con permisos por usuario o grupo, para que cada uno vea solo lo suyo.
WireGuard (VPN): acceso remoto cifrado a la red interna desde fuera.

3. Seguridad y hardening
Hardening del sistema:
SSH seguro (sin login de root, solo claves, puerto y usuarios restringidos).
Root asegurado.
Solo los servicios imprescindibles activos.
Actualizaciones de seguridad al día.
Firewall por zonas: una política distinta para cada zona, con los puertos mínimos abiertos y todo lo demás denegado.
Control de accesos: sudo limitado, usuarios organizados en grupos, permisos de archivos ajustados y política de contraseñas (longitud, complejidad, caducidad).
Suricata (IDS/IPS): analiza el tráfico y detecta o bloquea comportamientos sospechosos como escaneos o intentos de intrusión. Está listado como ampliación.

4. Monitorización y alertas
Prometheus: recoge métricas de servidores y servicios a intervalos regulares.
Grafana: dashboards con CPU, RAM, disco, red y disponibilidad.
Alertmanager: envía notificaciones cuando una métrica supera un umbral (disco lleno, servicio caído).
Logs centralizados: los registros de todas las máquinas en un solo sitio para revisarlos con comodidad.
Simulación de incidentes: provocar fallos para comprobar que se detectan y avisan.

5. Backups y continuidad
Estrategia 3-2-1: 3 copias de los datos, en 2 tipos de soporte distintos y 1 fuera del sitio. Con frecuencia diaria, semanal y mensual, y una política de retención.
Protección: compresión, cifrado y almacenamiento separado del servidor original.
Validación: verificación automática de que las copias son legibles y no están corruptas.
Restauración: borrar datos del laboratorio a propósito y recuperarlos, como prueba real.
Plan de Disaster Recovery: documento con los pasos para recuperar todo tras un desastre grave.

6. Automatización (infraestructura como código)
Ansible: define en archivos de configuración los usuarios, paquetes, SSH, firewall y servicios. Permite reconstruir la infraestructura desde cero en minutos.
Scripts: automatizan backups, comprobaciones, mantenimiento y tareas repetitivas, y actualizan servicios entre máquinas.
Docker/Podman: ejecuta servicios seleccionados en contenedores. También es una ampliación.

7. Laboratorio de pruebas
Escenarios de fallo: servidor caído, disco lleno, servicio detenido, intentos de acceso por SSH.
Pentest controlado: Nmap, enumeración de servicios y revisión de configuraciones.
Detección: comprobar que Suricata, los logs, las alertas y los dashboards lo registran.
Corrección: reforzar la seguridad y repetir la prueba. El ciclo es ataque → detección → corrección → validación.

8. Identidad (ampliación)
LDAP/FreeIPA: directorio central de usuarios, para que un usuario se autentique una vez y acceda solo a sus recursos.

Qué es imprescindible y qué no
MVP: red segmentada, DNS/DHCP, web, firewall, backups y Prometheus/Grafana básico.
Ampliaciones: Suricata, LDAP/FreeIPA y Docker.
Lo primero que se recortaría si falta tiempo: el laboratorio de pentest.

# Definición de terminado

Una tarea solo se mueve a la columna **Hecho** cuando cumple
TODAS estas condiciones:

## Condiciones generales
- [ ] Está implementada y funciona en la máquina virtual.
- [ ] Se ha probado desde el cliente (o con el comando de comprobación que corresponda).
- [ ] La configuración o el script está subido al repositorio.
- [ ] Está documentada: qué hace, cómo se instala y cómo se prueba.
- [ ] No contiene contraseñas, claves privadas ni datos sensibles.
- [ ] Otro compañero del equipo la ha revisado.
- [ ] El issue está actualizado y cerrado, y la tarjeta está en Hecho.

## Condiciones según el tipo de tarea

**Servicios (DNS, DHCP, web, Samba...)**
- El servicio arranca solo y responde desde el cliente.
- Los puertos necesarios están permitidos en el cortafuegos.

**Seguridad y cortafuegos**
- Se ha comprobado que el tráfico no autorizado se bloquea.
- Los intentos sospechosos quedan registrados en los registros (logs).

**Copias de seguridad**
- Se ha hecho una copia y se ha restaurado con éxito.

**Documentación**
- Está en la carpeta correcta del repositorio y se entiende sin ayuda.

## Flujo de una tarea
Backlog → Por hacer → En curso → En revisión → Hecho

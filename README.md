# ServerFort

Infraestructura Ubuntu Server segura, monitorizada y automatizada para pequeñas empresas.

## Descripción

ServerFort es un proyecto académico de administración de sistemas que propone diseñar e implementar una infraestructura empresarial en máquinas virtuales. Combina redes, servicios Linux, seguridad, monitorización, copias de seguridad y automatización.

## Problema y destinatarios

El proyecto aborda los riesgos de mantener servidores sin una configuración de seguridad adecuada, sin copias automáticas o sin supervisión de fallos. Está orientado a pequeñas empresas y departamentos de IT que no disponen de un administrador de sistemas dedicado a tiempo completo.

## Objetivos

- Diseñar una red segmentada con servicios internos y una DMZ.
- Configurar servicios DNS, DHCP, web y archivos.
- Proteger el acceso mediante firewall, permisos y administración SSH segura.
- Supervisar servidores y servicios con Prometheus y Grafana.
- Realizar copias de seguridad y comprobar la recuperación de datos.
- Automatizar configuraciones y tareas repetitivas mediante Ansible y scripts.
- Documentar la infraestructura y validar su funcionamiento con pruebas controladas.

## Alcance

El producto mínimo incluirá red segmentada, DNS/DHCP, servicio web, firewall, copias de seguridad y monitorización básica. La infraestructura se desplegará en máquinas virtuales.

Suricata, LDAP/FreeIPA y contenedores Docker son ampliaciones propuestas, sujetas al tiempo disponible. Quedan fuera del alcance el desarrollo de aplicaciones propias y el despliegue en hardware físico.

## Equipo

Proyecto Optativo de grado superior, ASIX / DAM.



Los roles de coordinación y documentación se acordarán en la reunión de planificación y se documentarán en el repositorio.

## Estado actual

Fase de arranque y planificación. La infraestructura todavía no está implementada. El alcance y las tecnologías son una propuesta inicial que deberá validarse durante el proyecto.

## Sprint 1: arranque y planificación inicial

Periodo indicado en el enunciado: del 7 al 21 de octubre de 2026.

- [ ] Crear el repositorio y añadir al equipo y al profesorado.
- [ ] Preparar la estructura de carpetas.
- [ ] Crear el GitHub Project y los milestones de Sprint 1 y Sprint 2.
- [ ] Redactar y priorizar un backlog de al menos 15 elementos.
- [ ] Documentar los roles y la Definition of Done.
- [ ] Redactar el primer capítulo de la memoria en LaTeX y compilarlo a PDF.
- [ ] Documentar Planning, seguimiento semanal, Review y Retrospectiva.
- [ ] Comprobar que todos los integrantes tienen aportaciones propias.

Las casillas se actualizarán según el trabajo realizado y las evidencias disponibles.

## Estructura prevista

```text
README.md
docs/
  memoria/          # Fuentes LaTeX y PDF de la memoria
  actas/            # Planificación, seguimiento y revisión
  retrospectivas/   # Mejoras acordadas al cierre de cada sprint
  adr/              # Decisiones técnicas y sus motivos
infra/              # Inventarios y configuración de infraestructura
scripts/            # Automatización y mantenimiento
design/             # Diagramas de red y arquitectura
```

## Organización del trabajo

Cada tarea se registrará como una Issue con descripción, criterios de aceptación, responsable, etiqueta y milestone cuando corresponda. El tablero reflejará su estado: Backlog, Por hacer, En curso, En revisión o Hecho.

Cada integrante realizará sus propios commits. Los cambios relevantes se incorporarán mediante pull requests y revisión de otro compañero, de acuerdo con las instrucciones del módulo. La configuración inicial del repositorio tiene la excepción indicada en el Sprint 1.

La memoria técnica se mantendrá en LaTeX y sus archivos fuente estarán versionados en este repositorio. Las actas recogerán las fechas y los acuerdos reales de las reuniones.

## Tecnologías propuestas

Ubuntu Server y Ubuntu Client, Apache, Samba, WireGuard, Prometheus, Grafana, Alertmanager y Ansible. Las herramientas concretas de DNS, DHCP, firewall y copias de seguridad se elegirán y justificarán durante el diseño.

## Validación prevista

Se comprobarán la conectividad y la resolución de nombres, el acceso a los servicios, el bloqueo de tráfico no autorizado, la detección de incidencias y la restauración de copias. Las pruebas de seguridad se realizarán únicamente sobre las máquinas del laboratorio del proyecto.

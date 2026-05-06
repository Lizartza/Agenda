# Secciones de trabajo

Este archivo define las secciones principales del proyecto Agenda y las responsabilidades de cada chat.

## Regla general

Cada chat debe trabajar solo dentro de su seccion asignada.

Si una tarea requiere cambios en otra seccion:

- No debe modificar directamente esa seccion.
- Debe explicar la dependencia.
- Debe pedir permiso al usuario.
- Debe proponer un prompt para enviar al chat responsable.
- El usuario decidira si abre o usa el chat correspondiente.

Formato recomendado de prompt para otro chat:

```text
Lee NORMAS.md, DECISIONES.md, LOGS.md y SECCIONES.md antes de hacer nada.
Este chat pertenece a la seccion [NOMBRE DE SECCION].
No modifiques archivos salvo que use la palabra clave correspondiente.
Necesito que trabajes en [TAREA CONCRETA] porque [MOTIVO].
```

## 1. Base Android

Responsable de:

- Crear y mantener el proyecto Android base.
- Configurar Kotlin, Jetpack Compose, Material 3 y Navigation Compose.
- Configurar el paquete Android `com.lizartza.agenda`.
- Configurar la estructura inicial del modulo `app`.
- Configurar Hilt base.
- Crear la navegacion inferior con pantallas placeholder.

No debe asumir responsabilidades principales de datos, tareas, eventos, notificaciones o widget salvo para integracion minima necesaria.

## 2. Datos Locales Room

Responsable de:

- Entidades Room.
- Enums.
- TypeConverters.
- DAOs.
- `AgendaDatabase`.
- Repositorios de datos.
- Inicializacion de categorias por defecto.

No debe construir pantallas completas ni flujos visuales salvo ejemplos minimos para validar integracion.

## 3. Tareas

Responsable de:

- Pantalla Tareas.
- Crear, editar y borrar tareas.
- Secciones internas Activas y Completadas.
- Ordenacion por urgencia, prioridad, fecha limite y fecha de creacion.
- Marcar tareas como completadas.
- Reanudar tareas completadas.
- Historial de tareas completadas.

Si necesita cambios en eventos, notificaciones o datos persistentes, debe coordinar con la seccion responsable.

## 4. Calendario/Eventos

Responsable de:

- Pantalla Hoy.
- Pantalla Semana.
- Pantalla Mes.
- Crear, editar y borrar eventos.
- Repeticion simple de eventos.
- Deteccion visual o aviso de solapamientos.
- Visualizacion de bloques vinculados a tareas.

No debe implementar la lista principal de tareas ni la logica de recordatorios fuera de la integracion necesaria.

## 5. Programar Tareas

Responsable de:

- Flujo para asignar una tarea a un bloque de tiempo.
- Crear eventos vinculados a tareas.
- Heredar categoria desde la tarea al evento.
- Mantener la tarea activa tras programarla.
- Seleccion de dia, hora de inicio y duracion.
- Aviso de solapamiento durante la programacion.

Debe coordinar con Tareas, Calendario/Eventos y Datos Locales Room cuando el cambio afecte sus responsabilidades.

## 6. Notificaciones

Responsable de:

- AlarmManager.
- Permisos de notificaciones.
- Programacion de recordatorios.
- Cancelacion y reprogramacion de alarmas al editar o borrar eventos.
- Comportamiento de notificaciones al tocar una alerta.

No debe modificar pantallas o entidades fuera de lo necesario sin coordinar con la seccion correspondiente.

## 7. Widget Hoy

Responsable de:

- Widget de Hoy con Glance.
- Mostrar resumen de eventos y bloques programados para hoy.
- Abrir la app en Hoy al tocar el widget.
- Actualizacion del widget cuando cambien eventos relevantes.
- Evaluar RemoteViews si Glance limita demasiado el widget.

No debe implementar la pantalla Hoy completa ni la logica principal de calendario.

## 8. Ajustes/Categorias

Responsable de:

- Pantalla Ajustes.
- Gestion de categorias.
- Preferencias de recordatorio por defecto.
- Preferencias visuales o de comportamiento que se definan mas adelante.
- Proteccion de la categoria `General`.

Debe coordinar con Datos Locales Room si necesita cambios en estructura de categorias.

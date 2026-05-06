# Logs del proyecto Agenda

Este archivo resume avances relevantes del proyecto en orden cronologico.

## 2026-05-04

- Se creo el repositorio Git local.
- Se conecto el repositorio con GitHub.
- Se crearon `README.md` y `.gitignore`.
- Se subio el primer commit a GitHub.

## 2026-05-05

- Se definio que Codex solo puede modificar archivos cuando el usuario escriba `PROGRAMALO`.
- Se acordo usar `NORMAS.md`, `DECISIONES.md` y `LOGS.md` como documentacion inicial.
- Se dejo `TODO.md` para mas adelante, cuando haya tareas funcionales concretas.
- Se decidio que la app sera una agenda Android independiente.
- Se eligio Kotlin nativo como stack base.
- Se eligio Jetpack Compose para la interfaz principal.
- Se definio que eventos y tareas seran conceptos separados, y que programar una tarea crea bloques de tiempo sin completarla automaticamente.
- Se definio que las tareas tendran prioridad alta, media o baja, estado activa o completada, y fecha limite opcional.
- Se definio que la lista de tareas destacara primero las vencidas o las que venzan en los proximos 7 dias.
- Se separaron las autorizaciones en `PROGRAMALO` para codigo, `DOCUMENTALO` para documentacion y `SUBELO A GITHUB` para commits y push.
- Se definio el modelo inicial de eventos, incluyendo repeticion simple, solapamientos permitidos con aviso y recordatorio por defecto de 1 hora.
- Se definio que eventos y tareas podran usar categorias compartidas con nombre y color.
- Se definio la navegacion principal con barra inferior: Hoy, Semana, Mes, Tareas y Ajustes.
- Se definio que el widget mostrara un resumen informativo de Hoy y abrira la app al tocarlo.
- Se simplificaron los estados de tarea a activa y completada.
- Se definio que las tareas completadas tendran historial, fecha de completado y podran reanudarse.
- Se definieron reglas de edicion y borrado para eventos y tareas, con confirmaciones cuando haya elementos relacionados.

## 2026-05-06

- Se definio el modelo tecnico de datos local con `TaskEntity`, `EventEntity` y `CategoryEntity`.
- Se decidio usar IDs `Long` autogenerados, enums para valores cerrados y tipos `LocalDate`, `LocalTime` y `LocalDateTime` con conversores Room.
- Se decidio organizar la app en un unico modulo Android `app` con paquetes internos `data`, `domain`, `ui`, `notifications` y `widget`.
- Se decidio usar Hilt para inyeccion de dependencias.
- Se decidio usar Jetpack Compose, Material 3, Navigation Compose, Room, Coroutines, Flow, Hilt, AlarmManager y Glance como librerias base.
- Se definio `com.lizartza.agenda` como nombre de paquete Android.

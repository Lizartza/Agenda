# Decisiones del proyecto Agenda

Este archivo registra decisiones tecnicas o de producto importantes, junto con sus motivos.

## Formato recomendado

```md
## YYYY-MM-DD - Titulo de la decision

Decision:
Descripcion breve de lo decidido.

Motivo:
Por que se toma esta decision.

Alternativas consideradas:
- Opcion A
- Opcion B

Consecuencias:
- Efecto practico 1
- Efecto practico 2
```

## 2026-05-05 - Documentacion base del proyecto

Decision:
Usar `NORMAS.md`, `DECISIONES.md` y `LOGS.md` como documentacion inicial del proyecto.

Motivo:
Mantener continuidad entre sesiones o chats sin depender solo del contexto conversacional.

Alternativas consideradas:
- Trabajar solo en un chat.
- Crear tambien `TODO.md` desde el principio.

Consecuencias:
- Las normas estables quedan centralizadas en `NORMAS.md`.
- Las decisiones importantes se registraran en este archivo.
- Los avances relevantes se resumiran en `LOGS.md`.
- `TODO.md` se creara mas adelante si el proyecto lo necesita.

## 2026-05-05 - App Android independiente

Decision:
La agenda sera una aplicacion movil independiente para Android.

Motivo:
El objetivo principal es organizar el dia desde el movil, con integracion propia de Android para notificaciones y widget en pantalla de inicio.

Alternativas consideradas:
- Sincronizar con Google Calendar.
- Crear una app multiplataforma desde el principio.

Consecuencias:
- No habra login ni cuenta de usuario en la primera version.
- No se dependera de Google Calendar ni de servicios externos.
- Los datos se guardaran localmente en el dispositivo.
- La app se centrara primero en Android.

## 2026-05-05 - Kotlin nativo como stack base

Decision:
Usar Kotlin nativo para desarrollar la aplicacion Android.

Motivo:
Kotlin ofrece mejor integracion directa con funciones Android importantes para este proyecto, especialmente widget, notificaciones y persistencia local.

Alternativas consideradas:
- React Native con TypeScript.
- Kotlin nativo Android.

Consecuencias:
- El proyecto se enfocara en Android nativo.
- Se priorizara integracion solida con el sistema frente a multiplataforma.
- La estructura del proyecto seguira patrones modernos de Android.

## 2026-05-05 - Jetpack Compose para la interfaz principal

Decision:
Usar Jetpack Compose para construir la interfaz principal de la app.

Motivo:
Jetpack Compose es la forma moderna recomendada para construir interfaces Android nuevas y permite desarrollar UI directamente en Kotlin.

Alternativas consideradas:
- Jetpack Compose.
- XML clasico.

Consecuencias:
- Las pantallas principales se construiran con composables.
- La UI quedara integrada en Kotlin, reduciendo separacion entre XML y codigo.
- El widget Android se evaluara aparte, usando Glance o RemoteViews/XML segun convenga.

## 2026-05-05 - Eventos y tareas como conceptos separados

Decision:
Eventos y tareas seran conceptos separados. Un evento representa un bloque de tiempo en el calendario. Una tarea representa algo activo o completado que puede recibir uno o varios bloques de tiempo.

Motivo:
La agenda debe servir tanto para registrar compromisos fijos como para decidir a que tarea dedicar tiempo cuando haya un hueco disponible.

Alternativas consideradas:
- Usar un unico tipo de elemento de agenda para todo.
- Convertir una tarea en evento y eliminarla de la lista de pendientes.
- Mantener eventos y tareas separados, permitiendo vincular eventos a tareas.

Consecuencias:
- Los eventos pueden existir sin estar vinculados a ninguna tarea.
- Una tarea puede tener varios eventos asociados en distintos dias u horarios.
- Programar una tarea no la completa ni la elimina.
- Una tarea solo deja de aparecer como activa cuando el usuario la marca como completada.
- Los eventos y tareas no tendran descripcion en la primera version; el titulo sera suficiente.

## 2026-05-05 - Prioridad, estado y orden de tareas

Decision:
Las tareas tendran prioridad, estado y fecha limite opcional. La lista principal dara preferencia a las tareas vencidas o con fecha limite en los proximos 7 dias.

Motivo:
La agenda debe ayudar a elegir que tarea hacer cuando hay tiempo disponible, destacando primero lo urgente y despues lo importante.

Alternativas consideradas:
- Ordenar solo por prioridad.
- Ordenar solo por fecha limite.
- Obligar a que todas las tareas tengan fecha limite.

Consecuencias:
- Las prioridades iniciales seran alta, media y baja.
- Los estados iniciales seran activa y completada.
- La fecha limite sera opcional.
- Las tareas activas apareceran en la lista principal.
- Las tareas completadas no apareceran en la lista principal.
- Primero apareceran las tareas vencidas o que vencen en 7 dias o menos.
- Dentro del bloque urgente, se ordenara por fecha limite mas cercana y despues por prioridad.
- El resto de tareas se ordenara por prioridad, despues por fecha limite y finalmente por fecha de creacion.

## 2026-05-05 - Palabras clave separadas por tipo de accion

Decision:
Separar las autorizaciones del proyecto en tres palabras clave: `PROGRAMALO`, `DOCUMENTALO` y `SUBELO A GITHUB`.

Motivo:
Usar `PROGRAMALO` para cualquier cambio no era practico. Separar codigo, documentacion y subida a GitHub da mas control y evita ambiguedades.

Alternativas consideradas:
- Mantener solo `PROGRAMALO` para todo.
- Usar comandos informales sin documentarlos.

Consecuencias:
- `PROGRAMALO` queda reservado para cambios en codigo o estructura tecnica.
- `DOCUMENTALO` autoriza modificar documentacion del proyecto.
- `SUBELO A GITHUB` autoriza crear commits y hacer push al repositorio remoto.
- Sin una palabra clave aplicable, Codex solo puede analizar, explicar, planear, revisar o proponer.

## 2026-05-05 - Modelo inicial de eventos

Decision:
Los eventos representaran bloques de tiempo en el calendario, con titulo, fecha, hora de inicio, hora de fin, opcion de todo el dia, repeticion simple, recordatorio, color o categoria, y `tareaId` opcional.

Motivo:
La agenda necesita representar compromisos fijos, rutinas y bloques dedicados a tareas, manteniendo un modelo simple para la primera version.

Alternativas consideradas:
- No incluir repeticion en la primera version.
- Incluir repeticion avanzada desde el principio.
- Bloquear eventos solapados.

Consecuencias:
- Los eventos no tendran descripcion en la primera version.
- Un evento podra ser normal o estar vinculado a una tarea.
- Borrar un evento vinculado no borrara la tarea asociada.
- Completar una tarea no borrara automaticamente sus eventos pasados.
- La repeticion inicial permitira eventos diarios, semanales o en dias concretos de la semana.
- La app permitira eventos solapados, pero avisara al usuario cuando detecte conflicto.
- Las opciones iniciales de recordatorio seran sin recordatorio, a la hora del evento, 5 minutos antes, 15 minutos antes, 30 minutos antes, 1 hora antes y 1 dia antes.
- El recordatorio por defecto sera 1 hora antes.

## 2026-05-05 - Categorias compartidas por eventos y tareas

Decision:
Usar categorias con nombre y color para organizar eventos y tareas.

Motivo:
Las categorias mejoran la legibilidad del calendario, ayudan a distinguir tipos de actividad y permiten futuros filtros por area.

Alternativas consideradas:
- Usar solo color manual por evento.
- Usar categorias solo para eventos.
- Usar categorias compartidas por eventos y tareas.

Consecuencias:
- Cada categoria tendra `id`, `nombre` y `color`.
- Eventos y tareas podran tener categoria opcional.
- Existira una categoria por defecto llamada `General`.
- Si una tarea tiene categoria y se crea un evento desde ella, el evento heredara esa categoria.
- Las categorias iniciales seran `General`, `Trabajo`, `Estudio`, `Salud`, `Personal` y `Ocio`.
- Mas adelante se podran usar categorias para filtrar vistas.

## 2026-05-05 - Navegacion principal, pantalla Hoy y widget

Decision:
La app usara una barra inferior con cinco secciones principales: Hoy, Semana, Mes, Tareas y Ajustes. La pantalla Hoy sera la vista principal al abrir la app, y el widget mostrara un resumen informativo de Hoy.

Motivo:
El objetivo central de la app es organizar el dia desde el movil. Separar el tiempo planificado de la lista de tareas mantiene la experiencia clara.

Alternativas consideradas:
- Usar menu lateral.
- Mostrar tareas pendientes directamente en Hoy.
- Crear un widget interactivo desde la primera version.

Consecuencias:
- Hoy mostrara la fecha actual, linea temporal del dia, eventos normales y bloques de tareas programadas para hoy.
- Hoy no mostrara la lista general de tareas pendientes.
- Las tareas activas viviran en la pestana Tareas.
- Desde Tareas se podra seleccionar una tarea y asignarle un bloque de tiempo.
- El widget mostrara resumen de Hoy, incluyendo proximos eventos y bloques programados.
- El widget no mostrara la lista general de tareas pendientes.
- El widget tendra interaccion minima en la primera version: al tocarlo abrira la app en Hoy.

## 2026-05-06 - Flujos principales de tareas

Decision:
Las tareas solo tendran dos estados: activa y completada. La pestana Tareas tendra secciones internas para tareas activas y completadas.

Motivo:
La distincion entre pendiente y en progreso no aporta suficiente valor en la primera version. Una tarea puede seguir activa aunque ya tenga bloques de tiempo asignados.

Alternativas consideradas:
- Usar pendiente, en progreso y completada.
- Usar solo activa y completada.

Consecuencias:
- Toda tarea nueva nace como activa.
- Programar una tarea no cambia su estado.
- Una tarea sigue activa hasta que el usuario la marca como completada.
- Al completar una tarea, se guardara la fecha de completado.
- Las tareas completadas se ocultaran de la lista principal, pero podran verse en la seccion Completadas.
- Desde Completadas se podra reanudar una tarea, cambiandola de completada a activa.
- Los eventos pasados asociados a una tarea completada se conservaran.
- Si una tarea completada tiene eventos futuros asociados, la app preguntara si conservarlos o eliminarlos.

## 2026-05-06 - Edicion y borrado de eventos y tareas

Decision:
La app permitira editar y borrar eventos y tareas con confirmaciones cuando la accion pueda afectar a elementos relacionados.

Motivo:
Eventos y tareas pueden estar vinculados. Las acciones destructivas deben ser explicitas para evitar perdida accidental de informacion.

Alternativas consideradas:
- Borrar automaticamente todos los elementos relacionados.
- Conservar siempre los elementos relacionados sin preguntar.
- Preguntar cuando haya elementos relacionados o repetidos.

Consecuencias:
- Un evento podra editar titulo, fecha, hora o duracion, categoria, repeticion y recordatorio.
- Si un evento esta vinculado a una tarea, al editarlo mantendra el vinculo.
- Si un evento es repetido, al editar o borrar se preguntara si aplicar el cambio solo a ese evento o a toda la serie.
- Borrar un evento vinculado a una tarea no borrara la tarea.
- Una tarea podra editar titulo, prioridad, fecha limite y categoria.
- Si cambia la categoria de una tarea, los eventos futuros asociados actualizaran su categoria automaticamente.
- Los eventos pasados asociados no cambiaran al editar la categoria de la tarea.
- Si se borra una tarea sin eventos asociados, se borrara directamente.
- Si se borra una tarea con eventos asociados, la app preguntara si conservarlos como eventos normales o eliminarlos.

## 2026-05-06 - Modelo tecnico de datos local

Decision:
Usar Room como base de datos local con tres entidades principales: `TaskEntity`, `EventEntity` y `CategoryEntity`.

Motivo:
La app sera independiente, local y centrada en Android. Room encaja bien con Kotlin, persistencia local y una estructura clara de entidades.

Alternativas consideradas:
- Guardar datos en preferencias simples.
- Usar una base de datos local con entidades Room.
- Crear una entidad separada para reglas de repeticion desde la primera version.

Consecuencias:
- `TaskEntity` tendra `id`, `title`, `priority`, `status`, `deadlineDate`, `categoryId`, `completedAt`, `createdAt` y `updatedAt`.
- `EventEntity` tendra `id`, `title`, `date`, `startTime`, `endTime`, `isAllDay`, `categoryId`, `taskId`, `reminder`, `recurrenceType`, `recurrenceDays`, `recurrenceEndDate`, `createdAt` y `updatedAt`.
- `CategoryEntity` tendra `id`, `name`, `color`, `createdAt` y `updatedAt`.
- La repeticion simple se guardara con campos dentro de `EventEntity`, sin entidad separada en la primera version.
- `recurrenceEndDate` sera opcional; si no existe, la repeticion continuara hasta que el usuario edite o borre el evento.
- Los identificadores seran `Long` autogenerados por Room.
- Se usaran enums para `TaskPriority`, `TaskStatus`, `ReminderOption` y `RecurrenceType`.
- Se usara `LocalDate` para fechas, `LocalTime` para horas y `LocalDateTime` para marcas temporales.
- Room necesitara `TypeConverters` para guardar esos tipos de fecha/hora y enums.

## 2026-05-06 - Arquitectura interna e inyeccion de dependencias

Decision:
Usar una arquitectura simple de un solo modulo Android `app`, organizada por paquetes internos, y usar Hilt para inyeccion de dependencias.

Motivo:
La app necesita una estructura clara sin introducir la complejidad de un proyecto multi-modulo en la primera version. Hilt permite conectar ViewModels, repositorios, DAOs, base de datos y servicios de forma ordenada.

Alternativas consideradas:
- Crear un proyecto multi-modulo desde el principio.
- Usar paquetes internos dentro de un unico modulo `app`.
- Gestionar dependencias manualmente.
- Usar Hilt para inyeccion de dependencias.

Consecuencias:
- El proyecto tendra un unico modulo Android `app` en la primera version.
- La organizacion interna seguira paquetes principales: `data`, `domain`, `ui`, `notifications` y `widget`.
- `data` contendra persistencia local, DAOs, entidades Room y repositorios.
- `domain` contendra modelos de dominio y reglas de negocio, como ordenar tareas, detectar solapamientos o programar tareas.
- `ui` contendra pantallas Compose, ViewModels, navegacion y componentes reutilizables.
- `notifications` contendra la logica de recordatorios.
- `widget` contendra la logica del widget de Hoy.
- Hilt se configurara desde el inicio para inyectar dependencias como repositorios, DAOs, base de datos y servicios.

## 2026-05-06 - Librerias base y nombre de paquete Android

Decision:
Usar un stack Android moderno basado en Jetpack Compose, Room, Hilt, Coroutines, Flow, AlarmManager y Glance. El nombre de paquete Android sera `com.lizartza.agenda`.

Motivo:
Estas librerias cubren las necesidades principales de la app: interfaz moderna, navegacion, persistencia local, inyeccion de dependencias, datos reactivos, recordatorios exactos y widget de Hoy.

Alternativas consideradas:
- Usar WorkManager para recordatorios.
- Usar AlarmManager para recordatorios exactos.
- Usar RemoteViews para el widget.
- Usar Glance para el widget.

Consecuencias:
- La UI principal usara Jetpack Compose y Material 3.
- La navegacion entre pantallas usara Navigation Compose.
- La persistencia local usara Room.
- La app usara Kotlin Coroutines y Flow para operaciones asincronas y datos reactivos.
- La inyeccion de dependencias usara Hilt.
- Los recordatorios usaran AlarmManager para permitir avisos exactos.
- El widget de Hoy usara Glance en la primera version.
- Si Glance limita demasiado el widget, se evaluara RemoteViews como alternativa.
- El identificador tecnico de la app sera `com.lizartza.agenda`.

## 2026-05-06 - Division del trabajo en chats por seccion

Decision:
Dividir el desarrollo en ocho chats/secciones de trabajo y documentar sus responsabilidades en `SECCIONES.md`.

Motivo:
Separar el trabajo por areas evita mezclar contextos, reduce cambios fuera de alcance y permite que cada chat se centre en una responsabilidad concreta.

Alternativas consideradas:
- Continuar todo el desarrollo en un unico chat.
- Crear chats por area sin reglas de frontera.
- Crear chats por seccion con responsabilidades documentadas.

Consecuencias:
- Las secciones iniciales seran Base Android, Datos Locales Room, Tareas, Calendario/Eventos, Programar Tareas, Notificaciones, Widget Hoy y Ajustes/Categorias.
- Cada chat debe respetar su seccion asignada.
- Si un chat necesita modificar otra seccion, no debe hacerlo directamente.
- El chat debe explicar la dependencia y proponer un prompt para el chat responsable.
- El usuario decidira si autoriza o traslada el trabajo al chat correspondiente.

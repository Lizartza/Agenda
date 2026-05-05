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
Eventos y tareas seran conceptos separados. Un evento representa un bloque de tiempo en el calendario. Una tarea representa algo pendiente o en progreso que puede recibir uno o varios bloques de tiempo.

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
- Una tarea solo deja de aparecer como pendiente cuando el usuario la marca como completada.
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
- Los estados iniciales seran pendiente, en progreso y completada.
- La fecha limite sera opcional.
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

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

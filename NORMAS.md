# Normas del proyecto Agenda

## Palabras clave de autorizacion

Codex solo puede realizar ciertas acciones cuando el usuario escriba explicitamente la palabra clave correspondiente.

```text
PROGRAMALO
```

Autoriza cambios en codigo o estructura tecnica del proyecto.

```text
DOCUMENTALO
```

Autoriza cambios en archivos de documentacion del proyecto, como `NORMAS.md`, `DECISIONES.md` y `LOGS.md`.

```text
SUBELO A GITHUB
```

Autoriza crear commits y subirlos al repositorio remoto.

Sin una palabra clave aplicable, Codex puede analizar, explicar, planear, revisar o proponer, pero no modificar archivos ni subir cambios.

## Estilo de colaboracion

- Ir al grano por defecto.
- Trabajar en fases pequenas.
- Recapitular tras avances significativos.
- Explicar las decisiones tecnicas importantes.
- Avisar antes de cambios con impacto amplio.
- No asumir decisiones de producto importantes sin discutirlas.

## Control de versiones

- Usar Git y GitHub como control de versiones.
- Hacer commits pequenos y descriptivos.
- Revisar `git status` antes de commits importantes.
- No subir secretos, claves, tokens ni archivos `.env`.

## Documentacion del proyecto

Archivos principales:

- `NORMAS.md`: reglas estables de trabajo, seguridad, colaboracion y control de versiones.
- `DECISIONES.md`: decisiones tecnicas o de producto importantes y sus motivos.
- `LOGS.md`: resumen cronologico de avances relevantes.
- `SECCIONES.md`: secciones de trabajo, responsabilidades y fronteras entre chats.

Normas de uso:

- Cuando haya una decision tecnica o de producto importante, debe registrarse en `DECISIONES.md`.
- Cuando se termine una fase relevante de trabajo, debe registrarse una entrada breve en `LOGS.md`.
- No es obligatorio crear documentacion adicional hasta que sea util para el proyecto.
- Para modificar documentacion hace falta que el usuario escriba `DOCUMENTALO`.

## Trabajo por secciones

- El proyecto se divide en secciones documentadas en `SECCIONES.md`.
- Cada chat debe tener una seccion principal asignada.
- Cada chat debe trabajar solo dentro de su seccion asignada.
- Si un chat necesita cambios en otra seccion, no debe hacerlos directamente.
- En ese caso debe explicar la dependencia, pedir permiso al usuario y proponer un prompt para enviar al chat responsable.
- El usuario decidira si abre o usa el chat correspondiente para ese cambio.

## Seguridad y cambios

- No revertir cambios sin permiso explicito.
- No borrar archivos importantes sin confirmacion clara.
- No instalar dependencias sin explicar antes por que son necesarias.
- No cambiar el stack tecnologico sin discutirlo.

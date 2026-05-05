# Normas del proyecto Agenda

## Regla principal

Codex solo puede modificar archivos cuando el usuario escriba explicitamente:

```text
PROGRAMALO
```

Sin esa palabra, Codex puede analizar, explicar, planear, revisar o proponer, pero no editar archivos.

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

Normas de uso:

- Cuando haya una decision tecnica o de producto importante, debe registrarse en `DECISIONES.md`.
- Cuando se termine una fase relevante de trabajo, debe registrarse una entrada breve en `LOGS.md`.
- No es obligatorio crear documentacion adicional hasta que sea util para el proyecto.

## Seguridad y cambios

- No revertir cambios sin permiso explicito.
- No borrar archivos importantes sin confirmacion clara.
- No instalar dependencias sin explicar antes por que son necesarias.
- No cambiar el stack tecnologico sin discutirlo.

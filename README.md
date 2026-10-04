# Desarrollo de aplicaciones con especificaciones

Skill en español para Codex y Claude Code que guía el desarrollo de aplicaciones mediante especificaciones vivas y preguntas de producto.

La IA pregunta por el propósito, los usuarios, las reglas, los límites y el resultado esperado. Guarda las respuestas en los documentos del proyecto y las utiliza para planificar, implementar y verificar el trabajo.

## Qué aporta

- Entrevista breve en lenguaje sencillo, sin exigir conocimientos técnicos.
- Flujo de constitución, especificación, aclaraciones, plan, tareas, implementación y verificación.
- Uso de Spec Kit cuando está disponible, con adaptación a las capacidades locales.
- Adopción en aplicaciones existentes sin exigir reconstruirlas.
- Consolidación de especificaciones duplicadas y detección de contradicciones.
- Actualización de los documentos afectados por cambios de comportamiento.
- Verificación de los criterios de aceptación, declarando lo que queda pendiente.

## Descargar

En la página del repositorio, selecciona **Code → Download ZIP** y descomprime el archivo.

También puedes descargar `spec-driven-development.zip` de la lista de archivos: abre el archivo y usa la opción de descarga del archivo sin procesar. Si el repositorio tiene una versión publicada, el mismo ZIP puede estar disponible en **Releases**.

## Instalar

Copia la carpeta `spec-driven-development` completa, con su archivo `SKILL.md` y sus subcarpetas. No copies todo el repositorio dentro de la carpeta de skills.

### Codex

Para usarla personalmente en tus proyectos, copia la carpeta en:

```text
~/.agents/skills/spec-driven-development/
```

En Windows, `~` representa tu carpeta de usuario, por ejemplo `C:\Users\TuUsuario`.

Para compartirla con un equipo dentro de un proyecto, colócala en:

```text
<raíz-del-proyecto>/.agents/skills/spec-driven-development/
```

Abre una nueva sesión de Codex e invócala con:

```text
$spec-driven-development
```

### Claude Code

Para usarla personalmente en tus proyectos:

```text
~/.claude/skills/spec-driven-development/
```

Para compartirla dentro de un proyecto:

```text
<raíz-del-proyecto>/.claude/skills/spec-driven-development/
```

Abre una nueva sesión de Claude Code e invócala con:

```text
/spec-driven-development
```

## Primer uso

Describe la aplicación que quieres crear. Por ejemplo:

> Quiero una aplicación para gestionar solicitudes de mis clientes. Guíame con preguntas para definir la primera versión y utiliza spec-driven development para desarrollarla.

Para un proyecto existente:

> Quiero aplicar esta metodología a mi aplicación existente. Revisa primero sus especificaciones, detecta duplicados o contradicciones y conserva las reglas acordadas del producto.

Si faltan datos importantes, la IA te hará preguntas breves. Si ya están definidos en el proyecto, debe recuperarlos y evitar repetir la entrevista.

## Usarla como método habitual

El archivo [instrucciones-permanentes-sdd.md](instrucciones-permanentes-sdd.md) contiene una preferencia opcional para usar este flujo habitualmente.

Puedes pedirle a tu agente que añada ese texto a tus instrucciones personales, conservando las existentes. Codex utiliza `~/.codex/AGENTS.md`; Claude Code utiliza `~/.claude/CLAUDE.md`. Para una preferencia compartida por el equipo, utiliza las instrucciones del proyecto correspondientes.

La skill permite selección automática según la solicitud; invocarla explícitamente ayuda a confirmar que se cargó. Las instrucciones son orientación para el agente y el resultado sigue necesitando verificación.

## Requisitos y alcance

Necesitas un agente compatible con skills y acceso al proyecto donde vas a trabajar. La skill no instala herramientas automáticamente al copiarla.

Para la integración con Spec Kit, prepara Python, un gestor como `uv` y Specify CLI según la documentación oficial. Cada aplicación necesita su propia inicialización de Spec Kit. Si ya está inicializada, se reutiliza su estructura.

Este repositorio contiene una skill de la comunidad. No es una distribución oficial de GitHub Spec Kit, OpenAI ni Anthropic. No incluye el texto completo del curso: convierte sus conceptos en instrucciones prácticas originales. Ayuda a reducir desajustes entre documentación y código; no garantiza eliminar toda deuda técnica ni sustituye las pruebas de software.

## Referencias

- [GitHub Spec Kit](https://github.com/github/spec-kit)
- [Spec Kit en proyectos existentes](https://github.github.io/spec-kit/guides/existing-projects.html)
- [Skills de Codex](https://developers.openai.com/codex/skills)
- [Skills de Claude Code](https://code.claude.com/docs/en/skills)

## Compartir mejoras

Puedes proponer mejoras mediante una issue o pull request en este repositorio. Describe el caso de uso, el resultado obtenido y el cambio propuesto. Evita incluir credenciales o información privada de tus proyectos.

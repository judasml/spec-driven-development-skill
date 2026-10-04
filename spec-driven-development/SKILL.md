---
name: spec-driven-development
description: Crear, ampliar o reparar aplicaciones con especificaciones vivas antes de implementar. Entrevistar al usuario sobre producto, aclarar reglas, ordenar specs existentes y mantener constitución, requisitos, plan, tareas, código y verificación coherentes. Usar para trabajo de software; no para consultas generales ni creación de documentos ajenos al desarrollo.
---

# Spec-driven development

Aplicar el desarrollo guiado por especificaciones al trabajo solicitado. El usuario define el producto mediante respuestas en lenguaje sencillo; el agente convierte esas respuestas en documentos, implementación y evidencia verificable. Mantener el proceso proporcional al cambio.

## Inicio y contexto

1. Leer las instrucciones del proyecto y revisar el estado de Git, estructura, documentación, pruebas y herramientas disponibles antes de editar.
2. Clasificar el trabajo: aplicación nueva, funcionalidad nueva, cambio de comportamiento, reparación o adopción/limpieza documental.
3. Localizar constitución y especificaciones oficiales. Si existen, reutilizarlas; no crear una segunda documentación equivalente.
4. Recuperar las decisiones de los archivos y de la conversación antes de preguntar. Identificar la funcionalidad activa sin cambiar silenciosamente el contexto de otra funcionalidad.

## Entrevista de producto

Consultar [references/entrevista.md](references/entrevista.md) cuando falten decisiones de producto. El agente conduce las preguntas; no pedir al usuario que escriba una especificación ni que conozca comandos, arquitectura o lenguajes.

- Preguntar solo lo que falta y afecta al trabajo. Hacer rondas cortas de una a tres preguntas, con recomendaciones y opciones sencillas cuando ayuden.
- Cubrir propósito, destinatarios, flujo principal, reglas de negocio, límites de presupuesto/herramientas, exclusiones y resultado esperado.
- Guardar cada respuesta en el documento correspondiente; distinguir decisiones explícitas, evidencia del repositorio, propuestas y supuestos.
- Las decisiones de negocio ambiguas o contradictorias que cambien el resultado deben resolverse antes de implementar la parte afectada. Mientras se espera, avanzar en inspección y documentación independientes.
- Resolver decisiones técnicas rutinarias con criterio y las convenciones existentes. No exigir una aprobación por cada documento o etapa cuando el usuario ya autorizó desarrollar el trabajo.
- La falta de respuesta no es una aprobación. Si el usuario delega una decisión, elegir una opción razonable y documentar su motivo.

## Integración con Spec Kit

Spec Kit aporta plantillas y flujos; esta skill dirige su aplicación y la entrevista. No duplicar ni sustituir sus skills nativas si ya están disponibles.

- Revisar `specify version`, `specify init --help` y los recursos locales del proyecto antes de asumir sintaxis o funcionalidades.
- En Windows, preferir scripts PowerShell. Elegir la integración del agente activo: `codex` o `claude`.
- Inicializar solamente el proyecto objetivo cuando sea necesario y esté dentro del trabajo autorizado. No reinstalar paquetes globales ni inicializar en la carpeta personal.
- Para una carpeta nueva: `specify init <nombre> --integration <agente> --script ps`.
- Para un repositorio existente, inspeccionar conflictos y disponer de un estado recuperable antes de `specify init --here --force --integration <agente> --script ps`. `--force` puede reemplazar archivos gestionados. No guardar, descartar ni incluir cambios ajenos de forma indiscriminada.
- La inicialización crea infraestructura; no reconstruye automáticamente los requisitos de una aplicación existente.
- Los pasos `speckit-*` se ejecutan como skills/comandos del agente, no como comandos de PowerShell. En Codex se usan formas como `$speckit-specify`; en Claude usar la forma expuesta por la instalación, sin asumir que un alias de un curso sigue vigente.
- Si Spec Kit o una operación no están disponibles, informar la limitación y conservar el flujo documental con archivos Markdown. No afirmar que se ejecutó una skill o una verificación que no se ejecutó.

Fuentes para dudas de integración/versiones: [guía oficial](https://github.github.io/spec-kit/quickstart.html), [integraciones](https://github.github.io/spec-kit/reference/integrations.html), [proyectos existentes](https://github.github.io/spec-kit/guides/existing-projects.html). Consultarlas solo cuando los recursos locales no resuelvan la duda.

## Constitución y especificación

Antes de implementar una aplicación nueva, documentar su constitución y el primer alcance acotado. En aplicaciones existentes, recuperar las reglas reales y conservar la compatibilidad relevante; no reconstruir todo el sistema como requisito previo a una corrección pequeña.

La constitución contiene propósito, principios, restricciones transversales y acuerdos de tecnología/estructura realmente decididos. Usar `.specify/memory/constitution.md` si corresponde a la instalación. No inventar tecnologías ni requisitos para completar una plantilla.

La especificación de cada funcionalidad contiene:

- Intención y usuarios beneficiados.
- Comportamiento y flujos principales.
- Reglas de negocio y restricciones.
- No objetivos de esta iteración.
- Requisitos identificables, por ejemplo `FR-001`, y prioridades cuando sean útiles.
- Criterios de aceptación observables en formato Dado/Cuando/Entonces.
- Casos de borde relevantes, errores esperados y límites concretos.
- Supuestos, aclaraciones pendientes y métricas de éxito acordadas; no inventar umbrales.

Mantener el qué y el porqué en `spec.md`; las decisiones de implementación van en el plan. Redactar requisitos con actor, condición/disparador cuando corresponda y resultado verificable. EARS ayuda a expresar condiciones; no equivale solamente a comenzar cada frase con “el sistema”.

Los ejemplos del curso no son reglas universales: no heredar canchas, horarios, contraseñas, stack, ramas o número de tareas. Verificar límites temporales y términos ambiguos: hora de cierre frente a último inicio de un bloque, zona horaria, estados activos y excepciones.

## Plan, tareas e implementación

1. Aclarar los vacíos relevantes de la especificación; usar la capacidad `clarify` disponible cuando ayude.
2. Preparar el plan técnico con comprobación de la constitución, impacto, dependencias y validación. Crear investigación, modelo de datos, contratos y quickstart solo si son necesarios o parte de las plantillas aplicables.
3. Derivar tareas pequeñas, ordenadas por dependencias y vinculadas a requisitos/historias. Conservar IDs, progreso y trabajo ya realizado al revisar el plan.
4. Analizar coherencia entre constitución, spec, plan y tareas antes de implementar. No ejecutar tareas cuyo comportamiento dependa de una contradicción sin resolver.
5. Implementar el alcance autorizado y mantener tareas/documentos actualizados. No agregar funciones excluidas ni sustituir el producto del usuario por otra idea.

Usar las capacidades nativas `constitution`, `specify`, `clarify`, `plan`, `tasks`, `analyze`, `implement` y `converge` cuando estén disponibles y correspondan. No prometer que una sola ejecución propaga o verifica todo; revisar los artefactos producidos y el resultado real.

## Cambios y reparación

Identificar el artefacto más alto realmente afectado:

- Si cambia un principio transversal acordado, revisar la constitución y los documentos afectados.
- Si cambia el comportamiento deseado, actualizar primero la spec, después los elementos del plan/tareas que correspondan, e implementar.
- Si cambia solo el diseño técnico dentro de los acuerdos vigentes, actualizar el plan y los contratos relevantes.
- Si el código incumple una spec vigente, corregir la implementación y verificar el contrato; no modificar la spec para justificar el defecto.
- En cambios de formato o internos sin alteración de comportamiento, mantener los documentos vigentes y registrar solo el impacto útil. No fabricar una especificación completa ni repetir la entrevista.

Una nueva instrucción explícita del usuario puede cambiar una decisión anterior. Señalar el impacto y actualizar los artefactos relacionados; preguntar solo si hay ambigüedad real, no pedirle que repita autorización ya dada.

## Specs existentes y duplicadas

Cuando la adopción o limpieza documental forme parte del encargo:

1. Inventariar specs, README, instrucciones, planes y tareas; indicar su papel y autoridad.
2. Distinguir implementado, pendiente y no verificado usando evidencia del código y de las pruebas. El código describe el estado actual; no demuestra por sí solo la intención correcta.
3. Consolidar duplicados equivalentes conservando requisitos únicos, IDs y referencias. No resolver contradicciones por fecha del archivo ni porque una opción esté implementada.
4. Mantener un índice sencillo de documentos oficiales si hay varias funcionalidades. Una fuente de verdad puede estar distribuida en varios documentos con responsabilidades claras.
5. Sustituir copias por enlaces cuando sea útil; conservar la trazabilidad del material reemplazado mediante Git o un registro de migración. No borrar historia necesaria ni documentación ajena al alcance.

Usar specs vivas para comportamiento vigente y separar propuestas futuras e historia. No sobrescribir artefactos que el proyecto haya declarado históricos sin acordar su política de mantenimiento.

## Verificación y cierre

- Vincular criterios de aceptación a evidencia: pruebas automatizadas, recorridos de interfaz, integración o comprobaciones manuales según el cambio.
- Usar pruebas significativas y los controles existentes. Los evals de aceptación complementan las pruebas unitarias, de integración y de extremo a extremo; no las reemplazan universalmente.
- Para reglas de concurrencia, comprobar una garantía atómica en almacenamiento/operación y su comportamiento; “consultar y luego guardar” por sí solo no evita carreras.
- Revisar casos de borde pertinentes y confirmar que documentación y código quedaron alineados. Usar `converge` si está disponible, evaluando su evidencia en lugar de aceptar una etiqueta como garantía.
- Si hay divergencias, registrarlas como trabajo pendiente y corregir las que estén dentro del alcance autorizado. Mantener visibles los bloqueos o pruebas imposibles; no marcar tareas completas sin evidencia.
- Guardar avances revisables con la estrategia Git del repositorio. No exigir una rama por comando ni hacer `git add .` indiscriminadamente.
- En el cierre informar qué cambió, qué criterios se comprobaron, qué sigue pendiente y dónde están los documentos oficiales. No afirmar que las specs eliminan toda deuda técnica ni garantizan ausencia de errores.

## Continuidad entre sesiones

Guardar decisiones y pendientes en el repositorio, no solo en el chat. Al retomar, leer constitución, spec activa, plan/tareas y evidencia antes de preguntar otra vez. Actualizar las instrucciones del proyecto para señalar documentos oficiales cuando esa configuración esté autorizada; esta skill no concede permisos para publicar, desplegar ni modificar proyectos ajenos.

# Entrevista de producto dirigida por el agente

El usuario quiere que la IA haga las preguntas correspondientes para completar su parte. Conversar en español sencillo salvo que prefiera otro idioma. Recuperar primero respuestas del repositorio y del chat. No mostrar este banco completo como un formulario obligatorio.

## Rondas de inicio para una aplicación nueva

Elegir una a tres preguntas según lo que aún falte.

### Propósito y usuarios

- ¿Qué problema quieres resolver y quién utilizará la aplicación?
- ¿Qué hace hoy esa persona para resolverlo y qué debería mejorar?
- ¿Cuál es la acción principal que debe poder completar en la primera versión?

### Alcance y reglas

- ¿Qué tres funciones son indispensables para la primera versión? Si el usuario ya describió funciones, resumirlas y preguntar solo por una prioridad faltante.
- ¿Qué reglas debe respetar siempre? Ofrecer ejemplos ajustados al negocio real.
- ¿Qué funciones prefieres dejar fuera por ahora?
- ¿Qué puede hacer cada tipo de usuario y qué información puede ver?

### Límites y herramientas

- ¿Debe funcionar en navegador, teléfono u otro entorno? No preguntar si ya está decidido.
- ¿Hay presupuesto máximo o herramientas que debamos evitar? Aclarar si “gratis” incluye alojamiento, servicios externos y operación.
- ¿Debe conectarse a alguna herramienta existente o usar datos que ya tienes?
- ¿Hay una fecha necesaria o una prioridad que limite el primer alcance?

### Validación

- ¿Qué recorrido debería completar una persona para que consideres útil la primera versión?
- Ante un caso de borde concreto detectado, ¿qué resultado esperas? Describir el caso con lenguaje del negocio.
- ¿Qué comportamiento actual debemos conservar? Especialmente en proyectos existentes.

No exigir que el usuario elija frameworks, bases de datos o patrones si no tiene una preferencia. Proponer y documentar una solución técnica razonable conforme a sus límites.

## Proyectos existentes

Inspeccionar primero. Preguntar por la funcionalidad que quiere cambiar, reglas que no deben perderse y contradicciones que el repositorio no resuelve. No repetir todas las preguntas de una aplicación nueva ni asumir que todo lo construido es correcto.

Ejemplo de contradicción: “El documento A permite una reserva activa y el documento B permite varias. ¿Cuál debe ser la regla vigente?” Incluir referencias concretas y consecuencias de cada opción.

## Cómo presentar preguntas

- Usar herramientas de preguntas disponibles y compatibles con el agente/modo, o preguntas breves en el chat cuando no existan.
- Ofrecer dos o tres alternativas con una recomendación cuando sean útiles, permitiendo respuesta propia. No seleccionar automáticamente una decisión de negocio pendiente.
- No preguntar sobre trabajo fuera del alcance ni convertir posibilidades futuras en requisitos.
- Si el usuario dice “no sé”, explicar una recomendación y el motivo sin jerga. Si delega elegir, registrar la decisión delegada.
- En cambios pequeños, preguntar solo por el punto ambiguo. Si está todo definido, continuar sin entrevista adicional.

## Persistencia de respuestas

Integrar cada respuesta en la constitución o la spec correspondiente y ajustar historias, requisitos y criterios afectados. Mantener referencias en plan y tareas. No guardar una copia de todas las respuestas en otro documento que se vuelva una fuente competidora.

Cuando aporte claridad, registrar en la sección de aclaraciones: pregunta, respuesta, requisito afectado y estado. Separar:

- **Decidido:** instrucción explícita o elección delegada del usuario.
- **Observado:** conducta del código o documentación existente, con evidencia.
- **Propuesto:** recomendación que todavía necesita una decisión.
- **Pendiente:** dato que impide implementar la parte afectada.

Cerrar una ronda resumiendo las decisiones y continuar el flujo autorizado. Solicitar revisión explícita de una spec cuando el usuario lo pida o queden decisiones de producto relevantes; no imponer confirmaciones repetidas para etapas ya autorizadas.

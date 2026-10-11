# Guía de review de código

Una revisión de código efectiva no es solo buscar errores; es mejorar la calidad del producto, reforzar la seguridad, mantener el código legible y ayudar al equipo a crecer.

## Objetivo

El objetivo del review de código es:

- detectar defectos lógicos o de seguridad
- asegurar que el cambio cumple con el alcance solicitado
- mantener el código consistente con el estilo del proyecto
- facilitar la mantenibilidad y escalabilidad
- compartir conocimiento entre el equipo

---

## Principios de una buena revisión

### 1. Sé respetuoso y constructivo

La revisión debe centrarse en el código, no en la persona.

Bien:
- "La validación aquí podría fallar si `null` llega desde la API. ¿Podríamos manejar este caso?"

Mal:
- "Esto está mal y está mal hecho"

### 2. Enfócate en lo importante

Prioriza:
- lógica y comportamiento
- seguridad
- errores de edge cases
- rendimiento
- claridad y mantenibilidad
- tests

### 3. Haz comentarios accionables

En lugar de decir "esto no parece bien", explica:
- qué problema detectas
- por qué importa
- qué solución propones o preguntas si necesitas aclaración

### 4. Usa contexto y no solo estilo

No conviertas la revisión en una discusión de formato si el problema real es funcionalidad o diseño.

---

## Qué revisar en un PR

### Lógica y comportamiento

- ¿Hace lo que se supone que debe hacer?
- ¿Se manejan correctamente los casos límite?
- ¿El cambio rompe comportamiento existente?
- ¿Hay efectos secundarios no previstos?

### Seguridad

- ¿Se valida la entrada del usuario?
- ¿Se manejan errores de forma segura?
- ¿Se evita exponer información sensible?
- ¿Se usan credenciales o tokens de forma correcta?

### Rendimiento

- ¿Hay bucles innecesarios?
- ¿Se están haciendo demasiadas llamadas a base de datos o red?
- ¿Hay repetición innecesaria de lógica o datos?

### Mantenibilidad

- ¿El nombre de variables y funciones es claro?
- ¿El código es fácil de seguir?
- ¿Se puede cambiar sin romper otras partes?
- ¿Falta documentación para una parte compleja?

### Tests

- ¿Se cubre el caso nuevo o corregido?
- ¿Hay pruebas para casos negativos?
- ¿Se evita depender solo de pruebas manuales?

---

## Checklist para un revisor

Antes de aprobar un PR, revisa:

- [ ] El cambio resuelve el problema descrito
- [ ] El alcance del PR es claro y no incluye tareas mezcladas
- [ ] El código es legible y consistente con el estilo del proyecto
- [ ] Se manejan errores de forma apropiada
- [ ] No hay secretos ni credenciales en el código
- [ ] Hay pruebas para el comportamiento nuevo o corregido
- [ ] La documentación se actualizó si fue necesario
- [ ] El PR no introduce regresiones evidentes
- [ ] El impacto es entendible para otros desarrolladores

---

## Buenas prácticas para revisar

### Revisa con intención clara

Antes de comentar, identifica:

- ¿hay un bug real?
- ¿hay una mejora de diseño?
- ¿hay una duda de negocio?
- ¿hay una cuestión de rendimiento o seguridad?

### Haz comentarios pequeños y precisos

Comentarios grandes y no específicos suelen ser menos útiles.

### Sé específico sobre el problema

En lugar de:
- "Esto es difícil de entender"

Usa:
- "La función `calculateTotal` hace dos operaciones distintas y no queda claro cuál es la prioridad. ¿Podríamos extraerla a un helper para mejorar legibilidad?"

### Haz preguntas cuando algo no esté claro

Esto ayuda a obtener contexto sin imponer una solución incorrecta.

Ejemplo:
- "¿Este caso debería considerarse un error de validación o un flujo de recuperación?"

---

## Qué hacer cuando algo necesita cambio

### Si hay un bug real

Explica bien el problema y, si es posible, propone una alternativa.

Ejemplo:
- "Aquí se está utilizando `user.id` sin validar si el usuario existe. Si `undefined`, el flujo rompe la petición. Podríamos comprobarlo antes de continuar."

### Si hay un punto de diseño

Explica el objetivo y el riesgo.

Ejemplo:
- "La lógica actual duplica la validación en dos capas. Moverla a un servicio centralizado haría la regla más consistente y menos propensa a drift."

### Si te falta contexto

Haz una pregunta antes de rechazar.

Ejemplo:
- "¿Era intención que esto se ejecute en cada request o solo en el arranque del servicio?"

---

## Qué evitar en la revisión

Evita:

- revisar solo el aspecto visual y no la lógica
- hacer comentarios personales o agresivos
- bloquear PRs por estilo si no es crítico
- pedir cambios sin explicar el motivo
- aprobar sin leer con atención
- mezclar opiniones no verificadas con hechos

---

## Estilos de comentario

### Comentario útil

"El código actual hace una llamada a la API en cada render. Dado que esta vista se renderiza varias veces, podría generar solicitudes innecesarias. ¿Podríamos memoizar esta llamada o moverla fuera del render?"

### Comentario poco útil

"Esto está mal. Mejor hacerlo diferente."

---

## Plantilla de comentarios para revisión

### Cuando detectas un bug

```md
**Problema:** La validación de `email` no contempla el caso de cadena vacía.

**Impacto:** Esto podría permitir un flujo inválido y causar un error en la siguiente capa.

**Sugerencia:** Añadir una comprobación antes de continuar, o reutilizar la validación existente en un único punto.
```

### Cuando detectas un problema de diseño

```md
**Observación:** Esta lógica se está duplicando en dos funciones.

**Riesgo:** Si cambia una regla, hay dos puntos que pueden desalinearse.

**Pregunta:** ¿Podemos centralizar esta validación en una función o servicio compartido?
```

### Cuando es una mejora de claridad

```md
**Observación:** El nombre de esta variable no refleja bien el propósito del dato.

**Sugerencia:** Renombrarla a `filteredUsersByStatus` para mejorar legibilidad y evitar confusión.
```

---

## Revisión por niveles

### 1. Revisión rápida

Busca:
- errores obvios
- tests faltantes
- bugs de seguridad
- problemas de compilación

### 2. Revisión funcional

Verifica:
- si la solución cumple el objetivo
- si el flujo hace sentido
- si se cubren casos límite

### 3. Revisión profunda

Considera:
- impacto arquitectónico
- complejidad
- mantenibilidad
- rendimiento
- calidad del diseño

---

## Cuando aprobar o pedir cambios

### Aprobar

Cuando:
- el problema está bien resuelto
- los tests son adecuados
- no hay riesgo evidente
- el código es claro y razonable

### Pedir cambios

Cuando:
- hay un bug funcional o de seguridad
- la solución es frágil o difícil de mantener
- faltan pruebas importantes
- se introducen riesgos de regresión

---

## Checklist final antes de merge

- [ ] El PR tiene un propósito claro
- [ ] El código cumple con la intención del cambio
- [ ] Hay pruebas que cubren la lógica nueva o corregida
- [ ] Se revisaron casos límite y errores
- [ ] No existen problemas de seguridad evidentes
- [ ] El review fue constructivo y específico
- [ ] La solución es mantenible y clara
- [ ] Se resolvieron comentarios importantes

---

## Resumen

La revisión de código es una práctica de calidad, comunicación y aprendizaje. El objetivo no es “encontrar fallos” por el simple hecho de revisarlos, sino asegurar que el código sea correcto, seguro, claro y sostenible.

La mejor revisión combina:

- respeto
- precisión
- contexto
- criterio técnico
- comentarios accionables

Cuando esto ocurre, el equipo mejora a la vez que acelera la entrega de software mejor construido.

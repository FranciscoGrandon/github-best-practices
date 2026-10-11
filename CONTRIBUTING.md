# Contribuir a este proyecto

Gracias por tu interés en contribuir. Esta guía explica cómo hacerlo de forma ordenada y efectiva.

## Tabla de contenidos

- [Código de conducta](#código-de-conducta)
- [¿Cómo contribuir?](#cómo-contribuir)
- [Reporte de bugs](#reporte-de-bugs)
- [Sugerencias de mejora](#sugerencias-de-mejora)
- [Pull requests](#pull-requests)
- [Estilo de código](#estilo-de-código)
- [Proceso de revisión](#proceso-de-revisión)
- [Preguntas](#preguntas)

---

## Código de conducta

Esperamos que todos los contribuidores:

- sean respetuosos y constructivos
- eviten lenguaje ofensivo
- acepten crítica constructiva
- se enfoquen en lo que es mejor para el proyecto

---

## ¿Cómo contribuir?

Hay muchas formas de aportar:

- reportar bugs
- sugerir mejoras
- mejorar documentación
- corregir errores de tipografía
- añadir pruebas
- revisar pull requests
- compartir el proyecto

---

## Reporte de bugs

Si encuentras un bug, por favor crea un issue usando la plantilla de bug report.

### Antes de crear un issue

- revisa si el bug ya fue reportado
- verifica que sea reproducible
- intenta en una versión más reciente

### Información útil para reportar un bug

- descripción clara del problema
- pasos exactos para reproducir
- resultado esperado vs resultado actual
- entorno (OS, versión, etc.)
- capturas o logs si aplica

---

## Sugerencias de mejora

Las sugerencias de mejora son bienvenidas.

### Cómo sugerir una mejora

- describe el problema que resuelve
- explica la solución propuesta
- proporciona ejemplos si es posible
- considera alternativas

---

## Pull requests

### Preparación

1. haz fork del repositorio
2. crea una rama desde `main`:
   ```bash
   git checkout -b feature/tu-feature
   ```
3. trabaja en tu rama
4. asegúrate de que los tests pasen
5. haz commits claros y descriptivos

### Antes de hacer push

- verifica el estilo de código
- ejecuta tests locales
- actualiza documentación si es necesario
- revisa tu código antes de subir

### Crear el PR

1. sube tu rama
2. abre un pull request en GitHub
3. completa la plantilla de PR
4. describe qué problema resuelve
5. incluye referencias a issues relacionadas

### Después de abrir el PR

- responde a comentarios de revisión
- haz cambios si se solicita
- no reescribas historia de commits a menos que se pida
- sé paciente con la revisión

### Reglas para merge

- al menos una aprobación de revisor
- todos los tests deben pasar
- no hay conflictos con `main`
- documentación está actualizada

---

## Estilo de código

### Commits

- usa prefixes: `feat:`, `fix:`, `docs:`, `test:`, `refactor:`, `chore:`
- escribe en imperativo: "add feature" no "added feature"
- mantén commits pequeños y enfocados
- ejemplo:
  ```bash
  git commit -m "feat: add user authentication flow"
  ```

### Ramas

- usa nombres descriptivos
- ejemplos válidos:
  - `feature/dark-mode`
  - `fix/null-pointer-exception`
  - `docs/update-installation`
  - `test/add-login-tests`

### Código

- sigue las convenciones del proyecto
- revisa código existente
- comenta código complejo
- mantén consistencia visual
- evita código muerto

### Documentación

- actualiza README si cambias funcionalidad
- documenta código no obvio
- usa lenguaje claro y simple
- mantén formato consistente

---

## Proceso de revisión

### Qué se revisa

- funcionalidad correcta
- manejo de errores
- seguridad
- claridad del código
- cobertura de pruebas
- documentación

### Feedback constructivo

- sé específico
- proporciona contexto
- sugiere mejoras, no solo critiques
- aprecia el esfuerzo

### Tiempos de revisión

- las revisiones pueden tardar días
- ten paciencia
- si no hay respuesta en una semana, menciona gentilmente

---

## Preguntas

¿Tienes dudas?

- revisa la documentación
- abre una issue con etiqueta `question`
- contacta a los mantenedores

---

## Reconocimiento

Todos los contribuidores son apreciados y reconocidos en el proyecto.

---

## Licencia

Al contribuir, aceptas que tu código se publica bajo la licencia del proyecto.

---

Gracias por contribuir. ¡Tu ayuda hace este proyecto mejor!

# GitHub: mejores prácticas para proyectos propios y colaborativos

Una guía práctica para usar GitHub de forma ordenada, segura y eficaz tanto en proyectos personales como en equipos.

## 1. Objetivo

El objetivo de esta guía es ayudar a mantener repositorios limpios, colaborativos y fáciles de mantener. Esto incluye:

- organización del repositorio
- flujo de trabajo con ramas
- buenas prácticas de commits
- uso de pull requests
- revisión de código
- seguridad
- automatización
- colaboración en equipo

---

## 2. Organización del repositorio

Un repositorio bien estructurado facilita el trabajo y reduce errores.

### Recomendaciones básicas

- Usa un nombre claro y representativo para el proyecto.
- Mantén una estructura lógica de carpetas:
  - `src/` para código fuente
  - `docs/` para documentación
  - `tests/` para pruebas
  - `.github/` para workflows, templates y configuración
  - `scripts/` para utilidades o automatización
- Añade un README claro con:
  - descripción del proyecto
  - objetivo
  - requisitos
  - instalación
  - uso
  - contribución
  - roadmap o siguiente pasos
- Añade una licencia si el proyecto será compartido o reutilizado.
- Usa `.gitignore` para evitar archivos innecesarios.
- Añade un archivo `CONTRIBUTING.md` cuando el proyecto sea colaborativo.

### Estructura ejemplo

```text
my-project/
├── README.md
├── LICENSE
├── .gitignore
├── CONTRIBUTING.md
├── docs/
│   └── architecture.md
├── src/
│   └── app/
├── tests/
│   └── integration/
├── .github/
│   ├── workflows/
│   ├── ISSUE_TEMPLATE/
│   └── PULL_REQUEST_TEMPLATE.md
└── scripts/
    └── deploy.sh
```

---

## 3. Flujo de trabajo con GitHub

El flujo recomendado para la mayoría de proyectos es:

1. Crear una rama nueva desde la rama principal
2. Trabajar en esa rama
3. Hacer commits pequeños y claros
4. Abrir un Pull Request
5. Revisar y comentar el código
6. Fusionar cuando esté validado

### Rama principal

Lo normal es usar una rama principal estable:

- `main`
- `master`

En proyectos colaborativos, suele evitarse hacer commits directos a la rama principal.

### Convención de nombres de ramas

Usa nombres descriptivos y consistentes:

```bash
git checkout -b feature/login-flow
git checkout -b fix/resolve-payment-error
git checkout -b chore/update-dependencies
git checkout -b docs/update-readme
git checkout -b hotfix/security-patch
```

Convenciones comunes:

- `feature/` para nuevas funcionalidades
- `fix/` para correcciones de bugs
- `docs/` para cambios de documentación
- `chore/` para tareas de mantenimiento
- `refactor/` para reorganización del código
- `hotfix/` para correcciones urgentes

---

## 4. Buenas prácticas con commits

Los commits deben ser pequeños, claros y fáciles de revisar.

### Reglas recomendadas

- Un commit debe tener un propósito concreto.
- Evita commits gigantes que mezclen varias cosas.
- Usa mensajes descriptivos con estilo consistente.
- Revisa el diff antes de confirmar.

### Mensajes de commit útiles

```bash
git commit -m "feat: add user authentication flow"
git commit -m "fix: resolve null value in profile response"
git commit -m "docs: update getting started guide"
git commit -m "test: add API validation for invoice endpoint"
git commit -m "refactor: simplify project configuration loader"
```

### Prefixes comunes

- `feat:` nueva funcionalidad
- `fix:` corrección de error
- `docs:` documentación
- `test:` pruebas
- `refactor:` reorganización del código
- `chore:` mantenimiento o tareas rutinarias
- `perf:` mejora de rendimiento
- `ci:` cambios en CI/CD
- `build:` cambios en build o dependencias

### Consejo práctico

Si un commit requiere explicar más de un concepto, probablemente está mezclando varias tareas. Mejor dividirlo.

---

## 5. Pull Requests (PRs)

Los Pull Requests son una parte esencial del trabajo colaborativo en GitHub.

### Qué debe incluir un PR

- título claro y específico
- descripción del problema y solución
- alcance del cambio
- pruebas realizadas
- enlaces o referencias a issues relacionadas
- capturas si aplica

### Plantilla recomendada

```markdown
## Descripción
Describe brevemente el problema que resuelve este cambio.

## Cambios realizados
- Cambio 1
- Cambio 2
- Cambio 3

## Validación
- [ ] Ejecuté pruebas locales
- [ ] Revisé el linter
- [ ] Verifiqué el comportamiento esperado

## Referencias
- Fixes #123
```

### Buenas prácticas para PRs

- Crea un PR para cada tarea o cambio importante.
- Mantén el PR enfocado.
- Pide revisión a personas relevantes.
- Responde a comentarios con cambios concretos.
- No mezcles refactors, mejoras y correcciones en un mismo PR si se pueden separar.

---

## 6. Revisión de código

La revisión de código no es solo aprobar o rechazar. Es una oportunidad para mejorar la calidad del proyecto.

### Qué revisar

- lógica y corrección del algoritmo
- manejo de errores
- seguridad
- claridad del código
- consistencia con el estilo del proyecto
- impacto en otras partes del sistema
- cobertura de pruebas

### Comentarios útiles

- “¿Se está manejando este caso límite?”
- “¿Podríamos simplificar esta lógica?”
- “¿Hay otra forma más segura de validar esta entrada?”
- “¿Hace falta añadir una prueba para este comportamiento?”

### Reglas para una buena revisión

- Sé específico y constructivo.
- Explica el problema y la mejora sugerida.
- Evita comentarios genéricos como “esto está mal” sin contexto.
- Si algo no está claro, pide aclaración.

---

## 7. Seguridad en GitHub

La seguridad es crítica en cualquier proyecto.

### No subir secretos

Nunca subas al repositorio:

- tokens
- claves API
- credenciales de bases de datos
- contraseñas
- archivos `.env` con valores reales
- certificados o claves privadas

### Recomendaciones

- Usa variables de entorno para configuraciones locales.
- Usa GitHub Secrets para pipelines y despliegues.
- Revisa depende de seguridad o vulnerabilidades con herramientas como:
  - Dependabot
  - Renovate
  - Snyk
- Escanea dependencias antes de subir cambios importantes.

### `.gitignore`

Incluye archivos generados o locales como:

```gitignore
.env
.env.local
node_modules/
.dist/
coverage/
.DS_Store
```

---

## 8. Colaboración en equipo

Cuando varias personas trabajan en el mismo proyecto, la disciplina y la comunicación importan tanto como el código.

### Recomendaciones clave

- Mantén la rama principal actualizada.
- Haz `pull` o `fetch` antes de comenzar a trabajar.
- Evita tocar la misma zona de código sin coordinación.
- Usa issues para tareas y seguimiento.
- Documenta decisiones importantes.
- Establece responsables o reviewers en PRs.
- Usa labels para clasificar tareas.

### Labels útiles

- `bug`
- `enhancement`
- `documentation`
- `help wanted`
- `good first issue`
- `question`
- `security`

### Proyectos y milestones

- Usa GitHub Projects para planificar trabajo visualmente.
- Usa milestones para agrupar objetivos de una etapa o release.

---

## 9. Issues: cómo usarlos bien

Los issues sirven para documentar trabajo, bugs, dudas y mejoras.

### Buen uso de issues

- crear un issue por cada tarea o bug relevante
- describir el problema con contexto
- incluir pasos para reproducir un bug
- asignar prioridad si aplica
- enlazar con pull requests relacionados

### Plantilla recomendada para bug report

```markdown
## Descripción
Describe el problema.

## Pasos para reproducir
1. Paso 1
2. Paso 2
3. Paso 3

## Resultado esperado
Describe lo que debería ocurrir.

## Resultado actual
Describe lo que está ocurriendo.

## Entorno
- OS:
- Browser/Version:
- App Version:
```

---

## 10. GitHub Actions y automatización

GitHub Actions permite automatizar tareas repetitivas.

### Casos comunes

- ejecutar pruebas automáticamente
- lanzar linters
- validar compilación
- publicar documentación
- desplegar aplicaciones
- ejecutar scripts de calidad

### Recomendaciones

- Usa CI para validar cambios en cada pull request.
- No dependas solo de la revisión manual.
- Mantén los workflows pequeños y entendibles.
- Guarda secretos en GitHub Secrets.

### Ejemplo simple de workflow

```yaml
name: CI

on:
  push:
    branches: [main]
  pull_request:

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: 20
      - name: Install dependencies
        run: npm install
      - name: Run tests
        run: npm test
```

---

## 11. Mantenimiento de ramas y limpieza del repositorio

Para evitar caos, conviene mantener las ramas ordenadas.

### Recomendaciones

- elimina ramas fusionadas que ya no se usan
- evita dejar ramas antiguas o sin trabajo
- mantén `main` limpio y estable
- usa nombres claros y permanentes
- no guardes ramas temporales para siempre

---

## 12. Releases y versionado

Cuando una versión del proyecto es importante, publica una release.

### Buenas prácticas

- usar etiquetas semver: `v1.0.0`, `v1.2.3`
- documentar cambios principales
- indicar nuevas funcionalidades y arreglos
- incluir notas de despliegue si aplica

### Versionado semver

- `MAJOR`: cambios incompatibles
- `MINOR`: nuevas funcionalidades compatibles
- `PATCH`: correcciones de errores

Ejemplo:

- `1.0.0` primera versión estable
- `1.1.0` nueva funcionalidad
- `1.1.1` corrección menor

---

## 13. Trabajo en proyectos propios

Cuando trabajas solo, sigue igual de bien las prácticas, aunque no haya equipo.

### Recomendaciones

- usa ramas para cada tarea
- mantén tus commits explicativos
- documenta cómo arrancar el proyecto
- usa issues para registrar mejoras y bugs
- crea releases cuando publíques versiones relevantes
- usa un README profesional
- añade badges si tienen sentido

### Buenas señales de un proyecto bien mantenido

- README claro
- instrucciones de instalación sencillas
- commit history ordenada
- issues organizadas
- cambios con PRs aunque sea un proyecto individual

---

## 14. Trabajo en proyectos colaborativos

Cuando hay más personas involucradas, debes reforzar la comunicación y la estructura.

### Recomendaciones adicionales

- definir un flujo de trabajo y documentarlo
- establecer reglas claras de aprobación
- usar `CONTRIBUTING.md`
- separar tareas concretas
- revisar PRs con tiempo y atención
- evitar “merge sin contexto”
- mantener la rama principal estable

---

## 15. Operaciones más frecuentes en GitHub

Estas son las tareas más habituales durante el día a día.

### Crear un repositorio

1. Ir a GitHub
2. Pulsar “New repository”
3. Elegir nombre, visibilidad y descripción
4. Inicializar con README si aplica
5. Crear el repositorio

### Clonar un repositorio

```bash
git clone https://github.com/usuario/repositorio.git
```

### Crear una rama

```bash
git checkout -b feature/nueva-funcionalidad
```

### Ver el estado del repositorio

```bash
git status
```

### Añadir cambios al staging

```bash
git add .
```

### Hacer un commit

```bash
git commit -m "feat: add new flow"
```

### Subir cambios a GitHub

```bash
git push origin feature/nueva-funcionalidad
```

### Crear un PR

1. Subir la rama
2. Ir al repositorio en GitHub
3. Hacer clic en “Compare & pull request”
4. Completar la descripción
5. Asignar reviewers
6. Crear el PR

### Fusionar un PR

- revisar comentarios
- confirmar que pasa la validación
- hacer merge
- borrar rama si ya no es necesaria

### Actualizar tu rama con la principal

```bash
git fetch origin
git rebase origin/main
```

O bien:

```bash
git pull origin main
```

### Ver historial

```bash
git log --oneline --decorate --graph
```

---

## 16. Checklist recomendada antes de hacer merge

Antes de fusionar un PR, revisa esto:

- [ ] El cambio tiene un propósito claro
- [ ] Los commits son pequeños y entendibles
- [ ] La documentación fue actualizada si aplica
- [ ] Hay pruebas y pasan correctamente
- [ ] El código cumple con el estilo del proyecto
- [ ] No hay secretos ni archivos sensibles
- [ ] El PR tiene descripción clara
- [ ] Se resolvieron comentarios de revisión
- [ ] La rama está actualizada con la principal

---

## 17. Errores frecuentes en GitHub

Estos son algunos errores que suelen aparecer:

- hacer commits enormes y poco claros
- trabajar directamente en `main`
- no documentar cambios importantes
- subir archivos sensibles
- abrir PRs sin descripción
- no revisar código antes de fusionar
- mezclar varias tareas en un mismo PR
- no borrar ramas obsoletas
- no hacer pruebas antes de desplegar

---

## 18. Regla práctica resumida

Si quieres resumirlo en una sola idea:

- trabaja en ramas
- haz commits pequeños y claros
- abre PRs con propósito
- revisa con atención
- documenta lo necesario
- usa seguridad y automatización
- mantén el repositorio ordenado

---

## 19. Recomendación final

GitHub funciona mejor cuando se usa con disciplina, claridad y una buena comunicación. No se trata solo de “guardar código”, sino de construir un proyecto sostenible, revisable y fácil de mantener.

La combinación ideal es:

- estructura clara
- ramas bien usadas
- commits descritos
- PRs bien documentados
- revisiones objetivas
- seguridad y automatización
- documentación moderna

Con estas prácticas, cada proyecto personal o colaborativo será más robusto y más fácil de escalar.

---

## 20. Recursos útiles

- GitHub Docs: https://docs.github.com/
- Git Flow: https://nvie.com/posts/a-successful-git-branching-model/
- Convenciones de commit: https://www.conventionalcommits.org/
- GitHub Projects: https://github.com/features/issues

---

## 21. Conclusión

Usar GitHub bien no significa complicar el flujo; significa hacerlo claro, reproducible y seguro. Con estas prácticas, tanto un proyecto individual como un equipo pueden trabajar de manera más eficiente, reducir errores y mantener el código sano a largo plazo.

Este repositorio sirve como referencia rápida para aplicar buenas prácticas en el día a día.

# GitHub Best Practices

> Una guía completa y profesional para trabajar de forma ordenada, segura y eficiente en GitHub, tanto en proyectos personales como en equipo.

<div align="center">

![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Version](https://img.shields.io/badge/version-1.0.0-blue.svg?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-green.svg?style=flat-square)
![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg?style=flat-square)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)

**[🚀 Comenzar](#cómo-empezar) • [📖 Guía Completa](#índice-de-contenidos) • [⭐ Contribuir](#contribuir)**

</div>

---

## 📋 Tabla de contenidos

- [Objetivo](#objetivo)
- [Cómo empezar](#cómo-empezar)
- [Índice de contenidos](#índice-de-contenidos)
- [Características principales](#características-principales)
- [Estructura del repositorio](#estructura-del-repositorio)
- [Flujo de trabajo recomendado](#flujo-de-trabajo-recomendado)
- [Módulos de la guía](#módulos-de-la-guía)
- [Contribuir](#contribuir)
- [Licencia](#licencia)

---

## 🎯 Objetivo

Esta guía reúne **mejores prácticas profesionales** para trabajar en GitHub:

✅ Organización clara de repositorios  
✅ Flujo de trabajo efectivo con ramas  
✅ Commits y pull requests de calidad  
✅ Revisión de código constructiva  
✅ Colaboración segura y profesional  
✅ Mantenimiento y escalabilidad  

**Ideal para:**
- Desarrolladores en proyectos personales
- Equipos colaborativos
- Startups y empresas
- Mejora de procesos de desarrollo

---

## 🚀 Cómo empezar

### 1. Clona o descarga este repositorio

```bash
git clone https://github.com/FranciscoGrandon/github-best-practices.git
cd github-best-practices
```

### 2. Explora la guía principal

Comienza leyendo el [README completo](#) que cubre los conceptos fundamentales.

### 3. Consulta los módulos específicos

Cada área tiene su propia guía detallada:

| Módulo | Descripción | Acceso |
|--------|-------------|--------|
| **Branching Model** | Estrategia de ramas | [📄 Ver](docs/branching-model.md) |
| **Code Review** | Guía de revisión de código | [📄 Ver](docs/code-review-guide.md) |
| **Contribuir** | Pautas para contribuidores | [📄 Ver](CONTRIBUTING.md) |

### 4. Usa las plantillas

Copia las plantillas para tu proyecto:

```bash
# Plantilla de bug report
cp .github/ISSUE_TEMPLATE/bug_report.yml tu-proyecto/.github/ISSUE_TEMPLATE/

# Plantilla de feature request
cp .github/ISSUE_TEMPLATE/feature_request.yml tu-proyecto/.github/ISSUE_TEMPLATE/

# Plantilla de Pull Request
cp .github/PULL_REQUEST_TEMPLATE.md tu-proyecto/.github/
```

### 5. Personaliza según tu proyecto

Adapta las guías y plantillas a los requisitos específicos de tu equipo o proyecto.

---

## 📚 Índice de contenidos

### Conceptos Fundamentales

1. **[Organización del repositorio](#1-organización-del-repositorio)**
   - Estructura recomendada
   - Buenas prácticas iniciales

2. **[Flujo de trabajo](#2-flujo-de-trabajo-recomendado)**
   - Pasos del flujo estándar
   - Integración continua

3. **[Ramas y branching model](docs/branching-model.md)**
   - Tipos de ramas
   - Convenciones de nombres
   - Ejemplos prácticos

### Desarrollo Colaborativo

4. **[Commits](#4-commits)**
   - Mensaje claros
   - Prefixes y convenciones
   - Buenas prácticas

5. **[Pull Requests](#5-pull-requests)**
   - Estructura del PR
   - Plantillas
   - Ciclo de vida

6. **[Revisión de código](docs/code-review-guide.md)**
   - Qué revisar
   - Cómo comentar
   - Mejores prácticas

### Seguridad y Operaciones

7. **[Seguridad](#7-seguridad)**
   - Qué no subir a GitHub
   - Secretos y credenciales
   - Buenas prácticas

8. **[Issues y seguimiento](#8-issues-y-seguimiento)**
   - Tipos de issues
   - Plantillas disponibles
   - Organización

9. **[Automatización](#9-automatización-con-github-actions)**
   - GitHub Actions
   - Casos comunes
   - Configuración

10. **[Operaciones frecuentes](#10-operaciones-frecuentes-en-github)**
    - Comandos git
    - Flujo paso a paso
    - Checklists

---

## ✨ Características principales

### 📖 Guías completas y prácticas

Cada sección incluye:
- Explicación clara del concepto
- Ejemplos reales
- Checklists accionables
- Mejores prácticas

### 🎨 Plantillas listas para usar

- Bug report template
- Feature request template
- Pull request template
- Contributing guide

### 🔗 Referencias y enlaces

Toda la documentación está interconectada para fácil navegación.

### 🎯 Enfoque profesional

Escrito pensando en equipos, proyectos reales y escalabilidad.

---

## 📁 Estructura del repositorio

```
github-best-practices/
├── README.md                           # Este archivo
├── CONTRIBUTING.md                     # Guía de contribución
├── LICENSE                             # Licencia MIT
├── .gitignore                          # Archivo de exclusión
│
├── docs/
│   ├── branching-model.md              # Estrategia de ramas
│   ├── code-review-guide.md            # Guía de code review
│   └── operations-checklist.md         # Checklist de operaciones
│
└── .github/
    ├── ISSUE_TEMPLATE/
    │   ├── bug_report.yml              # Plantilla: bug
    │   └── feature_request.yml         # Plantilla: feature
    └── PULL_REQUEST_TEMPLATE.md        # Plantilla: PR
```

---

## 🔄 Flujo de trabajo recomendado

```
main (rama principal)
  │
  ├─→ feature/nueva-funcionalidad
  │   └─→ Pull Request
  │       └─→ Revisión
  │           └─→ Merge a main
  │
  ├─→ fix/corrección-bug
  │   └─→ Pull Request
  │       └─→ Merge a main
  │
  └─→ hotfix/urgencia-producción
      └─→ Merge directo a main
```

### Pasos del flujo

1. **Actualizar main**
   ```bash
   git checkout main
   git pull origin main
   ```

2. **Crear rama**
   ```bash
   git checkout -b feature/descripcion
   ```

3. **Trabajar y hacer commits**
   ```bash
   git add .
   git commit -m "feat: descripción clara"
   ```

4. **Subir cambios**
   ```bash
   git push origin feature/descripcion
   ```

5. **Abrir Pull Request**
   - Ir a GitHub
   - Crear PR con descripción clara
   - Solicitar revisión

6. **Revisar y mezclar**
   - Responder comentarios
   - Hacer cambios si es necesario
   - Merge a main

---

## 📦 Módulos de la guía

### 1️⃣ Organización del repositorio

Un repositorio bien estructurado facilita mantenimiento y colaboración.

**Incluye:**
- Estructura de carpetas
- Archivos esenciales (README, LICENSE, .gitignore)
- Documentación
- Configuración

[→ Más detalles](#1-organización-del-repositorio)

### 2️⃣ Branching Model

Estrategia clara para trabajar con ramas.

**Tipos de ramas:**
- `main` - rama principal
- `feature/*` - nuevas funcionalidades
- `fix/*` - correcciones
- `hotfix/*` - emergencias
- `docs/*` - documentación
- `chore/*` - mantenimiento

[→ Consulta la guía completa](docs/branching-model.md)

### 3️⃣ Commits de calidad

Mensajes claros, enfocados y descriptivos.

**Prefixes:**
- `feat:` nueva funcionalidad
- `fix:` corrección de error
- `docs:` documentación
- `test:` pruebas
- `refactor:` reestructuración

[→ Más detalles](#4-commits)

### 4️⃣ Pull Requests efectivos

Documentación clara, revisión constructiva, merge seguro.

**Elementos:**
- Descripción clara
- Cambios listados
- Validación y pruebas
- Referencias a issues

[→ Más detalles](#5-pull-requests)

### 5️⃣ Code Review profesional

Revisión constructiva, específica y enfocada en la calidad.

**Se revisa:**
- Lógica y comportamiento
- Seguridad
- Rendimiento
- Claridad del código

[→ Consulta la guía completa](docs/code-review-guide.md)

### 6️⃣ Seguridad

Protege tu proyecto: no subas secretos, usa variables de entorno.

**Importante:**
- Nunca subir tokens, passwords, claves
- Usar GitHub Secrets para CI/CD
- Revisar dependencias vulnerables

[→ Más detalles](#7-seguridad)

### 7️⃣ Issues y seguimiento

Documenta bugs, mejoras y tareas de forma clara.

**Plantillas:**
- Bug report
- Feature request
- Issue general

[→ Más detalles](#8-issues-y-seguimiento)

---

## 📊 Estadísticas de esta guía

| Métrica | Valor |
|---------|-------|
| Secciones | 10+ |
| Ejemplos prácticos | 50+ |
| Plantillas incluidas | 3 |
| Guías detalladas | 2 |
| Checklists | 5+ |

---

## 1. Organización del repositorio

### Estructura recomendada

```
my-project/
├── README.md
├── CONTRIBUTING.md
├── LICENSE
├── .gitignore
├── docs/
│   ├── branching-model.md
│   └── code-review-guide.md
├── src/
│   └── app/
├── tests/
├── .github/
│   ├── workflows/
│   ├── ISSUE_TEMPLATE/
│   └── PULL_REQUEST_TEMPLATE.md
└── scripts/
```

### Checklist inicial

- [ ] Nombre claro y descriptivo
- [ ] README con objetivos e instalación
- [ ] .gitignore actualizado
- [ ] LICENSE definida
- [ ] CONTRIBUTING.md si es colaborativo
- [ ] Carpetas organizadas lógicamente

---

## 2. Flujo de trabajo recomendado

El flujo estándar facilita la integración y reduce errores:

1. Actualizar rama principal
2. Crear rama nueva
3. Trabajar en la rama
4. Commits pequeños
5. Abrir Pull Request
6. Revisar y comentar
7. Fusionar a main
8. Eliminar rama si ya no se usa

---

## 4. Commits

### Buenas prácticas

```bash
# ✅ Bien: pequeño, específico, claro
git commit -m "feat: add user authentication flow"

# ❌ Mal: grande, vago, poco descriptivo
git commit -m "arreglé cosas"
```

### Prefixes comunes

- `feat:` nueva funcionalidad
- `fix:` corrección de error
- `docs:` documentación
- `test:` pruebas
- `refactor:` reestructuración
- `chore:` mantenimiento
- `perf:` rendimiento
- `ci:` configuración

---

## 5. Pull Requests

### Plantilla recomendada

```markdown
## Descripción
Explica el problema que resuelve este cambio.

## Cambios realizados
- Cambio 1
- Cambio 2

## Validación
- [ ] Tests pasados
- [ ] Linter revisado
- [ ] Comportamiento verificado

## Referencias
Fixes #123
```

Usa la plantilla oficial: [.github/PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md)

---

## 7. Seguridad

### ⚠️ Nunca subas

- Tokens o claves API
- Passwords
- Archivos `.env` reales
- Certificados privados

### ✅ Usa en su lugar

- Variables de entorno
- GitHub Secrets
- Gestores de secretos
- Herramientas de escaneo

---

## 8. Issues y seguimiento

### Plantillas disponibles

1. **Bug Report** - Reporta problemas
2. **Feature Request** - Propone mejoras
3. **General** - Otras tareas

Accede a ellas desde la pestaña "Issues" → "New issue"

---

## 9. Automatización con GitHub Actions

Automatiza validaciones y despliegues:

```yaml
name: CI

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run tests
        run: npm test
```

---

## 10. Operaciones frecuentes en GitHub

### Comandos esenciales

```bash
# Crear rama
git checkout -b feature/nueva

# Subir cambios
git push origin feature/nueva

# Actualizar desde main
git pull origin main

# Ver historial
git log --oneline --decorate --graph

# Fusionar localmente
git merge feature/nueva
```

---

## 🤝 Contribuir

¿Quieres mejorar esta guía?

1. **Fork** el repositorio
2. **Crea una rama** con tu mejora
3. **Abre un Pull Request** con descripción clara
4. **Espera revisión** y responde comentarios

### Pautas

- Sé claro y específico
- Respeta el tono profesional
- Revisa documentación existente antes de cambiar
- Incluye ejemplos si añades contenido

Para más detalles, consulta [CONTRIBUTING.md](CONTRIBUTING.md)

---

## 📖 Recursos relacionados

| Recurso | Descripción |
|---------|-------------|
| [CONTRIBUTING.md](CONTRIBUTING.md) | Guía de contribución |
| [docs/branching-model.md](docs/branching-model.md) | Estrategia de ramas |
| [docs/code-review-guide.md](docs/code-review-guide.md) | Guía de revisión de código |
| [.github/ISSUE_TEMPLATE/](github/ISSUE_TEMPLATE/) | Plantillas de issues |
| [.github/PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md) | Plantilla de PR |

---

## 💡 Recursos externos

- [GitHub Docs](https://docs.github.com/) - Documentación oficial
- [Conventional Commits](https://www.conventionalcommits.org/) - Estándar de mensajes
- [Git Flow](https://nvie.com/posts/a-successful-git-branching-model/) - Modelo de ramas
- [Pro Git Book](https://git-scm.com/book/es/v2) - Guía completa de Git

---

## ❓ FAQ

### ¿Puedo usar esto en mi proyecto?

**Sí.** La guía es de código abierto (MIT). Copia, personaliza y comparte libremente.

### ¿Funciona para equipos pequeños?

**Perfectamente.** Las prácticas son escalables: desde 1 persona hasta cientos de desarrolladores.

### ¿Es necesario seguir TODO al pie de la letra?

**No.** Adapta las recomendaciones a tu contexto. Lo importante es tener un proceso claro y consistente.

### ¿Puedo sugerir cambios?

**Claro.** Abre un issue o un PR con tu propuesta. Todas las mejoras son bienvenidas.

---

## 📊 Resumen ejecutivo

<table>
<tr>
<td width="50%">

### Para proyectos personales

✅ Mantén el código organizado  
✅ Documenta tus decisiones  
✅ Aprende buenas prácticas  
✅ Prepárate para trabajo en equipo  

</td>
<td width="50%">

### Para equipos

✅ Flujo de trabajo consistente  
✅ Colaboración profesional  
✅ Revisión de código efectiva  
✅ Menos conflictos y errores  

</td>
</tr>
</table>

---

## 📈 Estado de la guía

- ✅ Completa y operacional
- 📝 Actualizaciones periódicas
- 🔄 Feedback bienvenido
- 🚀 Listo para usar en producción

---

## 📝 Licencia

Este repositorio está bajo licencia **MIT**. Puedes usar, copiar, modificar y distribuir libremente.

[Ver licencia](LICENSE)

---

## 👤 Autor

**Francisco Grandón**  
📧 grandonpanxo@gmail.com  
🔗 [GitHub](https://github.com/FranciscoGrandon)

---

<div align="center">

### ⭐ Si esta guía te fue útil, considera dejar una estrella

**Contribuidores bienvenidos** · [Abre una issue](https://github.com/FranciscoGrandon/github-best-practices/issues) · [Envía un PR](https://github.com/FranciscoGrandon/github-best-practices/pulls)

---

Hecho con ❤️ para desarrolladores que quieren trabajar mejor en GitHub

</div>

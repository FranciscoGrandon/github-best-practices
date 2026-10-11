# Guía de branching model

Una estrategia simple y efectiva para trabajar con ramas en GitHub, tanto en proyectos personales como colaborativos.

## Objetivo

Mantener el repositorio estable, facilitar la colaboración y evitar mezclar tareas diferentes en la misma rama.

---

## Modelo recomendado

### Rama principal

Usa una rama principal estable, normalmente:

- `main`

Esta rama debe reflejar el estado listo para producción o, al menos, para integración estable.

---

## Tipos de ramas

### 1. `main`

- rama de referencia principal
- siempre debe estar en estado funcional
- no se recomienda hacer cambios directos si el proyecto es colaborativo

### 2. `feature/*`

Para nuevas funcionalidades.

Ejemplos:

```bash
git checkout -b feature/user-login
git checkout -b feature/dashboard-filters
```

### 3. `fix/*`

Para correcciones de errores.

Ejemplos:

```bash
git checkout -b fix/payment-validation
git checkout -b fix/cache-null-pointer
```

### 4. `hotfix/*`

Para correcciones urgentes en producción.

Ejemplos:

```bash
git checkout -b hotfix/security-patch
git checkout -b hotfix/production-crash
```

### 5. `docs/*`

Para documentación.

Ejemplos:

```bash
git checkout -b docs/update-installation
git checkout -b docs/api-reference
```

### 6. `chore/*`

Para tareas de mantenimiento o configuración.

Ejemplos:

```bash
git checkout -b chore/update-dependencies
git checkout -b chore/ci-improvements
```

### 7. `release/*`

Para preparación de versiones.

Ejemplos:

```bash
git checkout -b release/v1.4.0
```

---

## Flujo recomendado

1. Actualiza la rama principal
2. Crea una rama nueva desde `main`
3. Desarrolla la tarea en esa rama
4. Haz commits pequeños y claros
5. Abre un Pull Request
6. Revisa, corrige y aprueba
7. Fusiona a `main`
8. Elimina la rama si ya no se usa

---

## Ejemplo de flujo real

```bash
# 1. Actualizar main
git checkout main
git pull origin main

# 2. Crear rama para la tarea
git checkout -b feature/user-profile
a
# 3. Trabajar
# ... cambios ...

git add .
git commit -m "feat: add user profile card"

git push origin feature/user-profile
```

Luego se crea el PR desde `feature/user-profile` hacia `main`.

---

## Reglas recomendadas

- nunca trabajes directamente en `main` en equipos
- cada tarea debe ir en su propia rama
- un PR no debe mezclar tareas distintas
- usa nombres descriptivos
- elimina ramas viejas una vez fusionadas
- mantén `main` siempre en un estado saludable

---

## Buenas prácticas para merges

### Merge commit

Útil cuando quieres mantener historial completo y claro.

### Squash merge

Útil para mantener un historial más limpio y ordenado en repositorios con muchas pequeñas correcciones.

### Rebase

Útil para mantener líneas de trabajo más lineales, pero debe usarse con cuidado si ya se ha compartido la rama.

---

## Registro de rama por tipo de tarea

| Tipo | Uso | Ejemplo |
|---|---|---|
| `feature/*` | nuevas funcionalidades | `feature/login-form` |
| `fix/*` | correcciones | `fix/button-alignment` |
| `hotfix/*` | emergencias | `hotfix/api-503` |
| `docs/*` | documentación | `docs/setup-guide` |
| `chore/*` | mantenimiento | `chore/update-eslint` |
| `release/*` | preparación de versionado | `release/v2.0.0` |

---

## Recomendación final

El modelo más práctico para la mayoría de proyectos es:

- `main` --> rama estable
- `feature/*` --> desarrollo de nuevas capacidades
- `fix/*` --> correcciones
- `hotfix/*` --> emergencia producción
- `release/*` --> preparaciones de lanzamientos

Esto mantiene el repositorio ordenado, facilita revisiones y reduce riesgos.

---

## Checklist rápida

- [ ] rama creada desde `main`
- [ ] trabajo centrado en una sola tarea
- [ ] commits claros
- [ ] PR abierto con descripción
- [ ] revisión solicitada
- [ ] merge realizado a `main`
- [ ] rama eliminada si ya no se usa

---

## Resumen

En resumen: cada cambio debe ir en su propia rama, con nombre claro, un PR bien descrito y una integración controlada a la rama principal. Eso evita caos, facilita la colaboración y mejora la calidad del proyecto.

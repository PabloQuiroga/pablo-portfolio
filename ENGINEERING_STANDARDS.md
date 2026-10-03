# Engineering Standards

Este documento define las reglas técnicas y de proceso que rigen todos los proyectos de este portfolio.

## 1. Git & GitHub Workflow

### Branching Strategy
- `main`: Rama estable. Solo contiene código probado y versiones oficiales (releases).
- `develop`: Rama de integración. Donde se unen las funcionalidades antes de pasar a main.
- `feature/nombre-tarea`: Ramas temporales para desarrollar una funcionalidad específica.

### Commit Convention
Se utiliza el estándar de **Conventional Commits**:
- `feat:` Nueva funcionalidad.
- `fix:` Corrección de un error.
- `docs:` Cambios solo en documentación.
- `refactor:` Cambio de código que no arregla un bug ni añade feature.
- `test:` Añadir o corregir tests.
- `chore:` Tareas de mantenimiento (configuración, dependencias).

### Pull Request Standard
Todo PR debe incluir:
- Descripción clara del cambio.
- Justificación técnica (link al ADR o Especificación).
- Evidencia de que los tests pasaron.

## 2. SDD Framework (Proceso de Desarrollo)

Cada funcionalidad debe seguir estrictamente este flujo:
1. **Specification**: Definir el "QUÉ" en `docs/specification.md`.
2. **Design**: Definir el "CÓMO" en `docs/architecture.md`.
3. **Decision**: Registrar decisiones críticas en `docs/decisions/ADR-XXX.md`.
4. **Implementation**: Escribir el código siguiendo el diseño.
5. **Verification**: Ejecutar tests y validar CI.
6. **Release**: Crear tag de versión y actualizar documentación.

## 3. Testing Strategy

- **C/C++**: Prioridad en la detección de fugas de memoria (Valgrind) y casos borde.
- **JVM (Java/Kotlin)**: Prioridad en Unit Testing con Mocks y pruebas de integración.
- **Android**: Prioridad en el estado de la UI y pruebas de instrumentación.

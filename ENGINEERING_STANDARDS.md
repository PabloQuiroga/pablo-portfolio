# Engineering Standards

Este documento define las reglas técnicas y de proceso que rigen todos los proyectos de este portfolio.

## 1. Git & GitHub Workflow

### Branching Strategy

La estrategia de ramas debe adaptarse al tamaño y la complejidad del proyecto.

- `main`: rama principal. Debe mantenerse en un estado coherente y funcional, de acuerdo con el alcance del proyecto.
- `develop`: rama de integración opcional. Se utiliza cuando el flujo de trabajo del proyecto justifica mantener una rama de integración separada.
- `feature/nombre-tarea`: convención recomendada para ramas temporales de funcionalidades o cambios específicos.

Cada proyecto puede adoptar una estrategia más sencilla cuando resulte suficiente, siempre que mantenga un flujo de trabajo claro y revisable.

### Commit Convention
Se utiliza el estándar de **Conventional Commits**:
- `feat:` Nueva funcionalidad.
- `fix:` Corrección de un error.
- `docs:` Cambios solo en documentación.
- `refactor:` Cambio de código que no arregla un bug ni añade feature.
- `test:` Añadir o corregir tests.
- `chore:` Tareas de mantenimiento (configuración, dependencias).

### Pull Request Standard

Todo Pull Request debe incluir, según corresponda al cambio:

- **Descripción:** resumen claro del cambio y su objetivo.
- **Justificación técnica:** referencia a la especificación, al diseño o al ADR relacionado, cuando corresponda.
- **Verificación:** evidencia de las pruebas y los controles de calidad ejecutados. Si algún control aplicable no se ejecutó o falló, debe indicarse explícitamente.
- **Documentación:** actualización de los documentos afectados por el cambio.

Los requisitos específicos de aprobación, revisión y protección de ramas se definen según las características de cada proyecto.

### 2. SDD Framework (Proceso de Desarrollo)

Cada proyecto debe mantener documentación suficiente para definir, diseñar, implementar y verificar sus funcionalidades. La estructura concreta de archivos puede variar según el lenguaje, la arquitectura y la complejidad del proyecto.

El proceso de desarrollo sigue estas etapas:

1. **Specification:** definir el comportamiento esperado, los requisitos y los criterios de aceptación.
2. **Design:** documentar el diseño lógico, la arquitectura y las responsabilidades de los componentes, según las necesidades del proyecto.
3. **Decision:** registrar las decisiones técnicas relevantes mediante ADR (Architecture Decision Records), cuando corresponda.
4. **Implementation:** implementar el código de acuerdo con la especificación y el diseño acordados.
5. **Verification:** ejecutar las pruebas y los controles de calidad definidos para el proyecto, incluyendo CI cuando esté configurada.
6. **Release:** cuando corresponda, preparar una versión identificable y actualizar la documentación relacionada.

Los documentos de especificación, diseño, planificación, trazabilidad y decisiones deben mantenerse coherentes entre sí. Cada proyecto debe identificar cuáles son sus documentos de referencia y evitar mantener definiciones contradictorias.

## 3. Testing Strategy

La estrategia de testing debe adaptarse al lenguaje, la arquitectura, los riesgos y el alcance de cada proyecto.

- **C/C++:** priorizar los casos borde, la gestión de memoria y la detección de comportamiento indefinido. Utilizar herramientas como AddressSanitizer, UndefinedBehaviorSanitizer o Valgrind cuando sean compatibles y aporten valor.
- **JVM (Java/Kotlin):** priorizar las pruebas unitarias de la lógica de negocio y las pruebas de integración de los componentes que lo requieran. Utilizar mocks cuando ayuden a aislar dependencias externas.
- **Android:** priorizar las pruebas unitarias del dominio y la lógica de presentación, además de pruebas de integración o instrumentación cuando sean necesarias.

Cada proyecto debe documentar los controles de calidad que efectivamente utiliza. Las herramientas y los niveles de cobertura exigidos deben definirse según sus necesidades, evitando declarar controles que no estén configurados.

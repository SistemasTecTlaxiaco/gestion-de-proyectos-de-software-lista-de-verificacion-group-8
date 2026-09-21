# 📋 Instrumento de Auditoría de Calidad y Control de Cambios
**Asignatura:** Gestión de Proyectos de Software (SCG-1009)  
**Unidad 2:** Gestión de Calidad  
**Tema:** 2.5 Control de Cambios y Configuración de Software  
**Evidencia de Aprendizaje:** Lista de verificación (auditoría de código/documentación + sistema de insignias)  

---

<p align="center">
  <img src="https://img.shields.io/badge/Calidad%20GitHub-Insignia%20de%20Plata-C0C0C0?style=for-the-badge&logo=github&logoColor=black" alt="Insignia de Plata" />
  <img src="https://img.shields.io/badge/Estándares-CMMI%20%7C%20MoProSoft-1B2A4A?style=for-the-badge" alt="Estándares" />
  <img src="https://img.shields.io/badge/Control%20de%20Cambios-Tema%202.5-D97706?style=for-the-badge" alt="Tema 2.5" />
</p>

---

## 1. Homologación de Estándares Tradicionales a GitHub (CMMI / MoProSoft).

Para garantizar la rigurosidad técnica, los procesos tradicionales de calidad se adaptan a los mecanismos nativos de GitHub:

| Estándar Tradicional | Área de Proceso / Práctica | Mecanismo en GitHub | Justificación Técnica |
| :--- | :--- | :--- | :--- |
| **MoProSoft** (Nivel 2) | **Gestión de Configuración (GCO):** Control formal de elementos y solicitudes de cambio aprobadas. | • **Pull Requests (PR)** obligatorios.<br>• **Tags semánticos** (`v1.0.0`) para líneas base. | Cada cambio debe documentarse y asociarse a una versión inmutable antes de integrarse. |
| **CMMI-DEV** (Nivel 2) | **Configuration Management (CM):** Identificar elementos de configuración y auditar su integridad. | • **Commits atómicos y semánticos**.<br>• `.gitignore` depurado (evita binarios y variables `.env`). | Garantiza la trazabilidad bidireccional entre el requerimiento y el artefacto modificado. |
| **CMMI-DEV** (Nivel 3) | **Verification (VER) & Validation (VAL):** Revisiones técnicas entre pares (*Peer Reviews*). | • **Branch Protection Rules:** Mínimo 1 aprobación obligatoria para merge a `main`. | Ningún cambio entra a la rama principal sin revisión formal de otro miembro del equipo. |
| **CMMI-DEV / MoProSoft** | **Aseguramiento de Calidad (PPQA):** Detección temprana de defectos de forma sistemática. | • **GitHub Actions (CI):** Ejecución de linter, compilación y pruebas de sintaxis automáticas. | Reduce el error humano auditando la calidad del código previo a la integración. |

---

## 2. Sistema de Insignias y Lista de Verificación (Checklist).

El sistema evalúa el control de configuración en tres niveles de madurez acumulativos:

### 🥉 Nivel 1: Insignia de Bronce (Control Inicial y Línea Base)
*Objetivo:* Garantizar la estructura elemental del proyecto y la higiene del repositorio.

- [x] **BR-01 (Línea Base Documental):** Archivo `README.md` estructurado con contexto, objetivos y comandos base.
- [x] **BR-02 (Higiene del Repositorio):** Archivo `.gitignore` configurado según la pila tecnológica, impidiendo rastrear dependencias (`node_modules/`, `target/`) o credenciales (`.env`).
- [x] **BR-03 (Términos de Distribución):** Archivo `LICENSE` formalmente establecido en la raíz.
- [x] **BR-04 (Trazabilidad Básica de Cambios):** Historial de commits con mensajes descriptivos en imperativo (evitando commits genéricos como *"cambios"* o *"fix"*).

### 🥈 Nivel 2: Insignia de Plata (Estandarización, MoProSoft y Revisión por Pares)
*Objetivo:* Implementar gobernanza del flujo de trabajo y trazabilidad formal entre requerimientos y código.

- [x] **PL-01 (Estrategia de Ramas):** Prohibido el trabajo directo sobre la rama `main`; uso de ramas temáticas (`feature/*`, `fix/*`).
- [x] **PL-02 (Plantillas de Solicitud de Cambio):** Archivo `.github/PULL_REQUEST_TEMPLATE.md` configurado para estandarizar descripción, pruebas y vinculación a tareas.
- [x] **PL-03 (Plantillas de Requerimientos):** Configuración de `.github/ISSUE_TEMPLATE/` para estandarizar historias de usuario e incidencias.
- [x] **PL-04 (Revisión Formal entre Pares):** Pull Requests documentados con revisión técnica y vinculación explícita a Issues (`Closes #X`).
- [x] **PL-05 (Guía de Colaboración):** Archivo `CONTRIBUTING.md` con lineamientos de commits, nombres de ramas y reglas de merge.

###  Nivel 3: Insignia de Oro (CMMI Nivel 3 - Verificación Automatizada)
*Objetivo:* Asegurar la calidad del software de manera automatizada y blindar la integridad del producto final.

- [ ] **OR-01 (Protección de Gobernanza):** `Branch Protection Rules` activas en `main` (bloqueo de force push y revisión obligatoria).
- [ ] **OR-02 (Integración Continua / CI):** Pipeline en GitHub Actions (`.github/workflows/ci.yml`) que compila o analiza sintaxis en cada PR.
- [ ] **OR-03 (Control de Versiones Formal):** Creación de un GitHub Release etiquetado con SemVer (`v0.1.0`) y `CHANGELOG.md`.
- [ ] **OR-04 (Auditoría de Dependencias):** Escaneo activo de vulnerabilidades (Dependabot o auditoría de dependencias en CI).

---

## 3. Reporte de Ejecución de la Auditoría.

* **Fecha de auditoría:** 21 de septiembre de 2026
* **Auditor(a):** Desarrolladora / Gestora del Proyecto
* **Repositorio auditado:** Rama `main` / Repositorio oficial del equipo

### Matriz de Resultados

| Criterio | Estado | Observación Técnica |
| :--- | :---: | :--- |
| **BR-01 a BR-04 (Bronce)** | **CUMPLE** | Estructura documental base, higiene con `.gitignore`, licencia y commits descriptivos en regla. |
| **PL-01 a PL-05 (Plata)** | **CUMPLE** | Plantillas de PR/Issues activas, ramas de trabajo aisladas y trazabilidad con requerimientos. |
| **OR-01** (Branch Protection) | **PENDIENTE** | Requiere configuración manual de políticas de aprobación en *Settings > Branches*. |
| **OR-02** (CI Automatizado) | **PENDIENTE** | Falta enlazar ejecución de pruebas unitarias o linters en GitHub Actions. |
| **OR-03** (Releases SemVer) | **PENDIENTE** | No se ha generado la etiqueta formal `v0.1.0` en la sección de Releases. |
| **OR-04** (Seguridad de Dependencias) | **EN PROCESO** | Habilitado a nivel básico sin bloqueo forzado en PRs. |

---

## 4. Dictamen de Calidad.

* **Insignia Obtenida:** **🥈 PLATA (Silver Quality Badge)**
* **Dictamen y Honestidad Académica:**  
  El repositorio cumple con el 100% de los lineamientos de los niveles Bronce y Plata, demostrando control de configuración y trazabilidad según MoProSoft. No se adjudica la Insignia de Oro con rigor técnico debido a que los pipelines de integración continua automatizada y las reglas de protección forzada de rama están en fase de implementación.

### Plan de Acción Inmediato para Escalar a Oro:
1. Activar regla de protección en GitHub (*Settings > Branches*) para exigir mínimo 1 aprobación en `main`.
2. Añadir pipeline de CI en `.github/workflows/ci.yml` para verificación automática previa a cada merge.
3. Publicar el Release `v0.1.0` asociando la línea base actual.

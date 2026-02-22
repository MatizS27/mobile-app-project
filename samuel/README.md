# Aplicación Móvil de Evaluación entre Pares  
## Flutter + Clean Architecture + GetX

Proyecto universitario de desarrollo móvil orientado a la evaluación entre pares en trabajos colaborativos, siguiendo principios de arquitectura limpia y buenas prácticas de ingeniería de software.

---

## 1. Descripción general del proyecto

La aplicación es una solución móvil desarrollada en Flutter que permite a estudiantes evaluar el desempeño y compromiso de sus compañeros de equipo en actividades colaborativas de curso. No se permite la autoevaluación y se soportan múltiples criterios de valoración como puntualidad, contribución, compromiso y actitud.

El objetivo principal es proporcionar a los docentes información cuantitativa y cualitativa sobre el funcionamiento real de los equipos de trabajo, facilitando procesos de retroalimentación formativa y toma de decisiones académicas.

El proyecto está diseñado para integrarse conceptualmente con el LMS Brightspace, utilizando sus group categories como fuente oficial de conformación de equipos.

---

## 2. Alcance y objetivos

### 2.1 Objetivo general

Desarrollar una aplicación móvil multiplataforma (Android / iOS) que permita la evaluación entre pares en trabajos grupales, ofreciendo un sistema estructurado, seguro y trazable para docentes y estudiantes.

### 2.2 Objetivos específicos

- Gestionar cursos, docentes y estudiantes.
- Permitir que un docente administre múltiples cursos y que un estudiante esté inscrito en varios cursos.
- Importar y sincronizar grupos desde Brightspace.
- Crear actividades de evaluación entre pares con ventana de tiempo definida y visibilidad configurable.
- Aplicar rúbricas con criterios configurables y escalas numéricas.
- Generar reportes agregados y detallados por actividad, grupo y estudiante.
- Garantizar una experiencia de usuario clara y coherente para ambos roles.

---

## 3. Contexto actual (AS-IS)

En el estado actual:

- Los grupos no se crean dentro de la aplicación.
- La conformación de equipos se realiza en Brightspace mediante group categories.
- La aplicación importa y sincroniza esta información desde el LMS.

Supuestos clave:

- Los grupos pueden cambiar y deben mantenerse actualizados.
- La autenticación y almacenamiento de datos dependen de servicios institucionales (por ejemplo, Roble).
- La app se enfoca exclusivamente en la evaluación entre pares.

---

## 4. Roles de usuario y casos de uso

### 4.1 Roles principales

**Docente**
- Crear y gestionar cursos.
- Invitar estudiantes mediante códigos o enlaces.
- Importar grupos desde Brightspace.
- Crear actividades de evaluación.
- Configurar rúbricas y visibilidad de resultados.
- Consultar reportes agregados y detallados.

**Estudiante**
- Unirse a cursos.
- Visualizar actividades pendientes.
- Evaluar a sus compañeros (sin autoevaluación).
- Consultar resultados agregados cuando estén habilitados.

---

## 5. Arquitectura

La aplicación adopta principios de Clean Architecture con separación clara entre presentación, dominio, datos e infraestructura, utilizando GetX para manejo de estado, navegación e inyección de dependencias.

---

## 6. Tecnologías

- Flutter
- GetX
- REST / HTTP
- SQLite / Hive
- Clean Architecture
- Principios SOLID

# Peer Assessment App

Sistema de Evaluación de Desempeño Colaborativo

## Información General

-   **Materia:** Mobile Development Project
-   **Periodo Académico:** 2026-10
-   **Objetivo:** Desarrollar una aplicación móvil en Flutter que
    permita a los estudiantes evaluar el desempeño y compromiso de sus
    pares en actividades colaborativas.
-   **Equipo:** 4 estudiantes por grupo
-   **Tecnologías:** Flutter, GetX
-   **Arquitectura:** Clean Architecture
-   **Servicios Core:** Roble (Autenticación y almacenamiento de datos)

------------------------------------------------------------------------

## Referentes del Sector

### Buddycheck

Herramienta especializada en evaluación por pares integrada con LMS como
Brightspace. Permite calcular el factor de esfuerzo individual para
ajustar calificaciones grupales.

### CATME (Comprehensive Assessment of Team Member Effectiveness)

Sistema académico basado en la nube que utiliza algoritmos para detectar
patrones inusuales en evaluaciones y ofrece rúbricas validadas
científicamente.

### Teammates

Herramienta open-source para feedback anónimo en el aula. Permite
visualizar la brecha entre autopercepción y percepción del equipo.

------------------------------------------------------------------------

## Diseño de la Solución

Se implementa una aplicación única con control de acceso basado en roles
(RBAC).

### Justificación

-   Centralización de lógica de negocio y entidades (Cursos, Grupos,
    Evaluaciones).
-   Integración con Brightspace para importación de categorías de grupo.
-   Uso de servicios Roble para autenticación y persistencia de datos.
-   Permisos obligatorios: Localización y ejecución en segundo plano.

------------------------------------------------------------------------

## Flujo Funcional

1.  Autenticación mediante Roble.
2.  Identificación de rol (Profesor o Estudiante).
3.  Profesor importa grupos desde Brightspace.
4.  Estudiantes se unen mediante invitación o verificación.
5.  Profesor activa evaluación con ventana de tiempo y tipo de
    visibilidad.
6.  Estudiantes evalúan a sus compañeros (sin autoevaluación).
7.  Visualización de resultados según configuración de visibilidad.

------------------------------------------------------------------------

## Matriz de Evaluación

  ----------------------------------------------------------------------------------------
  Criterio         Needs Improvement (2.0) Adequate (3.0)  Good (4.0)     Excellent (5.0)
  ---------------- ----------------------- --------------- -------------- ----------------
  Puntualidad      Ausencias constantes    Llegadas tarde  Generalmente   Siempre puntual
                                           frecuentes      puntual        

  Contribuciones   Participación mínima    Participación   Aportes        Aportes
                                           ocasional       constantes     relevantes y
                                                                          enriquecedores

  Compromiso       Bajo compromiso         Compromiso      Responsable    Compromiso total
                                           intermitente                   

  Actitud          Actitud negativa        Actitud         Actitud        Actitud ejemplar
                                           irregular       positiva       
  ----------------------------------------------------------------------------------------

------------------------------------------------------------------------

## Requisitos Técnicos

-   Clean Architecture obligatoria
-   Uso exclusivo de GetX
-   Integración con servicios Roble
-   Permisos: Localización y Background Work

------------------------------------------------------------------------

## Prototipo

Diseño disponible en Figma (enlace a agregar).

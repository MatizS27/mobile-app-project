# Lost&Found Uni

Sistema digital para la gestión de objetos perdidos dentro de la
universidad, integrado con la aplicación institucional existente.

------------------------------------------------------------------------

## Descripción General

Lost&Found Uni es un módulo que permite digitalizar el proceso actual de
objetos perdidos de la universidad.\
Actualmente, los objetos encontrados se guardan bajo llave hasta que el
dueño reclama diligenciando un formulario y confirmando su propiedad.

La aplicación permite:

-   Registrar objetos encontrados
-   Publicar objetos disponibles para reclamar
-   Solicitar reclamación digital
-   Validar propiedad
-   Integrarse con la aplicación institucional existente (ej:
    Uninorteco)
-   Generar trazabilidad completa del proceso

------------------------------------------------------------------------

## Integración con la App Institucional

Lost&Found Uni puede integrarse como:

-   Un módulo interno dentro de la app universitaria existente
-   Un microservicio conectado mediante API REST
-   Un sistema autenticado con correo institucional
-   Un servicio que use la base de datos de estudiantes y funcionarios

La autenticación puede realizarse usando el sistema institucional
(Single Sign-On).

------------------------------------------------------------------------

## Arquitectura General

``` mermaid
graph TD
    A[Usuario] -->|Login| B[App Flutter]
    B --> C[API Backend]
    C --> D[Base de Datos]
    C --> E[Panel Administrativo]
    E --> C
```

------------------------------------------------------------------------

## Flujo del Sistema

``` mermaid
sequenceDiagram
    participant U as Usuario
    participant A as App
    participant B as Backend
    participant D as Admin

    U->>A: Reporta objeto perdido
    A->>B: Envía solicitud
    B->>D: Notifica administrador
    D->>B: Confirma coincidencia
    B->>A: Notifica aprobación
    A->>U: Usuario reclama objeto
```

------------------------------------------------------------------------

## Modelo de Datos Básico

Objeto: - id - nombre - descripcion - categoria - ubicacion_encontrado -
fecha_encontrado - estado (disponible, reclamado, entregado) -
imagen_url

Usuario: - id - nombre - correo_institucional - rol (estudiante,
administrativo)

SolicitudReclamo: - id - usuario_id - objeto_id -
descripcion_prueba_propiedad - estado (pendiente, aprobado, rechazado)

------------------------------------------------------------------------

## Funcionalidades Clave

### Usuario

-   Ver objetos encontrados
-   Filtrar por categoría o fecha
-   Enviar solicitud de reclamación
-   Subir evidencia
-   Ver estado de su solicitud

### Administrador

-   Registrar objetos encontrados
-   Validar solicitudes
-   Aprobar o rechazar reclamaciones
-   Marcar objeto como entregado
-   Exportar reportes

------------------------------------------------------------------------

## Beneficios

-   Reduce tiempo de gestión manual
-   Mejora la trazabilidad
-   Disminuye pérdida definitiva de objetos
-   Aumenta eficiencia administrativa
-   Mejora experiencia estudiantil

------------------------------------------------------------------------

## Futuras Mejoras

-   Notificaciones push
-   Reconocimiento de imagen
-   Código QR para entrega
-   Estadísticas por facultad
-   Integración con cámaras o sistema de seguridad

------------------------------------------------------------------------

## Licencia

Proyecto académico desarrollado para entorno universitario.

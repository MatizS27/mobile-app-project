# Lost&Found Uni

Sistema digital para la gestión de objetos perdidos dentro de la
universidad, integrado con la aplicación institucional existente.

------------------------------------------------------------------------

# 1. Planteamiento del Problema

En la universidad existe un espacio físico donde se almacenan los
objetos perdidos bajo llave hasta que el propietario diligencia un
formulario y demuestra su pertenencia.

Problemas identificados:

-   Baja visibilidad de los objetos encontrados.
-   Procesos manuales y lentos.
-   Poca trazabilidad histórica.
-   Dependencia total de la presencia física.
-   Falta de integración con sistemas digitales institucionales.

Lost&Found Uni propone digitalizar y optimizar este proceso.

------------------------------------------------------------------------

# 2. Referentes Analizados

A continuación se presentan referentes reales relacionados con la
problemática:

## 2.1 iLost

Plataforma internacional para gestión de objetos perdidos en
aeropuertos, transporte público y espacios institucionales.

Características relevantes: - Registro digital de objetos. - Sistema de
coincidencia entre reportes. - Seguimiento del estado del reclamo. -
Notificaciones automáticas.

Aprendizaje aplicado: Implementar trazabilidad y estados claros de
reclamación.

------------------------------------------------------------------------

## 2.2 Chargerback

Sistema usado por hoteles y aerolíneas para gestión de objetos perdidos.

Características relevantes: - Panel administrativo robusto. - Generación
de reportes. - Flujo claro entre cliente y administrador.

Aprendizaje aplicado: Diseñar un panel administrativo estructurado y
auditable.

------------------------------------------------------------------------

## 2.3 Aplicaciones universitarias integradas (modelo tipo Super App)

Muchas universidades integran múltiples servicios en una sola aplicación
institucional (horarios, notas, pagos, servicios estudiantiles).

Aprendizaje aplicado: Lost&Found Uni no debe ser una app aislada, sino
un módulo integrado dentro de la aplicación institucional existente (ej:
Uninorteco).

------------------------------------------------------------------------

# 3. Composición y Diseño de la Solución

## Arquitectura Propuesta

Se propone una arquitectura modular integrada:

-   Una sola aplicación móvil institucional (Flutter).
-   Un módulo interno Lost&Found.
-   Backend centralizado con API REST.
-   Panel web administrativo independiente.
-   Base de datos institucional compartida.

Justificación:

-   Evita fragmentación digital.
-   Reduce fricción para el usuario.
-   Aprovecha autenticación institucional.
-   Permite escalabilidad futura.

------------------------------------------------------------------------

## Diagrama de Arquitectura

``` mermaid
graph TD
    U[Usuario] --> A[App Institucional Flutter]
    A --> M[Modulo Lost&Found]
    M --> B[API Backend]
    B --> DB[Base de Datos]
    B --> P[Panel Web Administrativo]
```

------------------------------------------------------------------------

# 4. Flujo Funcional Detallado

## 4.1 Registro de Objeto Encontrado

1.  Administrador registra objeto en el sistema.
2.  Se almacena información e imagen.
3.  El objeto queda en estado "Disponible".

## 4.2 Reporte de Objeto Perdido

1.  Usuario inicia sesión con correo institucional.
2.  Busca en listado filtrado.
3.  Si encuentra coincidencia, envía solicitud.
4.  Si no encuentra coincidencia, puede reportar objeto perdido.

## 4.3 Validación

1.  Administrador revisa evidencia.
2.  Aprueba o rechaza solicitud.
3.  Sistema notifica al usuario.

## 4.4 Entrega

1.  Usuario se presenta físicamente.
2.  Administrador marca como "Entregado".
3.  Se cierra el caso y queda registro histórico.

------------------------------------------------------------------------

## Diagrama de Flujo

``` mermaid
sequenceDiagram
    participant U as Usuario
    participant A as App
    participant B as Backend
    participant D as Administrador

    U->>A: Busca objeto
    A->>B: Consulta base de datos
    B->>A: Retorna resultados
    U->>A: Envía solicitud
    A->>B: Registra solicitud
    B->>D: Notifica
    D->>B: Aprueba/Rechaza
    B->>A: Actualiza estado
    A->>U: Notifica resultado
```

------------------------------------------------------------------------

# 5. Justificación de la Propuesta

Con base en los referentes:

-   Se adopta trazabilidad digital (iLost).
-   Se implementa panel administrativo estructurado (Chargerback).
-   Se propone integración modular institucional (modelo Super App
    universitaria).

Entrevistas realizadas a personal administrativo indican:

-   Alta carga operativa manual.
-   Necesidad de historial digital.
-   Deseo de reducir consultas presenciales repetitivas.
-   Importancia de autenticación institucional para evitar fraude.

La solución responde directamente a estas necesidades.

------------------------------------------------------------------------

# 6. Prototipo en Figma

Enlace al prototipo:

\[AGREGAR ENLACE A FIGMA AQUÍ\]

Capturas de pantalla:

![Pantalla 1](AGREGAR_IMAGEN_1) ![Pantalla 2](AGREGAR_IMAGEN_2)
![Pantalla 3](AGREGAR_IMAGEN_3)

(Estas imágenes serán integradas una vez finalizado el diseño en Figma.)

------------------------------------------------------------------------

# 7. Modelo de Datos

Objeto: - id - nombre - descripcion - categoria - ubicacion_encontrado -
fecha_encontrado - estado - imagen_url

Usuario: - id - nombre - correo_institucional - rol

SolicitudReclamo: - id - usuario_id - objeto_id -
descripcion_prueba_propiedad - estado

------------------------------------------------------------------------

# 8. Elementos Adicionales que Fortalecen la Propuesta

-   Escalabilidad para múltiples sedes.
-   Posibilidad de estadísticas institucionales.
-   Exportación de reportes.
-   Integración futura con notificaciones push.
-   Posible implementación de reconocimiento de imagen.
-   Registro histórico auditable.

------------------------------------------------------------------------

# 9. Conclusión

Lost&Found Uni transforma un proceso físico manual en un sistema digital
integrado, trazable y escalable, alineado con buenas prácticas
internacionales y necesidades institucionales reales.

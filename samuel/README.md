# Lost&Found Uni

## Descripción General

Lost&Found Uni es una solución digital para optimizar la gestión de
objetos perdidos dentro de la universidad, integrable como módulo dentro
de la aplicación institucional UninorteCo o como sistema independiente
conectado al ecosistema académico.

El sistema digitaliza el proceso actual (custodia física + formulario de
verificación), agrega trazabilidad, notificaciones, analítica
institucional y control por roles.

------------------------------------------------------------------------

## Referentes Analizados

### 1. Chargerback

Sitio: https://www.chargerback.com\
Sistema profesional usado por aeropuertos y hoteles para gestión de
objetos perdidos.

Aportes: - Flujo estructurado de reclamos - Estados de seguimiento -
Panel administrativo robusto

Limitaciones: - Costoso - No adaptado a ecosistemas académicos - No
integrado a apps universitarias

------------------------------------------------------------------------

### 2. Nextdoor

Sitio: https://nextdoor.com

Aportes: - Modelo comunitario - Publicación sencilla - Filtros por
ubicación

Limitaciones: - Sin control institucional - Sin validación formal de
propiedad - Riesgo de fraude

------------------------------------------------------------------------

### 3. Portales Lost & Found Universitarios (ej. UCLA)

Ejemplo: https://www.transportation.ucla.edu/campus-parking/lost-found

Aportes: - Clasificación estructurada - Centralización

Limitaciones: - Sin app móvil dedicada - Sin notificaciones
inteligentes - Flujo manual

------------------------------------------------------------------------

## Arquitectura General

### Opción Recomendada: Módulo dentro de UninorteCo

Arquitectura lógica:

Usuario -\> UninorteCo -\> Módulo Lost&Found -\> API REST -\> Backend
-\> Base de Datos

------------------------------------------------------------------------

## Arquitectura de Componentes

Frontend: - App móvil (Estudiante) - App móvil (Personal)

Backend: - API Gateway - Servicio de Objetos - Servicio de Reclamos -
Servicio de Autenticación (SSO)

Base de Datos: - Usuarios - Objetos - Reclamos - Auditoría

------------------------------------------------------------------------

## Flujo Funcional

1.  Personal registra objeto encontrado.
2.  Sistema guarda información en base de datos.
3.  Estudiante consulta inventario.
4.  Estudiante envía reclamo.
5.  Personal valida solicitud.
6.  Sistema notifica resultado.
7.  Estudiante retira objeto presencialmente.

------------------------------------------------------------------------

## Tecnologías Propuestas

Frontend: - Flutter - React Native - Kotlin / Swift

Backend: - Node.js + NestJS - Spring Boot - Django REST

Base de Datos: - PostgreSQL - MySQL - Firebase (MVP)

Infraestructura: - AWS - Azure - Google Cloud

Autenticación: - OAuth 2.0 - JWT - SSO institucional

Notificaciones: - Firebase Cloud Messaging

------------------------------------------------------------------------

## Métricas de Éxito

-   Tiempo promedio de recuperación
-   Porcentaje de objetos recuperados
-   Número de reclamos digitales
-   Reducción de carga administrativa
-   Satisfacción estudiantil

------------------------------------------------------------------------

## Conclusión

Lost&Found Uni integra control institucional, movilidad, trazabilidad y
analítica en un solo sistema, alineado con el ecosistema digital
universitario y preparado para escalar a futuro.

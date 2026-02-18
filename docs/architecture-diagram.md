
---

````markdown
# Arquitectura del Sistema – Enfoque REST y GraphQL
````
---

# 1. Arquitectura General

El sistema ha sido diseñado bajo un modelo de **arquitectura desacoplada orientada a servicios**, aplicando principios modernos de diseño de software que garantizan escalabilidad, mantenibilidad y flexibilidad tecnológica.

La arquitectura separa claramente las responsabilidades entre cliente, capa de exposición de API, lógica de negocio y almacenamiento de datos.

## Componentes Principales

- **Cliente Web / Mobile**
- **API REST**
- **Servidor GraphQL**
- **Capa de Servicios (Service Layer)**
- **Base de Datos**
````

# 2. Diagrama Arquitectónico Simplificado

        ┌─────────────┐
        │   Cliente   │
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │   API Layer │
        └──────┬──────┘
         ┌─────┴─────┐
         ▼           ▼
     ┌────────┐  ┌──────────┐
     │  REST  │  │ GraphQL  │
     └────┬────┘  └────┬─────┘
          ▼            ▼
        ┌─────────────────┐
        │  Service Layer  │
        └────────┬────────┘
                 ▼
           ┌──────────┐
           │ Database │
           └──────────┘
````

Este diseño permite que ambas tecnologías (REST y GraphQL) compartan la misma lógica de negocio, evitando duplicación de código y manteniendo coherencia en el dominio.

---

# 3. Flujo de Comunicación – REST

## Proceso

Cliente → Endpoint REST → Servicio → Base de Datos → Respuesta completa

## Descripción Técnica

1. El cliente realiza una petición HTTP (GET, POST, PUT, DELETE).
2. El endpoint REST recibe la solicitud.
3. La capa de servicios ejecuta la lógica de negocio.
4. Se consulta la base de datos.
5. Se devuelve una representación completa del recurso solicitado.

## Características

* Entrega la representación total del recurso.
* Basado en estándares HTTP.
* Permite versionado de API.
* Alta compatibilidad con múltiples clientes.

---

# 4. Flujo de Comunicación – GraphQL

## Proceso

Cliente → Query específica → GraphQL Resolver → Servicio → Base de Datos → Respuesta precisa

## Descripción Técnica

1. El cliente envía una consulta estructurada (Query o Mutation).
2. El servidor GraphQL interpreta la consulta.
3. El Resolver ejecuta la lógica correspondiente en la capa de servicios.
4. Se obtiene la información desde la base de datos.
5. Se devuelve únicamente los campos solicitados.

## Características

* Entrega datos específicos bajo demanda.
* Reduce el over-fetching y under-fetching.
* Mayor eficiencia en aplicaciones móviles.
* Permite consultas compuestas en una sola petición.

---

# 5. Principios de Ingeniería Aplicados

La arquitectura implementa los siguientes principios fundamentales:

* **Separación de responsabilidades (Separation of Concerns)**
* **Bajo acoplamiento (Low Coupling)**
* **Alta cohesión**
* **Escalabilidad horizontal**
* **Versionado de API**
* **Optimización del consumo de datos**
* **Reutilización de lógica de negocio**

Estos principios permiten que el sistema evolucione sin afectar otras capas del sistema.

---

# 6. Justificación Arquitectónica

La incorporación simultánea de REST y GraphQL tiene un propósito comparativo y estratégico.

## REST

* Estándar ampliamente adoptado en la industria.
* Fácil integración con servicios externos.
* Modelo simple y estructurado.
* Ideal para APIs públicas.

## GraphQL

* Mayor eficiencia en recuperación de datos.
* Reduce consumo de ancho de banda.
* Mejora experiencia en clientes móviles.
* Permite consultas dinámicas y flexibles.

La coexistencia de ambos modelos permite evaluar rendimiento, consumo de red y experiencia de desarrollo.

---

# 7. Ventajas del Modelo Propuesto

* Arquitectura flexible.
* Fácil mantenimiento.
* Adaptable a nuevos clientes.
* Permite migración progresiva entre tecnologías.
* Preparado para entornos escalables en la nube.

---

# 8. Conclusión

La arquitectura propuesta permite realizar una evaluación objetiva entre los enfoques REST y GraphQL, garantizando una estructura desacoplada y orientada a servicios.

Este diseño asegura:

* Escalabilidad
* Mantenibilidad
* Eficiencia en consumo de datos
* Flexibilidad tecnológica

Finalmente, la elección entre REST o GraphQL dependerá del contexto del negocio, tipo de cliente y requerimientos de rendimiento del sistema.

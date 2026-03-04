

```markdown
## Gestión del Ciclo de Vida con Git & GitHub  
## REST vs GraphQL


```
## 📌 Descripción del Proyecto

Este repositorio documenta el diseño arquitectónico y los contratos técnicos de un sistema orientado a la gestión de información de Pokémon, desarrollado como ejercicio académico para simular el entorno  de un Arquitecto de Software.

El enfoque principal no es la implementación de lógica de negocio, sino la correcta administración del ciclo de vida del proyecto mediante:

- Gestión de tareas con Issues  
- Trabajo estructurado con ramas (branching strategy)  
- Integración controlada mediante Pull Requests  
- Documentación técnica versionada  
- Evidencia clara del historial de commits  

Cada avance fue desarrollado siguiendo buenas prácticas de control de versiones y organización  del trabajo.

---

## 🎯 Objetivo Académico

Demostrar:

1. Uso adecuado de Git y GitHub en un entorno colaborativo.
2. Organización del trabajo mediante ramas independientes.
3. Documentación formal de contratos REST y esquema GraphQL.
4. Comparación técnica entre arquitecturas REST y GraphQL.
5. Evidencia de integración  mediante Pull Requests.

---

## 🏗 Arquitectura del Sistema

El sistema fue modelado bajo una arquitectura desacoplada orientada a servicios, permitiendo evaluar dos enfoques de exposición de datos:

- API REST tradicional
- API GraphQL orientada a consultas específicas

### Diagrama General


```
            ┌───────────────────┐
            │      Cliente      │
            │   Web / Mobile    │
            └─────────┬─────────┘
                      │
                      ▼
            ┌───────────────────┐
            │     API Layer     │
            ├──────────┬────────┤
            │   REST   │ GraphQL│
            └──────┬───┴───┬────┘
                   │       │
                   ▼       ▼
            ┌───────────────────┐
            │   Service Layer   │
            └─────────┬─────────┘
                      │
                      ▼
            ┌───────────────────┐
            │     Database      │
            └───────────────────┘
```



##  Estructura del Repositorio
```

PracticaFinal/
│
├── README.md
├── docs/
│   ├── rest-api.md
│   ├── graphql-schema.md
│   └── architecture-diagram.md 
```


##  Estrategia de Trabajo en Git

El proyecto fue desarrollado siguiendo una estrategia basada en ramas:

- `main` → Rama principal protegida  
- `feat/rest-api` → Diseño de endpoints REST  
- `feat/graphql-schema` → Definición del esquema GraphQL  
- `feat/architecture-diagram` → Diseño arquitectónico  

Cada componente fue trabajado en su rama independiente y posteriormente integrado mediante Pull Request vinculado a su Issue correspondiente.

No se realizaron desarrollos directos en `main`.

---

##  Gestión de Tareas (Issues)

Se crearon Issues para organizar el trabajo:

- Diseño de endpoints REST  
- Definición de esquema GraphQL  
- Diagrama de arquitectura  

Cada Issue fue cerrado únicamente después de su integración mediante Pull Request aprobado.

---

##  Comparativa Técnica

### REST

- Entrega representación completa del recurso.
- Puede generar over-fetching.
- Amplia compatibilidad y adopción.
- Simplicidad estructural.

### GraphQL

- Permite solicitar solo los campos necesarios.
- Reduce consumo de datos.
- Permite consultas anidadas en una sola petición.
- Ideal para entornos móviles.

---

##  Justificación Técnica

Para aplicaciones donde la eficiencia en red es crítica (ej. entornos móviles), GraphQL ofrece ventajas claras en optimización de consumo de datos.

REST mantiene ventajas en simplicidad, estandarización y compatibilidad universal.

La arquitectura propuesta permite evaluar ambos enfoques de manera objetiva.

---

## 📚 Enfoque  Aplicado

Este proyecto evidencia:

- Control de versiones disciplinado
- Organización estructurada del trabajo
- Documentación técnica clara
- Integración controlada
- Registro histórico verificable


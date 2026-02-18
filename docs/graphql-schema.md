
````markdown
## 1. Introducción

GraphQL es un lenguaje de consulta para APIs que permite al cliente solicitar únicamente los datos que necesita.

A diferencia de REST, donde los endpoints devuelven recursos completos, GraphQL:
````

---
- Permite consultas específicas
- Reduce el over-fetching
- Permite consultas anidadas en una sola petición
- Mejora la eficiencia en aplicaciones móviles
````

---
## 2. Definición del Tipo Principal

```graphql
type Pokemon {
  id: ID!
  name: String!
  height: Int
  weight: Int
  evolutions: [Pokemon]
}
````

---

## 3. Definición de Queries

```graphql
type Query {
  pokemons(first: Int): [Pokemon]
  pokemon(id: ID!): Pokemon
}
```

---

## 4. Ejemplo de Consulta Específica

```graphql
query {
  pokemon(id: "1") {
    name
    weight
    height
  }
}
```

### Resultado

Solo se retornan los campos solicitados.

---

## 5. Consulta con Relaciones (Anidamiento)

```graphql
query {
  pokemon(id: "1") {
    name
    weight
    height
    evolutions {
      name
    }
  }
}
```

Esta consulta obtiene:

* Datos básicos
* Evoluciones
* En una sola petición HTTP

---

## 6. Ventajas Técnicas

* Evita over-fetching
* Reduce under-fetching
* Mejora rendimiento en redes móviles
* Estructura tipada
* Auto-documentación mediante introspection

---

## 7. Consideraciones Arquitectónicas

GraphQL es ideal cuando:

* El cliente necesita flexibilidad
* Se requiere optimización de consumo de datos
* Existen múltiples fuentes de datos


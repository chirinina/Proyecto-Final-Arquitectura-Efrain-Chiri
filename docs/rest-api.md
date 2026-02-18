
```markdown

## 1. Introducción

El presente documento define el contrato técnico de la API REST del sistema de gestión de Pokémon.  
El diseño sigue principios RESTful, promoviendo:

- Uso correcto de métodos HTTP
- Recursos identificables mediante URI
- Respuestas estructuradas en JSON
- Separación clara entre cliente y servidor
- Escalabilidad y mantenibilidad

La API se diseña como parte de una arquitectura desacoplada orientada a servicios.

Base URL:

```

[https://api.pokemon-system.com/v1](https://api.pokemon-system.com/v1)

```

---

## 2. Convenciones Técnicas

| Elemento | Convención |
|----------|------------|
| Formato de datos | JSON |
| Autenticación | Token Bearer (JWT) |
| Versionado | URI versioning (/v1/) |
| Códigos HTTP | Estándar RFC 7231 |

---

## 3. Endpoints Definidos

---

### 3.1 Obtener lista paginada de Pokémon

```

GET /pokemon

````

#### Descripción
Retorna una colección paginada de Pokémon registrados en el sistema.

#### Parámetros opcionales

| Parámetro | Tipo | Descripción |
|-----------|------|------------|
| page | int | Número de página |
| limit | int | Cantidad de registros por página |

#### Ejemplo de Respuesta

```json
{
  "page": 1,
  "limit": 10,
  "total": 150,
  "data": [
    {
      "id": 1,
      "name": "Bulbasaur",
      "type": ["grass", "poison"]
    }
  ]
}
````

#### Código de respuesta

* 200 OK
* 400 Bad Request

---

### 3.2 Obtener Pokémon por ID

```
GET /pokemon/{id}
```

#### Descripción

Devuelve la representación completa del recurso Pokémon identificado por su ID.

#### Ejemplo

```
GET /pokemon/1
```

#### Respuesta

```json
{
  "id": 1,
  "name": "Bulbasaur",
  "height": 7,
  "weight": 69,
  "abilities": [],
  "moves": [],
  "stats": []
}
```

#### Código de respuesta

* 200 OK
* 404 Not Found

---

### 3.3 Crear nuevo Pokémon

```
POST /pokemon
```

#### Cuerpo de la solicitud

```json
{
  "name": "NuevoPokemon",
  "height": 10,
  "weight": 100
}
```

#### Respuesta

* 201 Created
* 400 Bad Request

---

## 4. Consideraciones Arquitectónicas

* La API expone recursos completos, lo que puede generar over-fetching.
* Se prioriza simplicidad y compatibilidad universal.
* Ideal para sistemas tradicionales cliente-servidor.
* Permite integración sencilla con aplicaciones web y móviles.

---

## 5. Justificación de Diseño

El modelo REST fue elegido por:

* Estándar ampliamente adoptado
* Fácil testeo mediante herramientas como Postman o ReqBin
* Escalabilidad horizontal
* Independencia del cliente

---
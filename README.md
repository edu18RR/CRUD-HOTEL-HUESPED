# Documentación de API Rest Hotel Softtek v1.0.0
## Descripción del proyecto

Este proyecto radica en la creación de una API Rest que pueda crear un huesped 
con "x" reservaciones. Ya que la relación es que un huesped puede tener muchas 
reservaciones, por lo tanto el diagrama queda de la siguiente manera.

![img.png](img.png)

## Recursos
El proyecto esta creado con las siguientes tecnologías, las primeras 4 se obtienen
al momento de crear el proyecto.

| Plugin                | URL                      |
|-----------------------|--------------------------|
| Spring Web            | https://start.spring.io/ |
| Spring Data JPA       | https://start.spring.io/ |
| Lombok                | https://start.spring.io/ |
| H2 Database           | https://start.spring.io/ |
| Spring Doc (opcional) | https://springdoc.org/#getting-started |

## Accesos

Acceso a la base de datos H2 mediante URL:

```sh
url: http://localhost:8080/hotel-softtek/h2-console/
user: sa
password: 
```
![img_2.png](img_2.png)

Acceso a la UI de la documentación de la API mediante URL:
```sh
url: http://localhost:8080/hotel-softtek/swagger-ui/index.html#/
```

## Uso en Postman

### POST (crear Huesped)
```sh
http://localhost:8080/hotel-softtek/api/v1/huespedes
```
Hay que insertar un JSON para esta petición.

``` json
{
    "nombre": "Eduardo",
    "apellido": "Rosas",
    "fechaNacimiento": "1990-05-15",
    "nacionalidad": "Mexicana",
    "telefono": "555-123-4567",
    "reservas": [
        {
            "fechaEntrada": "2024-07-10",
            "fechaSalida": "2024-07-11",
            "valor": 3500.0,
            "formaPago": "Tarjeta"
        },
        {
            "fechaEntrada": "2024-07-10",
            "fechaSalida": "2024-07-11",
            "valor": 300.0,
            "formaPago": "Tarjeta"
        }
    ]
}
```
Ejemplo:
![img_4.png](img_4.png)
### GET

Despues de validar la creación de un nuevo usuario lo validamos:

```sh
http://localhost:8080/hotel-softtek/api/v1/huespedes
```
Ejemplo:

![img_1.png](img_1.png)

### POST (editar Huesped)
```sh
http://localhost:8080/hotel-softtek/api/v1/huespedes/editar/1
```

Hay que insertar un JSON para esta petición.

``` json
{
    "nombre": "Eduardo",
    "apellido": "Rosas Rangel",
    "fechaNacimiento": "1990-08-15",
    "nacionalidad": "Mexicano",
    "telefono": "555-123-4567",
    "reservas": [
        {
            "fechaEntrada": "2024-02-10",
            "fechaSalida": "2024-02-11",
            "valor": 6500.0,
            "formaPago": "Efectivo"
        },
        {
            "fechaEntrada": "2024-11-11",
            "fechaSalida": "2024-11-11",
            "valor": 3000.0,
            "formaPago": "Tarjeta"
        }
    ]
}
```
Ejemplo:
![img_1.png](img_1.png)
### DELETE
```sh
http://localhost:8080/hotel-softtek/api/v1/huespedes/eliminar/1
```

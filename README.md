
# Desafío de Construcción de un Foro con Java y SpringBoot

¡Hola! Bienvenidos y bienvenidas a un nuevo desafío. En esta oportunidad, vamos a poner en práctica los conocimientos adquiridos en Java y SpringBoot. ¿Cuál es la propuesta que les traigo en esta oportunidad? Vamos a realizar nuestra propia API REST con la temática de un foro. ¿Qué les parece, entonces, construir su propio foro? Un lugar donde las personas puedan crear sus tópicos con sus dudas o con sugerencias que otras personas puedan también responder e interactuar allí dentro de una comunidad. Suena genial, ¿verdad? ¿Qué les parece si vemos entonces lo que traigo para ustedes y la propuesta para nuestro desafío?

Para eso, voy a presentar aquí mi pantalla y les estoy mostrando el Insomnia. En este caso, el Insomnia va a ser la aplicación que vamos a utilizar para conseguir hacer las pruebas de nuestra aplicación. Como lo estamos desarrollando todo a nivel de backend, recordemos que no vamos a tener una interfaz gráfica, pero sí vamos a conseguir entonces probar todos nuestros endpoints o rutas.

## Requisitos

- Java 11+
- Spring Boot
- Insomnia (o cualquier herramienta de tu preferencia para pruebas de API)
- Base de datos (puede ser la de tu elección: MySQL, PostgreSQL, etc.)

## Endpoints

### Listar Tópicos

- **Método:** GET
- **Ruta:** `/topicos`
- **Descripción:** Lista todos los tópicos creados por los usuarios.
- **Respuesta:** 
  ```json
  [
    {
      "id": 1,
      "titulo": "Mi primer tópico",
      "mensaje": "¿Cómo inicio en Java?",
      "curso": "Java Básico",
      "usuarioId": 1
    },
    {
      "id": 2,
      "titulo": "Duda sobre Spring Boot",
      "mensaje": "¿Cómo configuro mi aplicación?",
      "curso": "Spring Boot",
      "usuarioId": 2
    }
  ]
  ```

### Crear Tópico

- **Método:** POST
- **Ruta:** `/topicos`
- **Descripción:** Crea un nuevo tópico.
- **Cuerpo de la petición:**
  ```json
  {
    "titulo": "Nuevo tópico",
    "mensaje": "Contenido del tópico",
    "curso": "Curso relacionado",
    "usuarioId": 3
  }
  ```
- **Respuesta:**
  ```json
  {
    "id": 3,
    "titulo": "Nuevo tópico",
    "mensaje": "Contenido del tópico",
    "curso": "Curso relacionado",
    "usuarioId": 3,
    "status": 201
  }
  ```

### Eliminar Tópico

- **Método:** DELETE
- **Ruta:** `/topicos/{id}`
- **Descripción:** Elimina un tópico existente.
- **Respuesta:**
  ```json
  {
    "message": "Tópico eliminado con éxito.",
    "status": 200
  }
  ```

## Autenticación

Para crear, actualizar o eliminar tópicos, es necesario que el usuario esté autenticado. Para ello, utilizaremos JWT (JSON Web Tokens).

### Generar Token

- **Método:** POST
- **Ruta:** `/auth`
- **Descripción:** Genera un token de autenticación.
- **Cuerpo de la petición:**
  ```json
  {
    "email": "usuario@example.com",
    "password": "contraseña"
  }
  ```
- **Respuesta:**
  ```json
  {
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
  }
  ```

## Herramientas

### Insomnia

Utilizaremos Insomnia para probar nuestra API. Aquí es donde podemos realizar peticiones GET, POST, DELETE, etc., y verificar las respuestas.

### Trello

Vamos a utilizar Trello para gestionar nuestro proyecto. Crearás tu propia copia del tablero de Trello, donde podrás gestionar, mover tarjetas y añadir información extra según sea necesario.

## Ejemplo de Uso

1. **Listar Tópicos:**
   - Realizar una petición GET a `localhost:8080/topicos`.
   - Verificar que la respuesta contenga la lista de tópicos.

2. **Crear Tópico:**
   - Realizar una petición POST a `localhost:8080/topicos` con el cuerpo adecuado.
   - Verificar que la respuesta sea un 201 y contenga el nuevo tópico creado.

3. **Eliminar Tópico:**
   - Realizar una petición DELETE a `localhost:8080/topicos/{id}` con el token de autenticación.
   - Verificar que la respuesta sea un 200 y el tópico haya sido eliminado.

## Conclusión

Este desafío es una excelente oportunidad para poner en práctica tus conocimientos en Java y Spring Boot, creando una API REST funcional y segura. Además, podrás gestionar tu proyecto de manera efectiva utilizando Trello. ¡Estoy ansiosa por ver el resultado final y cómo personalizas tu propio foro!

¡Manos a la obra y hasta la próxima!

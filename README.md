
# Backend Despacho — Spring Boot

## Descripción General

Microservicio backend desarrollado con Spring Boot para administrar operaciones de despachos mediante APIs REST.

El sistema permite:
- Registrar despachos.
- Consultar información.
- Actualizar registros.
- Eliminar despachos.
- Persistir información en MySQL.

---

# Tecnologías Utilizadas

| Tecnología | Uso |
|---|---|
| Java 21 | Lenguaje principal |
| Spring Boot | Framework |
| Spring Data JPA | Persistencia |
| MySQL | Base de datos |
| Maven | Dependencias |
| Docker | Contenerización |
| Swagger | Documentación APIs |

---

# Arquitectura del Proyecto

```text
Controller
   ↓
Service
   ↓
Repository
   ↓
Database
```

---

# Explicación del Funcionamiento

## Controllers

Los controladores reciben solicitudes HTTP.

Ejemplo:

```java
@GetMapping
public List<Despacho> listar()
```

Funciones:
- GET
- POST
- PUT
- DELETE

---

## Services

La capa Service contiene:
- Lógica de negocio.
- Validaciones.
- Reglas del sistema.

---

## Repository

La capa Repository:
- Accede a MySQL.
- Ejecuta consultas.
- Usa Spring Data JPA.

---

# Flujo de Funcionamiento

```text
Frontend
   ↓
Controller
   ↓
Service
   ↓
Repository
   ↓
MySQL
```

---

# Configuración

## application.properties

```properties
server.port=8081

spring.datasource.url=jdbc:mysql://localhost:3306/despacho_db
spring.datasource.username=root
spring.datasource.password=
```

---

# Instalación

## Requisitos

- Java 21
- Maven
- MySQL

---

## Ejecutar Proyecto

```bash
./mvnw spring-boot:run
```

Windows:

```bash
mvnw.cmd spring-boot:run
```

---

# Swagger

Documentación:

```bash
http://localhost:8081/swagger-ui/index.html
```

---

# Docker

## Construir Imagen

```bash
docker build -t backend-despacho .
```

---

## Ejecutar Contenedor

```bash
docker run -d -p 8081:8081 backend-despacho
```

---

# Persistencia

El sistema utiliza MySQL.

Spring Data JPA:
- Maneja entidades.
- Relaciones.
- Consultas automáticas.

---

# Manejo de Errores

El backend incorpora:
- Exceptions personalizadas.
- Handler global.
- Respuestas HTTP.

---

# Integración con Frontend

El backend es consumido desde React mediante Axios.

Ejemplo:

```javascript
axios.get("http://localhost:8081/api/despachos")
```

---

# AWS EC2

Arquitectura:

```text
Frontend EC2
   ↓
Backend Despacho EC2
   ↓
MySQL
```

---

# Buenas Prácticas

- Arquitectura en capas
- APIs RESTful
- Docker
- Swagger
- Separación de responsabilidades
#Task Management API#
#Descripción
Esta es una API para una aplicación de gestión de tareas, desarrollada en Java utilizando Spring Boot y siguiendo la arquitectura hexagonal. La API permite realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) en las tareas y está conectada a una base de datos MySQL.

#Diseño
Arquitectura Hexagonal
La arquitectura hexagonal, también conocida como arquitectura de puertos y adaptadores, tiene como objetivo permitir la separación de preocupaciones y facilitar el mantenimiento y la evolución del software. En esta API, la arquitectura se estructura de la siguiente manera:

Dominio: Contiene las entidades y las reglas de negocio.
Aplicación: Contiene los servicios y la lógica de aplicación.
Infraestructura: Contiene los adaptadores secundarios (por ejemplo, la implementación de repositorios).
Entrada(in)/Salida(out): Contiene los adaptadores primarios (por ejemplo, controladores REST).

#Tecnologías Utilizadas
Java 17
Spring Boot 3
MySQL
JPA/Hibernate
Maven

Configuración del Proyecto
Prerrequisitos
JDK 17 o superior
MySQL 8 o superior
Maven 3.6 o superior
Instalación
Clona el repositorio:

bash
Copiar código
git clone https://github.com/OctavioToledo/Api-TareasApp.git

#Configura la base de datos:

-SQL

CREATE DATABASE tasks;

Configura el archivo application.properties en src/main/resources:

properties
Copiar código
spring.datasource.url=jdbc:mysql://localhost:3306/tasks
spring.datasource.username= tu_usuario
spring.datasource.password= tu_contraseña
spring.jpa.hibernate.ddl-auto=update


#Uso de la API
Endpoints

-Crear una Tarea
URL: /api/tasks
Método: POST
Cuerpo:
json
Copiar código
{
  "title": "Nueva tarea",
  "description": "Descripción de la tarea",
  "completed": true/false
}

-Obtener todas las Tareas
URL: /api/tasks
Método: GET

-Obtener una Tarea por ID
URL: /api/tasks/{taskId}
Método: GET

-Actualizar una Tarea
URL: /api/tasks/{taskId}
Método: PUT
Cuerpo:
json
Copiar código
{
  "title": "Título actualizado",
  "description": "Descripción actualizada",
  "completed": true/false
}

-Eliminar una Tarea
URL: /api/tasks/{taskId}
Método: DELETE

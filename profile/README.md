## PROJECT #2 - CASTELLS 🏰

Este proyecto implementa un sistema utilizando microservicios para gestionar el mundo de los **castells** (torres humanas tradicionales de Cataluña). En su versión más simple, donde tenemos un casteller (con un role de USER), un cap o jefe (con un rol mas de ADMIN) y una diada (un evento o actividad donde se juntan casteller con cap).


## Diagrama UML

![UML CASTELLS.png](img/UML%20CASTELLS.png)


## Arquitectura del proyecto

  El sistema está compuesto por los siguientes microservicios:

- **`discovery-server`**: Eureka Server para descubrimiento de microservicios.
- **`castells-gateway`**: API Gateway para redirigir peticiones a los servicios correspondientes.

  Eureka clients:
  
- **`castells-cap`**: Servicio dedicado a los *caps de colla*.
- **`castells-casteller`**: Servicio que gestiona los datos de los *castellers* .
- **`castells-diada`**: Servicio encargado de gestionar las *diades* 

## Características principales

1. **Discovery Server** (`discovery-server`): actúa como registro central de microservicios usando Eureka. Todos los servicios se registran aquí automáticamente.
2. **API Gateway** (`castells-gateway`): intercepta todas las peticiones externas y las redirige al microservicio adecuado (Load Balance). T
3. **Microservicios de dominio**:
   - Cada uno gestiona una parte del sistema y su propia base de datos.
   - Se comunican entre ellos mediante peticiones REST.
  
## Tecnologias

- Java 
- Spring
- Lombok
- SQL 
- Git
- Eureka Server
- Eureka Client

## Programas

- IntelliJ
- MySQL Workbench
- Postman
- GitHub 

## Cómo ejecutar la aplicación


1. **Clonar los repositorios**

    Cada microservicio, server y gateway tiene un repositorio por separado dentro de la organización:
   
    https://github.com/Project-2-ODS

2. **Configurar la base de datos en cada microservicio** (cap, diada y casteller)

  Dentro de MySQL Workbench, generar un Schema por cada microservicio, deben respetar el nombre de la aplication.properties de cada uno:
  
    - castells-cap
    - castells-diada
    - castells-casteller
  
4. **Iniciar el servidor Discovery Server**

   Se ejecuta por el puerto 8761
   
5. **Iniciar microservios y gateway**

  Se debe seguir este orden (servidor-microservicios-gateway) para su correcta ejecución.

6. Se podrá consultar el estado de los microservicios entrando a:
   
   http://localhost:8761
  
7. Se podrán hacer consultas CRUD, dentro de Postman.
   




## Extra Links

Para consultar el Repositorio en GitHub:

https://github.com/Project-2-ODS

Para consultar el Task Manager de cómo se fue desarrollando éste proyecto:

https://trello.com/b/1XCWKdn0/project2-castells

Para consultar la presentación de diapositivas:

link

---

## Trabajo Futuro

Para hacer evolucionar el proyecto, comenzaria por algo sencillo como cambiar las relaciones, por ejemplo, en la relacion Diada->Casteller de One-To-One a One-To-Many, donde un Casteller puede ir a varias Diadas, y tambien poder hacer un listado de los Castellers que participarán en dicha Diada. Luego jugar con la escavilidad y poder sumar un microservicio más, de la gente que se encarga de la contabilidad de la Colla, y poder sumar cada dia más funciones y mas microservicios.


## Miembro

Francisco Ismael Farrando.

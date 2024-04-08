
# CASO DE NEGOCIO DEVOPS/DEVSECOPS DESARROLLADO PARA UMSA Y SOFTTEK

## Situación inicial 📍

Como parte de un equipo de DevOps hemos recibido un pedido del área de desarrollo de nuestra empresa. Este equipo necesita que se aprovisione la infraestructura necesaria para varios microservicios alojados en AWS. Este trabajo se deberá realizar utilizando Pipelines e IaC. Esto permitirá a los desarrolladores del equipo poder habilitar pasajes automáticos a ambientes de desarrollo. Nuestro líder técnico ya cuenta con los requerimientos desagregados en un backlog de tareas listo para que comencemos la etapa de implementación.

## Nuestro objetivo 📋

Poder desplegar la infraestructura solicitada utilizando herramientas de automatización, pipelines y orquestación en la nube de AWS. También debemos dejar implementados los pipelines de compilación, testeo SAST y despliegue aplicativo en varios ambientes.

## Metodología de trabajo🔧

A lo largo de los próximos dos sprints se deberá trabajar en la implementación de la infraestructura y los pipelines de despliegue, junto con el equipo aplicando el marco de trabajo ágil y teniendo espacios de reunión con su líder técnico para realizar consultas y tener un seguimiento de las tareas realizadas y asegurar la calidad de los entregables producidos.

## Requerimientos 

Como Ingeniero DevOps, deberá crear la infraestructura necesaria para los ambientes de Desarrollo (DEV) y Testing (QA) de diversos microservicios, para habilitar luego los pasajes o despliegues de los mismos. Los microservicios son todos similares, pero tendrán breves diferencias que estarán indicadas en cada tarea del backlog.

1. Para el ambiente de Desarrollo, se requiere que la entrega sea continua, cada cambio de código fuente deberá disparar la compilación y despliegue del código fuente en este ambiente, tomando como origen la rama indicada en cada tarea del backlog. También se requiere se ejecute análisis de código estático como paso posterior a la compilación.
2. Para el ambiente de Testing, se requiere que la entrega sea manual, mediante la ejecución manual del pipeline cuando así se requiera. En el ambiente de Testing el despliegue se realizará directamente utilizando la imagen previamente recopilada y entregada en el ambiente de desarrollo.

## Requerimientos técnicos💻

- La infraestructura deberá ser desplegada en la nube de Amazon Web Services (AWS).
- El código fuente utilizado para generar la infraestructura debe ser escrito utilizando la sintaxis Terraform, esta deberá alojarse en un repositorio de la empresa que se indicará en cada tarea.
- A algunos microservicios se les deberán agregar paquetes solicitados por los desarrolladores. Esto se indicará en cada tarea.
- Los pasos de compilación de cada microservicio deberán incluir la dockerización de una imagen con la versión del mismo.
- Los pipelines necesarios para desplegar a los ambientes deberán utilizar la imagen docker generada previamente y subida a Docker Hub e implementarla según los criterios de cada microservicio.
- Para generar los pipelines podrá utilizar cualquier herramienta que desee, aunque recomendamos utilizar Github Actions para simplificar el proceso.

## ¿Qué vamos a validar?🔍

Para asegurar el correcto cumplimiento de las tareas, el líder se encargará de revisar diferentes aristas del proyecto. Estos son algunos puntos que vamos a validar:

- Calidad y funcionalidad del proyecto
- Legibilidad del código y documentación.
- Cumplimiento de los requerimientos técnicos

## Otras habilidades requeridas para un correcto desarrollo del proyecto:

Trabajo Colaborativo, Negociación y Liderazgo. Se evaluarán a partir de la siguiente rúbrica de evaluación:

| Nivel de desempeño | Trabajo colaborativo | Negociación | Liderazgo |
|-------------------|----------------------|-------------|------------|
| 🔴                | Trabaja de manera individual constantemente. No muestra interés en comprender las necesidades del equipo. | Demuestra debilidades en la identificación y gestión de acuerdos. | Comprende las necesidades del equipo y del Cliente. |
| 🟡                | Por momentos trabaja de manera grupal, compartiendo su trabajo, visión e ideas. | Negocia de manera efectiva, buscando soluciones que beneficien a ambas partes, equipo y Cliente. | Lidera eficazmente en situaciones específicas, pero puede mejorar en la gestión general del equipo. |
| 🟢                | Trabaja de manera grupal, compartiendo su trabajo y conocimiento con el resto de sus pares. Ofrece ayuda, buscando la mejora continua y la satisfacción de requerimientos del cliente. | Negociación avanzada con enfoque en soluciones ganar-ganar, centradas en los requerimientos del Cliente y que fomentan relaciones a largo plazo. | Inspira y guía al equipo de manera efectiva, contribuyendo al crecimiento del equipo. |

## Referencias🦺

- Recurra a los Working Time (disponibles en la plataforma) efectuados durante la cursada para tener un paso a paso de cómo proceder en la ejecución de las tareas asignadas.
- Puede utilizar herramientas de inteligencia artificial que le ayuden a comprender qué se está solicitando en la tarea.
- Existen diversos tutoriales y guías en la documentación oficial de cada herramienta y proveedor que le podrán ayudar sobre los procesos que debe ejecutar en cada caso para interconectar los servicios y herramientas necesarias.

## Recursos🎁

- Toda la información referente al flujo de trabajo y datos técnicos se encontrará disponible en cada tarea asignada del sprint correspondiente.
- Se utilizará Trello como herramienta de gestión del Backlog de tareas para este caso de negocio.

## Entregables ✅

### 🎯Objetivos del Sprint 1:

- Armar la infraestructura correspondiente y los Archivos de IaC. Se requiere Terraform, Docker y EC2 como mínimo.
- La IaC (Terraform/Docker) debe ser subida al repositorio indicado en cada tarea asignada.
- Todas las tareas del Sprint asignadas a su nombre deben estar finalizadas y su estado en el board debe ser el correcto.

### 🎯Objetivos del Sprint 2:

- Preparar los pipelines de CICD para que efectúe el despliegue aplicativo a Dev y QA. Para Dev el despliegue debe ser automático, para QA el Despliegue debe ser manual.
- Todas las tareas del Sprint asignadas a su nombre deben estar finalizadas y su estado en el board debe ser el correcto.
- La ejecución de los pipelines debe ser independiente, esto quiere decir que si un pipeline se vuelve a correr, no impactará sobre la ejecución anterior.
- Validar esto si incluye scripts en sus pipelines.

### Extras (plus)

- Se valorará el uso de herramientas adicionales como pueden ser Grafana y SonarQube.

 - 󰗒Para Grafana puede conectar Grafana Cloud a la infraestructura y monitorear en tiempo real durante la demo. Puede monitorear sus recursos de docker locales, por ejemplo.
 - 󰗒Para SonarQube, puede pasar el código fuente por una instancia de SonarQube (SAST) y subir el reporte generado al repositorio de código fuente que se utilizó para IaC.

# Microservicio en NodeJS 

El archivo App.js contiene el microservicio.

Es necesario efectuar un npm update para actualizar los paquetes.

No se incluyo un .gitIgnore por lo que los paquetes también se suben, no obstante y como aclaración esto no es una buena practica en el mundo real.

Cada Microservicio posee su propio branch. Deberá clonar el branch y trabajar sobre el mismo en su propio repositorio GitHub dado que las Github actions y el manejo de Secrets y variables deberá efectuarlo en su propio repo.

Una vez generados los archivos de IaC, DockerFiles, Actions. Al finalizar el trabajo, deberán subirlos a este repositorio utilizando un nuevo branch con su propio nombre. 

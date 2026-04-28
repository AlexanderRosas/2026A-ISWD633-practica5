# COMPLETAR  
Antes de esta practica, el levantar un entorno con una base datos, requeria del uso de muchos comandos en la terminal, teniendo que recordar absolutamente cada uno de los pasos y las variables de entorno para que fucione correctamente. Siendo muy probable un error humano en alguno de los tipeos de información.
Con Docker Compose, aprendí que puedo definir toda mi infraestructura en un solo archivo YAML, lo que reduce drásticamente el error "humano".

## Aprendizajes Claves
  Orqueztacion simple; puedo levantar varios servicios de un solo comando,
  El uso de depends_on con la condición service_healthy es vital; aprendí que no basta con que el contenedor de la base de datos esté "arriba", sino que debe estar   listo para recibir conexiones antes de que la aplicación intente contactarlo.
  Me sorprendió que Compose crea una red por defecto donde los servicios se encuentran por su nombre (ej. mysql-service), simplificando la configuración del         DB_HOST.
## Problemas solucionados 
Al configurar SonarQube, el contenedor se cerraba porque Postgres no terminaba de arrancar a tiempo. Lo solucioné implementando un healthcheck en Postgres usando pg_isready y vinculando a Sonarqube con la condición service_healthy. También tuve problemas de indentación en el YAML; aprendí que Docker Compose es muy estricto con los espacios y no acepta tabuladores.

# Curso de Docker en Platzi

Esta es una aplicación de ejemplo para el curso de Docker de Platzi.

En esta rama se modifica docker compose con la imagen que se genera con el docker file,
ademas se agrega un volumen para copiar el proyecto y se le indica una ruta que no debe modificar.

tambien se utliza un command que sobreescribre el CMD dentro del docker file.

Comando Utilizados

### hace un build de los servicios en el directorio actual
`docker-compose build`  

### El nombre de la imagen suele ser <path>_<Service name>:latest

#### Vuelve a crear la imagen del servicio app
`docker-compose build <service name>`

### inicia los servicios, y crea una imagen nueva en caso de que detecte cambios
`docker-compose up -d` 

# Compose en equipo: override
docker-compose.override.yml es un archivo que se encarga de sobreescribir tu configuración de docker-compose.yml , se puede usar para tener segura tu configuración y para no guardar los cambios en el repositorio de git.

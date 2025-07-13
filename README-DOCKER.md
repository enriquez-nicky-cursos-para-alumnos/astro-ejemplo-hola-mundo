
## Pasos para levantar un contenedor para una nueva app de astro en modo desarrollo
- Ubicarte en tu carpeta raiz
- Crear un archivo docker-compose.yml
- Pegar este manifiesto
```sh
services:
  astro-ejemplo-hola-mundo:
    image: node:20
    container_name: astro-ejemplo-hola-mundo
    working_dir: /app
    volumes:
      - ./:/app
    ports:
      - "4321:4321"  
    stdin_open: true       # Para permitir entrada interactiva (como prompts)
    tty: true              # Para simular una terminal
```
- Crear el contenedor docker-compose up -d astro-ejemplo-hola-mundo
- Entrar al terminal del contenedor con docker exec -it astro-ejemplo-hola-mundo bash
- Dentro de contenedor ejecutar npm create astro@latest
- En las preguntas 
    - Si te pide nombre de proyecto, escribe ./astro-ejemplo-hola-mundo
    - Si te pide como empezar el proyecto , elige Basic 
    - Si te pide instalar dependencias, elige Yes
- Vuelve a entrar tu Visual Code y dentro del contenedor ejecutar npm run dev -- --host

## Video Ayudita
- https://youtu.be/9Ry329l56nU
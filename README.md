<a name="readme-top"></a>
![Symfony][Symfony]
![PHP][PHP]

<br />
<div align="center">
<h3 align="center">Jobeet Symfony Docker</h3>
</div>

## Sobre el Proyecto
El marco de trabajo Symfony es un marco MVC full-stack que ayuda a desarrollar sitios web más rápido. También establece un conjunto de mejores prácticas que le ayudarán a desarrollar sitios web mantenibles y seguros. Y la defensa de las mejores prácticas comienza tan pronto como desea instalar el propio marco de trabajo.

La instalación de Symfony no es muy diferente a la instalación de cualquier otro software PHP, pero para hacer que su instalación sea segura desde el principio, no debe poner todos los archivos bajo el directorio raíz de su sitio web, como lo hacen muchas otras guías de instalación. Aunque llevará un poco más de tiempo instalar Symfony de esta manera, un poco de esfuerzo adicional al principio realmente vale la pena a largo plazo. Además, al igual que con cualquier otra instalación de software PHP, hay muchas pequeñas trampas en las que puede caer que pueden hacer que su experiencia sea más difícil de lo necesario, por lo que intentaremos ayudarlo a evitarlas.

<p align="right">(<a href="#readme-top">Ir arriba</a>)</p>

### Instalación

1. Copiar el repositorio
2. Construir los contenedores de docker
    ```
        docker-compose up -d
    ```
3. Importar las tablas en la base de datos
    ```
        docker exec -it <ID_CONTAINER> php /var/lib/symfony/1.4/data/bin/symfony doctrine:build --all --no-confirmation
    ```
4. En caso de estar en modo desarollo, podemos llenar las tablas con los fixtures

    ```
        docker exec -it 74325747dcb6 php /var/lib/symfony/1.4/data/bin/symfony doctrine:data-load 
    ```

 5. Damos permisos al repositorio
    ```
        docker exec -it 44e8d5eb301b chown -R www-data:www-data "/var/www/jobeet"
    ```
 6. Podemos acceder al siguiente enlace para ver el formulario de creación de trabajos
    ```
        http://localhost:8000/frontend_dev.php/job/new
    ```
 7. Para acceder a phpmyadmin: 
    ```
        http://localhost:8081/
    ```


Acceso a base de datos:
host: host.docker.internal:8002
user : jobeet
pass : jobeet


<p align="right">(<a href="#readme-top">Ir arriba</a>)</p>


[Symfony]: https://img.shields.io/badge/Symfony-000000?style=for-the-badge&logo=Symfony&logoColor=white
[PHP]: https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white

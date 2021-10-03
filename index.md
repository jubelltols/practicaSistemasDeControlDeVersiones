## Sistemas de control de versiones

### ¿Qué es git?
Git es un sistema de control de versiones.
Un sistema de control de versiones nos va a servir para trabajar en equipo de una manera mucho más simple y optima cuando estamos desarrollando software.
Con Git vamos a poder controlar todos los cambios que se hacen en nuestra aplicación y en nuestro código y vamos a tener control absoluto de todo lo que pasa en el código, pudiendo volver atrás en el tiempo, pudiendo abrir diferentes ramas de desarrollo, etc.
Vamos a poder trabajar en equipo de una manera muy sencilla y optimizada, de forma que si tenemos dos o tres personas trabajando en ciertas funcionalidades del proyecto y nosotros podemos estar trabajando en nuestra parte del código. Cuando acabamos de desarrollar nuestro código, utilizamos Git para mezclar los cambios con los otros compañeros. De forma que el código se mezcla de manera perfecta sin generar ningún tipo de fallo y de forma rápida.
También nos va a proporcionar un listado de los cambios(commits) y podemos volver atrás en el tiempo a cualquiera de esos cambios o commits.
Además tendremos la posibilidad de trabajar con ramas de desarrollo, que nos van a permitir desarrollar cosas que divergen mucho del programa principal.

### La metodología utilizada para el desarrollo de la web
Git flow, que como su nombre indica, es un flujo de trabajo aplicado a un repositorio Git. Vincent Driessen fue el encargado de popularizarlo, definiendo un modelo estricto de ramificación diseñado en torno a los lanzamientos del proyecto. Es ideal para proyectos que lleven una planificación de entregas iterativas. Permite la paralelización del desarrollo mediante ramas independientes para la preparación, mantenimiento y publicación de versiones del proyecto así como soporta la reparación de errores en cualquier momento.
## Ramas principales
# Rama master
Contiene cada una de las versiones estables del proyecto. Cualquier commit que subamos en esta rama debe estar preparado para que se pueda incluir en producción.

# Rama develop
Contiene el código de desarrollo de la siguiente versión planificada del proyecto. En ella se incluirán cada una de las nuevas características que se desarrollen. Esta rama puede incorporarse tanto en una rama release (que veremos más adelante) como en la rama master, para su despliegue en producción.

## Ramas de apoyo
# Ramas feature
Estas ramas tienen que surgir de la rama develop. Cada una de estas ramas almacenan código de desarrollo con nuevas características. Típicamente existen solamente en los repositorios locales de los desarrolladores y no en el repositorio origen. Una vez terminado su desarrollo, se incorporarán nuevamente a la rama develop, que contendrá la última versión de código en desarrollo.

# Ramas release
Como las ramas feature, las ramas release también tienen que surgir de la rama develop. Contienen el código de la versión que se va a liberar próximamente. Es un paso previo y preparatorio para la versión definitiva de producción. En ella se incluye todo el código de develop necesario para el lanzamiento. Puede que contenga algún error pequeño que se debe de arreglar en este momento para no incluirlo en producción. Una vez finalizada la rama, esta se debe incluir tanto en la rama develop como en la rama master.

#Ramas hotfix
Estas ramas surgen de la rama master. Contienen una versión de producción con un error que se desea arreglar urgentemente. Una vez arreglado el error, se incluye el contenido de esta rama en las ramas master y develop para subsanar el error. Además, hay que marcar la versión arreglada de producción con un tag en la rama master.

### Explicacion de la practica 
Ramas hotfix
Estas ramas surgen de la rama master. Contienen una versión de producción con un error que se desea arreglar urgentemente. Una vez arreglado el error, se incluye el contenido de esta rama en las ramas master y develop para subsanar el error. Además, hay que marcar la versión arreglada de producción con un tag en la rama master.

Nuestro equipo de programadores está compuesto por 3 personas. Por este motivo, hemos decidido dividir el trabajo de la siguiente forma:
- El usuario 1 que es el más experimentado, se encargará de crear el repositorio del proyecto e implementará la estructura inicial del proyecto utilizando el siguiente boilerplate (link). Esta página inicial incluirá la cabecera, la barra de navegación con el acceso a Home y el footer de la página. En la parte central del home incluirá una breve descripción del curso.
- El usuario 2 creará la sección de “Modificar contenido HTML” en el que incluirá algún ejemplo similar al que existe en el siguiente enlace así como una explicación de dicho código. También desarrollará la sección “Modificar atributos HTML
- El usuario 3 que acaba de llegar a la empresa implementará la sección “Modificar estilos CSS” de la misma forma que ha hecho el usuario 2. Añadirá ejemplos similares a este
(comentando el código).
Así pues, nuestra tarea consistirá en crear un repositorio en Github en el que simulemos toda la implementación acordada además de documentar todo el proceso correctamente para que nuestro cliente vea que somos una empresa seria y trabajamos siguiendo una metodología. Esta documentación, deberá estar incluida en el github pages del propio repositorio del proyecto.

### Creacion del repositorio Github

![Screenshot](image10.png)

### Implementacion de la estructura inicial del proyecto utilizando un [Boilerplate](https://github.com/h5bp/html5-boilerplate)
```
npx create-html5-boilerplate practicaSistemasDeControlDeVersiones
```
```
cd practicaSistemasDeControlDeVersiones
```
```
npm install
```
![Screenshot](imagn30.png)
```
git init
```
```
git add .
```
![Screenshot](image5.png)
```
git commit -m "Estructura inicial"  
```
![Screenshot](image10.png)
![Screenshot](image7.png)

### Primer push al repositorio remoto
```
git branch -M main
```
```
git remote add origin https://github.com/jubelltols/practicaSistemasDeControlDeVersiones.git
```
```
git push -u origin main
```
![Screenshot](image3 (3).png)

### Adecuacion de la estructura inicial para la metodología Git Flow
```
git flow init
```
```
git branch
```
```
git push -u origin develop
```
![Screenshot](image3 (4).png)

### Creacion de la pagina inicial por el usuario 1
```
git add .
```
```
git commit -m "Pagina inicial"  
```
```
git push
```
### Clonacion del repositorio por el usuario 2
```
git clone https://github.com/jubelltols/practicaSistemasDeControlDeVersiones.git
```
```
cd practicaSistemasDeControlDeVersiones
```
```
git flow init 
```
### Creacion de la features contenidoHTML por el usuario 2
```
git flow feature start contenidoHTML
```
### Creacion de la seccion modificar contenido HTML por el usuario 2
```
git add .
```
```
git commit -m "MOTIVO DEL COMMIT: Creacion seccion: Modificar contenido HTML IMPLEMENTACIÓN: creacion de la pagina: modificar contenido HTML con una pequeña explicaion y un ejemplo"
```
```
git flow feature publish contenidoHTML
```
![Screenshot](image4 (3).png)
```
git flow feature finish contenidoHTML
```
```
git push origin --all
```
### Creacion de la features atributosHTML por el usuario 2
```
git flow feature start atributosHTML
```
### Creacion de la seccion modificar atributos HTML por el usuario 2
```
git add .
```
```
git commit -m "MOTIVO DEL COMMIT: Creacion seccion: Modificar atributos HTML IMPLEMENTACIÓN: creacion de la pagina: modificar atributos HTML con una pequeña explicaion y un ejemplo"
```
![Screenshot](image11.png)
```
git flow feature publish feature/atributosHTML
```
```
git flow feature finish atributosHTML
```
```
git push origin --all
```
### Clonacion del repositorio por el usuario 3
```
git clone https://github.com/jubelltols/practicaSistemasDeControlDeVersiones.git
```
```
cd practicaSistemasDeControlDeVersiones
```
```
git flow init 
```
### Creacion de la features estilosCSS por el usuario 3
```
git flow feature start estilosCSS
```
### Creacion de la seccion modificar estilos CSS por el usuario 3
```
git add .
```
```
git commit -m "MOTIVO DEL COMMIT: Creacion seccion: Modificar estilos CSS IMPLEMENTACIÓN: creacion de la pagina: modificar estilos CSS con una pequeña explicaion y un ejemplo"
```
```
git flow feature publish estilosCSS
```
```
git flow feature finish estilosCSS
```
```
git push origin --all
```
![Screenshot](image2.png)
### Fusion de todas las ramas por el usuario 1
```
git pull 
```
```
git checkout main
```
```
git merge --no-ff develop
```
```
git push origin main
```
### Etiquetacion a la version 1 (v1.0) por el usuario 1
```
git tag v1.0
```
```
git push origin v1.0
```
![Screenshot](image1.png)
### Creacion de la rama test por el usuario 1
```
git checkout -b test v1.0
```
```
git push origin test
```
## Git Hook: 
### Automatización de la instalación del proyecto

### Verificación del formato de mensaje de commit.
![Screenshot](image8.png)
### Check caracteres extraños
![Screenshot](image9.png)
### Verificar formato correcto ficheros html

### Añadir hook a carpeta gitHooks y vincular carpeta 
```
mkdir gitHooks
```
```
git config core.hooksPath gitHooks
```
![Screenshot](image6.png)



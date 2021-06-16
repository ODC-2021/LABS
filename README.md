# Laboratorios de Organización
Recopilado de trabajos del laboratorio de la materia del primer cuatrimestre del 2021.

# ¿Cómo añadir mi laboratorio?
Pasos a seguir:
1. Tener el laboratorio hecho xdxd
2. Tener un usuario de GitHub y unirse a la organización. Se debe pedir invitación a `@shirosweets` o `@AgustinMDominguez`
3. Clonar el repositorio
4. Elegir una forma para subir el laboratorio ([ver abajo](#Formas-para-subir-mi-laboratorio)).

# Formas para subir mi laboratorio
- [Forma 1: Subir los archivos directamente](#Forma-1:-Subir-los-archivos-directamente)
    - [Pasos a seguir en el repositorio F1](#Pasos-a-seguir-en-el-repositorio-F1)
- [Forma 2: Repositorio dentro de otro](#Forma-2:-Repositorio-dentro-de-otro)
    - [Pasos a seguir en el repositorio F2](#Pasos-a-seguir-en-el-repositorio-F2)
- [Forma 3: Linkear el repositorio](#Forma-3:-Linkear-el-repositorio)
    - [Pasos a seguir en el repositorio F3](#Pasos-a-seguir-en-el-repositorio-F3)
- [Errores comunes con Git](#Errores-comunes-con-Git)
    - [Please tell me who you are](#Please-tell-me-who-you-are)
        - [Solución "please tell me who you are"](#Solución-"please-tell-me-who-you-are")
---
## Forma 1: Subir los archivos directamente
**Pros:**
- Rápido de hacer.
- Son 3 comandos simples de git (`git add`, `git commit`, `git push`).
- Puedes controlar qué se ve del código fuente y que no.

**Contras:**
- Se pierden los commits si los han realizado en otro repositorio.
- Límite de 5000MB o 500MB (dependiendo el tipo de cuenta de Github) por commit.

### Pasos a seguir en el repositorio F1
1. Abrir la terminal:

    Linux:
    > `Ctrl + Alt + T`

    Windows:
    > `Win + R`

    Type:
    > `cmd.exe`

    Mac:
    > `Command (o Cmd) ⌘`

    > `Shift ⇧`

2. Clonar el repositorio:
    > `git clone https://github.com/ODC-2021/LABS`

3. Cambiarnos a la carpeta del repositorio:
    > `cd LABS/`

4. Actualizar el repositorio (por las dudas):
    > `git pull origin main`

5. Crear una branch con el formato `apellido1_apellido_2`.
    > `git branch apellido1_apellido_2`

6. Cambiarse a esa branch:
    > `git checkout apellido1_apellido_2`

7. Crear una carpeta con el formato `nombre_apellido1_apellido_2`.

8. Copiar los archivos del laboratorio.

9. En [LABS.md](LABS.md):
Agregar laboratorio a la lista de `LABS.md` con su información básica, como indica el formato:
    * Titulo del proyecto. *[Opcional]*
    * Integrantes.
    * Descripción general de lo que se ve en pantalla.
    * Algunas imágenes y/o videos de muestra para intrigar al lector.
    * Un link al repositorio o acceso a las instrucciones.

10. Usar uno de los siguientes comandos:

    Este comando añadirá directamente todos los archivos que hayamos modificado:
    > `git add -A`

    Este comando necesita especificar qué archivos deseamos subir:
    > `git add archivo.s archivo2.s`

11. Es necesario ahora subir un commit para guardar los cambios:

    > `git commit -m "Nombre del commit"`

12. Pushear a la branch creada:
    > `git push origin apellido_1_apellido2`

13. Usar una de las siguientes opciones para mergear a `main`:
    * Crear una *Pull Request* en GitHub hacia `main` y asignar a `@shirosweets` o `@AgustinMDominguez`
    * Avisar a `@shirosweets` o `@AgustinMDominguez` que la branch fue pusheada para que se realize el merge.

## Forma 2: Repositorio dentro de otro
Git nos permite traer un repositorio un repositorio dentro de otro ("como linkeado o como una redirección"). Documentación de [submódulos](https://git-scm.com/book/es/v2/Herramientas-de-Git-Subm%C3%B3dulos)

**Pros:**
- Preservan los commits realizados.
- Los commits preservados señalan a su autor.
- Se actualiza permanentemente si se modifica el repositorio origen.
- Se preservan las tags, topics y configuraciones.
- El repositorio resultante sería liviano.
- Apoyar los proyectos open source :octocat:

**Contras:**
- Es necesario un repositorio público (preferentemente de GitHub).
- Si era en otra plataforma, los commits se harán con ese email y si no existe una cuenta en Github aparecerá sólo el nombre del autor.
- Comandos avanzados de git.
- Se va a mostrar como esté el repositorio, sin ser posible hacer alteraciones particulares para este repo o controlar lo que se ve.
- Explota una abeja si lo haces mal.

### Pasos a seguir en el repositorio F2
1. Abrir la terminal:

    Linux:
    > `Ctrl + Alt + T`

    Windows:
    > `Win + R`

    Type:
    > `cmd.exe`

    Mac:
    > `Command (o Cmd) ⌘`

    > `Shift ⇧`

2. Clonar el repositorio:
    > `git clone https://github.com/ODC-2021/LABS`

3. Cambiarnos a la carpeta del repositorio:
    > `cd LABS/`

4. Actualizar el repositorio (por las dudas):
    > `git pull origin main`

5. Crear una branch con el formato `apellido1_apellido_2`:
    > `git branch apellido1_apellido_2`

6. Cambiarse a esa branch:
    > `git checkout apellido1_apellido_2`

7. Agregar submódulo con el url del repositorio y extraerlo en una carpeta con el nombre del laboratorio:
    > `git submodule add github_url nombre_apellido_1_apellido2`

8. Realizamos un commit con el cambio agregado:
    > `git commit -m "Link submodule nombre_apellido_1_apellido2"`

9. En [LABS.md](LABS.md):
Agregar laboratorio a la lista de `LABS.md` con su información básica, como indica el formato:
    * Titulo del proyecto. *[Opcional]*
    * Integrantes.
    * Descripción general de lo que se ve en pantalla.
    * Algunas imágenes y/o videos de muestra para intrigar al lector.
    * Un link al repositorio o acceso a las instrucciones.

10. Usar uno de los siguientes comandos:

    Este comando añadirá directamente todos los archivos que hayamos modificado:
    > `git add -A`

    Este comando necesita especificar qué archivos deseamos subir:
    > `git add archivo.s archivo2.s`

11. Es necesario ahora subir un commit para guardar los cambios:

    > `git commit -m "Nombre del commit"`

12. Pushear a la branch creada:
    > `git push origin apellido_1_apellido2`

13. Usar una de las siguientes opciones para mergear a `main`:
    * Crear una *Pull Request* en GitHub hacia `main` y asignar a `@shirosweets` o `@AgustinMDominguez`
    * Avisar a `@shirosweets` o `@AgustinMDominguez` que la branch fue pusheada para que se realize el merge.

## Forma 3: Linkear el repositorio

**Pros:**
- No es necesario utilizar comandos de git complejos.
- El repositorio resultante sería liviano.

**Contras:**
- No todos los grupos han trabajado con repositorios.
- No compartir el código fuente.
- Todos sabrán que no sabes usar git y bajarás de lvl.

### Pasos a seguir en el repositorio F3
1. Abrir la terminal:

    Linux:
    > `Ctrl + Alt + T`

    Windows:
    > `Win + R`

    Type:
    > `cmd.exe`

    Mac:
    > `Command (o Cmd) ⌘`

    > `Shift ⇧`

2. Clonar el repositorio:
    > `git clone https://github.com/ODC-2021/LABS`

3. Cambiarnos a la carpeta del repositorio:
    > `cd LABS/`

4. Actualizar el repositorio (por las dudas):
    > `git pull origin main`

5. Crear una branch con el siguiente formato `apellido1_apellido_2`:
    > `git branch apellido1_apellido_2`

6. Cambiarse a esa branch:
    > `git checkout apellido1_apellido_2`

7. En [LABS.md](LABS.md):
Agregar laboratorio a la lista de `LABS.md` con su información básica, como indica el formato:
    * Titulo del proyecto. *[Opcional]*
    * Integrantes.
    * Descripción general de lo que se ve en pantalla.
    * Algunas imágenes y/o videos de muestra para intrigar al lector.
    * Un link al repositorio o acceso a las instrucciones.

8. Usar uno de los siguientes comandos:

    > `git add LABS.md`

9. Es necesario ahora subir un commit para guardar los cambios:

    > `git commit -m "Nombre del commit"`

10. Pushear a la branch creada:
    > `git push origin apellido_1_apellido2`

11. Usar una de las siguientes opciones para mergear a `main`:
    * Crear una *Pull Request* en GitHub hacia `main` y asignar a `@shirosweets` o `@AgustinMDominguez`
    * Avisar a `@shirosweets` o `@AgustinMDominguez` que la branch fue pusheada para que se realize el merge.

# Errores comunes con Git

## Please tell me who you are
```bash
*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'Pelayo@PELAYO.(none)')
```
### Solución "please tell me who you are"
Si se desea realizar una configuración global (toda la computadora, es decir, todos los repositorios, no recomendado para usuarios con varias cuentas de git):
> `git config --global user.name "Nombre Apellido"`

> `git config --global user.email email@dominio.com`

Si se desea realizar una configuración para cada repositorio:
> `git config user.name "Nombre Apellido"`

> `git config user.email email@dominio.com`
<div align="align">

# Gestión básica de git 
# Rubén Abreu González

### Índice
1. [Configuración](#tarea-configración)
2. [Creación de un repositorio](#tarea-creación-de-un-repositorio)
3. [Comprobar estado del repositorio](#tarea-comprobar-el-estado-del-repositorio)
4. [Realizando Commit´s](#tarea-realizando-commit´s)
5. [Modificación de ficheros](#tarea-modificación-de-ficheros)
6. [Historial](#tarea-historial)

## Tarea: Configración
Configurar Git definiendo el nombre del usuario, el correo electrónico y activar el coloreado de la salida. Mostrar la configuración final.

Operaciones a realizar:
```code
 git config --global user.name "Your-Full-Name"
 git config --global user.email "your-email-address"
 git config --global color.ui auto
 git config --list
```

-  git config --global color.ui auto
- salida:
```
```

- git config --list
- salida:
```code
user.email=rubalba.rag@gmail.com
git config --global user.name rabgonzalez
user.name=rabgonzalez
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
```

## Tarea: Creación de un repositorio
Crear un repositorio nuevo con el nombre dpl y mostrar su contenido.

Operaciones a realizar:
```code:
 mkdir dpl
 cd dpl
 git init
 ls -la
```
- mkdir dpl
- salida:
```
```
- cd dpl
- salida:
```
```

- git init 
- salida:
```code:
ayuda: Usando 'master' como el nombre de la rama inicial. Este nombre de rama predeterminado
ayuda: está sujeto a cambios. Para configurar el nombre de la rama inicial para usar en todos
ayuda: de sus nuevos repositorios, reprimiendo esta advertencia, llama a:
ayuda: 
ayuda: 	git config --global init.defaultBranch <nombre>
ayuda: 
ayuda: Los nombres comúnmente elegidos en lugar de 'master' son 'main', 'trunk' y
ayuda: 'development'. Se puede cambiar el nombre de la rama recién creada mediante este comando:
ayuda: 
ayuda: 	git branch -m <nombre>
Inicializado repositorio Git vacío en /home/dam/rabgonzalez/dpl/.git/
```
- ls -la
- salida:
```code:
total 16
drwxrwxr-x 3 dam dam 4096 oct  4 15:01 .
drwxrwxr-x 4 dam dam 4096 oct  4 15:00 ..
drwxrwxr-x 7 dam dam 4096 oct  4 15:01 .git
-rw-rw-r-- 1 dam dam 1546 oct  4 15:01 README.md
```

## Tarea: Comprobar el estado del repositorio
- Comprobar el estado del repositorio.

-  Crear un fichero indice.txt con el siguiente contenido:
    - Capítulo 1: Instalación de Git por el alumno XXX (donde XXX es el nombre del alumno)
    - Capítulo 2: Flujo de trabajo básico

- Comprobar de nuevo el estado del repositorio.

- Añadir el fichero a la zona de intercambio temporal.

- Volver a comprobar una vez más el estado del repositorio.

- git status
- salida:
```code:
En la rama master

No hay commits todavía

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)
	README.md

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)
```

- cat > indice.txt 
"Capítulo 1: Instalación de Git por el alumno XXX
Capítulo 2: Flujo de trabajo básico"
Ctr+D

- salida:
```
```

- git status
- salida:
```code:
En la rama master

No hay commits todavía

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)
	README.md
	indice.txt

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)
```
- git add indice.txt
- salida:
```
```

- git status
- salida:
```code
n la rama master

No hay commits todavía

Cambios a ser confirmados:
  (usa "git rm --cached <archivo>..." para sacar del área de stage)
	nuevos archivos: indice.txt

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)
	README.md
```

## Tarea: Realizando Commit´s
Realizar un commit de los últimos cambios con el mensaje Añadido índice de la asignatura DPL. y ver el estado del repositorio.

- git commit -m "Añadido índice de la asignatura DPL."
- salida:
```code
[master (commit-raíz) 5b20334] Añadido índice de la asignatura DPL.
1 file changed, 2 insertions(+)
create mode 100644 indice.txt
```

- git status
- salida:
```code
En la rama master
Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)
	README.md

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)
```

## Tarea: Modificación de ficheros
- Cambiar el fichero indice.txt para que contenga lo siguiente:
    - Capítulo 1: Instalación de Git por el alumno XXX (donde XXX es el nombre del alumno)
    - Capítulo 2: Flujo de trabajo básico
    - Capítulo 3: Gestión de ramas
    - Capítulo 4: Repositorios remotos
- Mostrar los cambios con respecto a la última versión guardada en el repositorio.
- Hacer un commit de los cambios con el mensaje Añadido los capitulos 3 y 4.

- cat > indice.txt
"Capítulo 1: Instalación de Git por el alumno XXX _(donde XXX es el nombre del alumno)_ Capítulo 2: Flujo de trabajo básico
Capítulo 3: Gestión de ramas
Capítulo 4: Repositorios remotos"
Ctrl+D

- salida
```
```

- git diff
- salida:
```code
Capítulo 1: Instalación de Git por el alumno XXX _(donde XXX es el nombre del alumno)_
Capítulo 2: Flujo de trabajo básico
Capítulo 3: Gestión de ramas
Capítulo 4: Repositorios remotos
```

- git add indice.txt
- salida:
```
```

- git commit -m "Añadido los capitulos 3"
- salida:
```code
[master 1246bda] Añadido los capitulos 3
 1 file changed, 3 insertions(+), 1 deletion(-)
```

## Tarea: Historial
- Mostrar los cambios de la última versión del repositorio con respecto a la anterior.
- Cambiar el mensaje del último commit por Añadido el capitulo sobre gestión de ramas al índice.
- Volver a mostrar los últimos cambios del repositorio.

- git show
- salida:
```code
commit 1246bda6ca7d44b515c3d437e3bff249fb1ac9df (HEAD -> master)
Author: rabgonzalez <rubalba.rag@gmail.comgit config --global user.name rabgonzalez>
Date:   Wed Oct 4 15:36:01 2023 +0100

    Añadido los capitulos 3

diff --git a/indice.txt b/indice.txt
index d4e5bff..4f799e7 100644
--- a/indice.txt
+++ b/indice.txt
@@ -1,2 +1,4 @@
-Capítulo 1: Instalación de Git por el alumno XXX
+Capítulo 1: Instalación de Git por el alumno XXX _(donde XXX es el nombre del alumno)_
 Capítulo 2: Flujo de trabajo básico
+Capítulo 3: Gestión de ramas
+Capítulo 4: Repositorios remotos
\ No newline at end of file
```

- git commit --amend -m "Añadido el capitulo sobre gestión de ramas al índice"
- salida:
```code
[master 499d493] Añadido el capitulo sobre gestion de ramas al indice
 Date: Wed Oct 4 15:36:01 2023 +0100
 1 file changed, 3 insertions(+), 1 deletion(-)
```

- git show
- salida:
```code
commit 499d493ea66d6de5923846f3a69b060e5587bfa8 (HEAD -> master)
Author: rabgonzalez <rubalba.rag@gmail.comgit config --global user.name rabgonzalez>
Date:   Wed Oct 4 15:36:01 2023 +0100

    Añadido el capitulo sobre gestion de ramas al indice

diff --git a/indice.txt b/indice.txt
index d4e5bff..4f799e7 100644
--- a/indice.txt
+++ b/indice.txt
@@ -1,2 +1,4 @@
-Capítulo 1: Instalación de Git por el alumno XXX
+Capítulo 1: Instalación de Git por el alumno XXX _(donde XXX es el nombre del alumno)_
 Capítulo 2: Flujo de trabajo básico
+Capítulo 3: Gestión de ramas
+Capítulo 4: Repositorios remotos
\ No newline at end of file
```
</div>



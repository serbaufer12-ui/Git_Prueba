# Practica Guiada de Git

* **Modulo:** Afondamento nas competencias profesionais
* **Ciclo:** DAM (2º Curso)
* **Alumno:** Sergio F. B.
* **Repositorio:** `prueba_git`


## Paso 1: Creacion directorios con los distintos archivos

Se navega al escritorio, se crear la carpeta y se accede a la carpeta del proyecto `prueba_git`:

```bash

Sergio F.B@DESKTOP-G0V6A3S MINGW64 /
$ cd ~/Desktop

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop
$ mkdir prueba_git

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop
$ cd prueba_git

```

`mkdir` crea la carpeta, `cd` entra a ella .


## Paso 1.1: Cambiar nombre de la rama

```bash

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (master)
$ git branch -m main

```

`-m` renombra la rama ; Aqui pasamos de master a main.


### 1.2. Creacion de archivos de texto iniciales

Se crea el archivo `texto.txt`, `nano` abre el editor;

```bash

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ nano texto.txt

```

### 1.3. Creacion del script de automatizacionn
Se crea el archivo `script.sh` :

```bash
Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ nano script.sh

```

### 1.4. iniiciar repositorio GIT

Crea la carpeta `.git` donde git guarda todo el historial del proyecto.

```bash
Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git
$ git init
Initialized empty Git repository in C:/Users/Sergio F.B/Desktop/prueba_git/.git/

```


### 1.5. Ver el estado del repositorio en git

1. Vale vemos el archivo script.sh esta en zona de preparacion. Ya se ejecuto ``git add`, se incluira en el comit.

2. Untracked files = Texto.txt y la carpeta del Markdown_git, git sabe que estan pero todavia no los sigue


``` bash
Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   script.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Markdown_git/
        texto.txt

```

### 1.6. Añadir y confirmar ARCHIVOS del proyecto

Que hacemos; `git add` pasa el archivo al area de preparacion y `git commit` guarda esa preparaciom. Al final hacemos el `git status` que nos dice que queda la carpeta del Markdown que no vamos a tocar.

```bash

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git add texto.txt
warning: in the working copy of 'texto.txt', LF will be replaced by CRLF the next time Git touches it

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   script.sh
        new file:   texto.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Markdown_git/


Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git commit -m "Confirmacion Inicial"
[main (root-commit) d3f28f8] Confirmacion Inicial
 2 files changed, 5 insertions(+)
 create mode 100644 script.sh
 create mode 100644 texto.txt


Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Markdown_git/

nothing added to commit but untracked files present (use "git add" to track)


```

**Modificar archivo**

Git lo detecta pero no lo prepara para el commit

```bash
Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ nano texto.txt

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   texto.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Markdown_git/

no changes added to commit (use "git add" and/or "git commit -a")

```

### 2.1. Añadir los cambios

Que hacemos: modificamos el texto con el `nano` , hacemos el `git status` y observamos que 
esta en modo untracked y luego hacemos el `git add` pasa el archivo al area de preparacion y `git commit` guarda esa preparacion. Al final hacmos el `git status` que nos dice que queda la carpeta del Markdown que no vamos a tocar.

```bash

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ nano texto.txt

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   texto.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   texto.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Markdown_git/


Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git add texto.txt
warning: in the working copy of 'texto.txt', LF will be replaced by CRLF the next time Git touches it

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git commit -m "Aplicado el cambio"
[main 1ed2e91] Aplicado el cambio
 1 file changed, 5 insertions(+), 3 deletions(-)

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$


Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Markdown_git/

nothing added to commit but untracked files present (use "git add" to track)

```

**Ver la informacion sobre la ultima version**

Muestra el ultimo commit: autor, fecha, mensaje y los cambios realizados.



```bash

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git show
commit 1ed2e91fceb3fe93fda301eb03b943b994bf8c1d (HEAD -> main)
Author: Sergio <serbaufer12@gmail.com>
Date:   Fri Oct 30 10:31:50 2026 +0100

    Aplicado el cambio

diff --git a/texto.txt b/texto.txt
index 15bf608..ffee70a 100644
--- a/texto.txt
+++ b/texto.txt
@@ -1,3 +1,5 @@
-uno
-dos
-tres
+1uno
+2dos
+3tres
+PEDRO
+Hola

```
**Ver el Historial**

Lista los commits, del más reciente al más antiguo, con su identificador - HAST -.


```bash

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git log
commit 1ed2e91fceb3fe93fda301eb03b943b994bf8c1d (HEAD -> main)
Author: Sergio <serbaufer12@gmail.com>
Date:   Fri Oct 30 10:31:50 2026 +0100

    Aplicado el cambio

commit d3f28f8e68d8c79f56945a7b71bd0f0dfd8e4341
Author: Sergio <serbaufer12@gmail.com>
Date:   Fri Oct 30 10:23:41 2026 +0100

    Confirmacion Inicial


```

**Ver los cambios sin confirmar**

Lo que observamos con el `git show` vemos que no se miran los cambios, encambio si utilizamos el `git diff` si podemos verlo aun sin estar en el commit. (`+uepaaaa`)

```bash
Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ nano texto.txt

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git show
commit 1ed2e91fceb3fe93fda301eb03b943b994bf8c1d (HEAD -> main)
Author: Sergio <serbaufer12@gmail.com>
Date:   Fri Oct 30 10:31:50 2026 +0100

    Aplicado el cambio

diff --git a/texto.txt b/texto.txt
index 15bf608..ffee70a 100644
--- a/texto.txt
+++ b/texto.txt
@@ -1,3 +1,5 @@
-uno
-dos
-tres
+1uno
+2dos
+3tres
+PEDRO
+Hola



Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git diff
warning: in the working copy of 'texto.txt', LF will be replaced by CRLF the next time Git touches it
diff --git a/texto.txt b/texto.txt
index ffee70a..e22165e 100644
--- a/texto.txt
+++ b/texto.txt
@@ -3,3 +3,4 @@
 3tres
 PEDRO
 Hola
+uepaaaa

```

**Ignorar Archivos**

*Lo que hacemos*: `.gitignore` indica qué archivos debe ignorar Git.
En git status no aparece temporal~ porque se ignora; importante~ sí aparece como untracked.

```bash

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ nano .gitignore

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ nano texto.txt

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ nano temporal~

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ ls -a
./  ../  .git/  .gitignore  Markdown_git/  script.sh  temporal~  texto.txt


Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)
$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   texto.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        importante~
        Hola.java
        Markdown_git/

no changes added to commit (use "git add" and/or "git commit -a")

Sergio F.B@DESKTOP-G0V6A3S MINGW64 ~/Desktop/prueba_git (main)

```

**Confirmar datos**


```bash 



```
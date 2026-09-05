# Práctica Guiada: Git, GitHub y VS Code

Bienvenido/a a tu espacio de trabajo para la práctica de Git. Este repositorio ha sido creado para ti a través de Classroom 50.

El objetivo de esta práctica es doble:
1.  Aprender el ciclo de vida completo de un proyecto que nace en tu ordenador y se sube a la nube (`init` -> `commit` -> `push`).
2.  Aprender el flujo de trabajo estándar para unirte a un proyecto ya existente, como este (`clone` -> `commit` -> `sync`).

---

## Parte 1: Creando un Proyecto desde Cero (Sandbox)

En esta primera parte, vamos a simular la creación de un proyecto desde la nada. Trabajaremos en una carpeta temporal en tu ordenador, un **entorno de pruebas o sandbox**, para entender los comandos fundamentales.

#### Paso 1: Crear la carpeta de pruebas

Abre un terminal (Git Bash en Windows, Terminal en Mac/Linux). Un buen lugar es el Escritorio.

```bash
# Navega al Escritorio (o donde quieras crear la carpeta)
cd ~/Desktop

# Crea la carpeta y entra en ella
mkdir mi-proyecto-sandbox
cd mi-proyecto-sandbox
```

#### Paso 2: Iniciar el repositorio y configurar tu identidad

Ahora, convertiremos esta carpeta en un repositorio de Git y le diremos a Git quién eres.

```bash
# Inicia el repositorio. Esto crea la carpeta oculta .git
git init

# Configura tu nombre de usuario y email (usa el mismo email de GitHub)
git config --global user.name "Tu Nombre de Usuario"
git config --global user.email "tu-email@ejemplo.com"
```

#### Paso 3: Abrir el proyecto en VS Code y hacer el primer commit

1.  Abre una **nueva ventana** de VS Code y ve a `Archivo > Abrir Carpeta...` para abrir `mi-proyecto-sandbox`.
2.  Crea un archivo, por ejemplo `idea.txt`, y escribe cualquier cosa, como "Mi primera idea de proyecto."
3.  Ve a la pestaña de **Control de Código Fuente** (Source Control).
4.  Haz **"Stage"** (`+`) en el archivo `idea.txt`.
5.  Escribe el mensaje de commit `feat: Añade la idea inicial del proyecto` y haz **"Commit"** (✔️).

#### Paso 4: Publicar tu proyecto "Sandbox" en GitHub

Ahora vamos a subir este proyecto local a un nuevo repositorio en tu cuenta de GitHub.

1.  Ve a tu cuenta de GitHub en el navegador y crea un **nuevo repositorio**.
2.  Llámalo `mi-proyecto-sandbox`.
3.  **Importante:** Déjalo **vacío**. No lo inicialices con un README ni otros archivos.
4.  Copia la URL **HTTPS** que te proporciona GitHub.
5.  Vuelve a VS Code (a la ventana de `mi-proyecto-sandbox`) y abre el terminal integrado.
6.  Ejecuta `git remote add origin <URL-HTTPS>` y sustituye `<URL-HTTPS>` por la URL que copiaste.
7.  Ejecuta `git push -u origin main`. Si tu rama inicial se llama `master`, usa `git push -u origin master`.



> _**Pro-Tip:** El botón "Publish to GitHub" de VS Code puede crear el repositorio remoto y subir el código en un solo paso. Para esta primera práctica, se usa el terminal para ver claramente cómo se conecta un repositorio local a uno remoto mediante su URL._


---

## Parte 2: El Flujo de Trabajo Real - El Proyecto de Estadísticas

Ahora, vamos a trabajar como lo harías _uniéndote_ a un proyecto que ya existe. **Este mismo repositorio en el que estás leyendo estas instrucciones es tu proyecto para la Parte 2.**

#### Paso 5: Clonar el repositorio de la práctica

1.  Cierra la carpeta del sandbox en VS Code y abre una **ventana nueva y vacía**.
2.  Ve a la pestaña de **Control de Código Fuente** y haz clic en **"Clone Repository"**.
3.  Pega la URL HTTPS de **ESTE** repositorio (la puedes encontrar en su página principal en GitHub, bajo el botón verde "<> Code").
4.  Elige una carpeta en tu ordenador donde guardarlo (ej. `Documentos/Practica-Git-Estadisticas`).

Ya tienes el proyecto de la práctica en tu ordenador, listo para trabajar.

#### Paso 6: Configurar el `.gitignore`

Todo proyecto profesional necesita especificar qué archivos deben ser ignorados por Git.

1.  En el explorador de archivos de VS Code, crea un nuevo archivo llamado `.gitignore`.
2.  Pega el siguiente contenido dentro:
    ```
    # Byte-compiled / optimized / DLL files
    __pycache__/
    *.pyc
    
    # Virtual environment
    venv/
    .venv/
    ```
3.  Guarda el archivo, ve a la pestaña de **Control de Código Fuente**, haz **"Stage"** (`+`) y **"Commit"** con el mensaje: `chore: Configura .gitignore para Python`.

Utilizaremos más adelante alguna de las plantillas preconfiguradas que se encuentran en GitHub.

#### Paso 7: Crear la estructura de archivos

1.  Crea el archivo `main.py` y el archivo `datos.txt`.
2.  Añade una serie de enteros al archivo `datos.txt`, como, por ejemplo:
    ```
    10
    25
    15
    30
    20
    ```
3.  Haz **"Stage"** de **ambos** archivos, y haz un único **"Commit"** con el mensaje: `feat: Crea la estructura inicial del proyecto con main.py y datos.txt`.

#### Paso 8: Implementar la función de lectura

Abre `main.py` y añade el esqueleto de la función. El objetivo es que la implementes tú.

```python
# main.py

def leer_datos(fichero):
    """Lee números enteros de un fichero, uno por línea."""
    # Tu código aquí
    pass

if __name__ == "__main__":
    # Tu código para visualizar la lista de valores leídos aquí
    pass
```
Una vez implementada, haz **"Stage"** y **"Commit"** con el mensaje: `feat: Implementa la función de lectura de datos`.

#### Paso 9: Implementar los cálculos estadísticos

Modifica `main.py` para añadir la nueva función y las llamadas correspondientes.

```python
# main.py (esqueleto final)
import statistics

def leer_datos(fichero):
    """Lee números enteros de un fichero, uno por línea."""
    # Tu código aquí
    pass

def calcular_estadisticas(numeros):
    """Calcula la media y la mediana de una lista de números."""
    # Tu código aquí
    pass

if __name__ == "__main__":
    """
    Tu código aquí para:
    1. Leer los datos.
    2. Visualizar la lista de valores leídos.
    3. Calcular las estadísticas.
    4. Mostrar la media y la mediana.
    """
    pass
```

Cuando lo tengas funcionando, haz **"Stage"** y **"Commit"** con el mensaje: `feat: Añade cálculo de media y mediana`.

#### Paso 10: Sincronizar tu trabajo con GitHub

Has estado guardando todos tus cambios (commits) en tu ordenador. Es hora de subirlos a tu repositorio en la nube para tener una copia de seguridad.

1.  Ve a la esquina inferior izquierda de VS Code.
2.  Haz clic en el botón **"Synchronize Changes"** (🔄). Esto subirá todos tus commits a GitHub.

---

## Parte 3: El Ciclo de Sincronización Completo

Hasta ahora, solo has "subido" (`push`) cambios de tu ordenador a la nube. Pero el trabajo real implica también "bajar" (`pull`) los cambios que se hagan en el repositorio remoto.

Vamos a simular esto mejorando nuestro archivo `.gitignore` directamente desde la web de GitHub.

#### Paso 11: Actualizar el `.gitignore` con la plantilla profesional de GitHub

Nuestro `.gitignore` actual es muy simple. Vamos a reemplazarlo por la plantilla oficial de GitHub, que es mucho más completa.

1.  Abre tu navegador y ve a la página de **tu repositorio de la práctica** en GitHub, creado al aceptar la asignación de Classroom.
2.  Busca el archivo `.gitignore` en la lista de archivos y haz clic en él para abrirlo.
3.  En la esquina superior derecha del visor del archivo, haz clic en el icono del lápiz (✏️ **"Edit this file"**).
4.  **Borra todo el contenido** que pusimos al principio.
5.  Abre la plantilla oficial de Python en el repositorio `github/gitignore`: `https://github.com/github/gitignore/blob/main/Python.gitignore`.
6.  Copia el contenido de esa plantilla y pégalo en tu `.gitignore`, reemplazando el contenido anterior.
7.  Baja hasta el final de la página. En el cuadro de mensaje del commit, escribe algo como `chore: Actualiza .gitignore a la plantilla oficial de Python`.
8.  Haz clic en el botón verde **"Commit changes"**.

¡Perfecto! Acabas de hacer un cambio directamente en la nube. Tu repositorio en GitHub ahora está **un commit por delante** del que tienes en tu ordenador.

#### Paso 12: Sincronizar el cambio de vuelta a tu ordenador

Tu VS Code aún no sabe que ha habido un cambio en GitHub. Vamos a actualizarlo.

1.  Vuelve a VS Code.
2.  Ve a la esquina inferior izquierda y haz clic de nuevo en el botón **"Synchronize Changes"** (🔄).
3.  Fíjate que ahora, junto al icono, puede aparecer una flecha hacia abajo **(↓)**, indicando que hay cambios para descargar.
4.  Al hacer clic, VS Code se comunicará con GitHub, descargará el nuevo commit (`git pull`) y actualizará tus archivos locales.
5.  **Verifica el resultado:** Abre el archivo `.gitignore` en VS Code. Deberías ver que su contenido ha cambiado y ahora es mucho más largo y completo, coincidiendo con el que acabas de guardar en la web.

> _**Concepto Clave:** Acabas de completar el ciclo de trabajo fundamental. Antes de empezar a trabajar, siempre "sincronizas" para bajar los cambios de la nube (de tus compañeros o tuyos desde otro ordenador). Luego trabajas en local y, al terminar, vuelves a sincronizar para subir tus contribuciones._

---

### Entrega de la Práctica

La práctica se considerará entregada cuando todo tu trabajo (los commits con los archivos `.gitignore`, `main.py` y `datos.txt`) esté subido a **este repositorio** antes de la fecha límite.

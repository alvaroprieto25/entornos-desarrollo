# PRÁCTICA INICIACIÓN A GIT Y GITHUB

## 1. Descargar Git y Python (si no están instalados)

1. **Git**: Descarga e instala Git desde [https://git-scm.com/](https://git-scm.com/).
   - Sigue las instrucciones según el sistema operativo (Windows, macOS o Linux).
   - Al instalarlo, selecciona **Git Bash** como terminal de uso.
  
2. **Python**: Descarga e instala Python desde [https://www.python.org/](https://www.python.org/).
   - Asegúrate de marcar la opción para **Agregar Python al PATH** durante la instalación.

## 2. Crear una cuenta en GitHub

1. Dirígete a [https://github.com/](https://github.com/) y regístrate si aún no tienes una cuenta.
2. Sigue los pasos de verificación y personalización de tu perfil.

## 3. Clonar el repositorio

1. **Abre Git Bash** y navega a la carpeta donde quieras clonar el repositorio.
2. Ejecuta el siguiente comando para clonar el proyecto:
   ```bash
   git clone https://github.com/alvaroprieto25/entornos_desarrollo.git
   ```
3. **Explicación**:
   - El comando `git clone` crea una copia completa del repositorio en tu computadora.
   - Ahora tendrás una carpeta llamada `entornos_desarrollo` con el contenido del proyecto.

## 4. Verificar si el repositorio está actualizado (git pull)

1. Cambia al directorio del proyecto clonado:
   ```bash
   cd entornos_desarrollo
   ```
2. Ejecuta el comando `git pull` para asegurarte de que el proyecto está actualizado:
   ```bash
   git pull
   ```

   **¿Por qué hacer `git pull`?**
   - `git pull` actualiza tu copia local con los cambios más recientes en GitHub.
   - Esto es importante porque otros miembros del equipo pueden haber hecho cambios y los subieron (push) al repositorio remoto, y al hacer `pull` te aseguras de que tienes la última versión antes de realizar tus propios cambios.

## 5. Realizar cambios en el archivo y hacer tu primer commit

1. Abre el archivo que está en el proyecto. Realiza algún cambio sencillo, como agregar una línea o un comentario en el código.
2. Guarda el archivo.
3. En Git Bash, asegúrate de estar en el directorio del proyecto (`entornos_desarrollo`).

### Paso a paso para hacer tu primer commit:

1. **Ver el estado de los cambios**:
   ```bash
   git status
   ```
   - Esto muestra los archivos que has modificado y te ayuda a verificar que Git ha detectado los cambios.

2. **Agregar los cambios al área de preparación (staging area)**:
   ```bash
   git add nombre_del_archivo
   ```
   - Sustituye `nombre_del_archivo` por el nombre real del archivo modificado.
   - También puedes usar `git add .` para añadir todos los cambios en el directorio actual.

3. **Hacer el commit con un mensaje**:
   ```bash
   git commit -m "Mensaje descriptivo de los cambios realizados"
   ```
   - Por ejemplo: `git commit -m "Agregué un comentario en el archivo principal"`

4. **Enviar los cambios a GitHub**:
   ```bash
   git push origin main
   ```
   - Esto envía tu commit al repositorio en GitHub.
   - Es probable que necesites ingresar tus credenciales de GitHub la primera vez (nombre de usuario y token).

## 6. Posibles conflictos al hacer push (cómo resolverlos)

Si otros compañeros han hecho cambios y los han subido (push) antes que tú, podrías encontrarte con un mensaje de error al intentar hacer `git push`. Esto es un conflicto porque tu copia local está desactualizada.

### Pasos para resolver el conflicto:

1. **Haz un `git pull` para obtener los cambios más recientes del repositorio**:
   ```bash
   git pull origin main
   ```
   - Si no hay conflictos, Git combinará los cambios automáticamente.
   - Si hay conflictos, verás una lista de archivos con conflictos y necesitarás resolverlos manualmente.

2. **Resolver el conflicto manualmente**:
   - Abre los archivos con conflicto. Verás que las áreas en conflicto están marcadas así:
     ```plaintext
     <<<<<<< HEAD
     (tus cambios aquí)
     =======
     (cambios en el repositorio remoto)
     >>>>>>> nombre_del_commit_remoto
     ```
   - Decide qué cambios quieres conservar. Puedes optar por tus cambios, los cambios del repositorio remoto o una combinación de ambos.
   - Elimina las marcas `<<<<<<<`, `=======` y `>>>>>>>` después de resolver los conflictos y guarda el archivo.

3. **Agrega los archivos resueltos al área de preparación**:
   ```bash
   git add nombre_del_archivo
   ```

4. **Realiza un nuevo commit para los cambios que resolvieron el conflicto**:
   ```bash
   git commit -m "Resolví conflictos en nombre_del_archivo"
   ```

5. **Intenta hacer push de nuevo**:
   ```bash
   git push origin main
   ```

   - Si has resuelto todos los conflictos correctamente, el comando `push` debería funcionar sin problemas y tus cambios estarán en GitHub.
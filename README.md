# [STUDIUM 360]

## Sec [01] - Grupo N° [05]

### Integrantes

| Nombre                           | Carnet        |
| -------------------------------- | ------------- |
| DIEGO EDUARDO CASTRO QUINTANILLA | 00117322      |
| ALISON ARACELY ARGUETA FLORES    | 00076422      |
| CRISTOFER RICARDO DIAZ ALFARO    | 00071222      |


# Documentación de la API

# Curso API

## Descripción
Esta API permite la gestión de cursos y recursos asociados a los cursos.

## URL Base
`/api/cursos`

### 1. Guardar un nuevo curso

- **URL**: `/`
- **Método HTTP**: POST
- **Cuerpo**: Datos del curso a guardar en formato JSON
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 201: Curso creado exitosamente. Respuesta en formato JSON con los detalles del nuevo curso.
    - Código 400: Error de validación o formato en el cuerpo de la solicitud. Respuesta en formato JSON con un mensaje de error.

### 2. Obtener todos los cursos sin incluir los recursos

- **URL**: `/`
- **Método HTTP**: GET
- **Cuerpo**: No se requiere cuerpo
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Éxito. Respuesta en formato JSON con la lista de cursos.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error.

### 3. Obtener cursos con paginación

- **URL**: `/?page=<número>&limit=<número>`
- **Método HTTP**: GET
- **Cuerpo**: No se requiere cuerpo
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Éxito. Respuesta en formato JSON con la lista de cursos paginados, el total de cursos, el número total de páginas y más detalles.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error.

### 4. Buscar un curso por su ID

- **URL**: `/<id>`
- **Método HTTP**: GET
- **Cuerpo**: No se requiere cuerpo
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Éxito. Respuesta en formato JSON con los detalles del curso encontrado.
    - Código 404: Curso no encontrado. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error.

### 5. Eliminar un curso por su ID

- **URL**: `/<id>`
- **Método HTTP**: DELETE
- **Cuerpo**: No se requiere cuerpo
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Curso eliminado exitosamente. Respuesta en formato JSON con un mensaje de éxito.
    - Código 404: Curso no encontrado. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error.

### 6. Filtrar cursos por materia

- **URL**: `/filtrar-por-materia`
- **Método HTTP**: POST
- **Cuerpo**: Datos de la materia a buscar en formato JSON
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Éxito. Respuesta en formato JSON con la lista de cursos que coinciden con la materia especificada.
    - Código 400: Error de validación o formato en el cuerpo de la solicitud. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error.

### 7. Filtrar cursos por nombre

- **URL**: `/filtrar-por-nombre`
- **Método HTTP**: POST
- **Cuerpo**: Datos del nombre a buscar en formato JSON
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Éxito. Respuesta en formato JSON con la lista de cursos que coinciden con el nombre especificado.
    - Código 400: Error de validación o formato en el cuerpo de la solicitud. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error.

### 8. Añadir un recurso a un curso específico

- **URL**: `/<id>/recursos`
- **Método HTTP**: POST
- **Cuerpo**: Datos del recurso a añadir en formato JSON
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 201: Recurso añadido exitosamente al curso. Respuesta en formato JSON con los detalles actualizados del curso.
    - Código 404: Curso no encontrado. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error.

### 9. Actualizar un recurso específico de un curso

- **URL**: `/<cursoId>/recursos/<resourceId>`
- **Método HTTP**: PUT
- **Cuerpo**: Datos del recurso actualizado en formato JSON
- **Cabeceras**:

# Tutorados API 

## Descripción
Esta API permite gestionar los tutorados en un curso.

## URL Base
`/api/cursos/:cursoId/tutorados`

## Métodos

### 1. Guardar un nuevo tutorado en un curso

- **URL**: `/:username`
- **Método HTTP**: POST
- **Cuerpo**: Datos del tutorado a agregar en formato JSON
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 201: Tutorado agregado exitosamente al curso. Respuesta en formato JSON con los detalles actualizados del curso.
    - Código 400: Error de validación o formato en el cuerpo de la solicitud. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error en caso de fallo en la operación.

### 2. Obtener todos los tutorados de un curso

- **URL**: `/`
- **Método HTTP**: GET
- **Cuerpo**: No se requiere cuerpo
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Éxito. Respuesta en formato JSON con la lista de tutorados del curso.
    - Código 404: Curso no encontrado. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error en caso de fallo en la operación.

### 3. Eliminar un tutorado de un curso

- **URL**: `/:username`
- **Método HTTP**: DELETE
- **Cuerpo**: No se requiere cuerpo
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Tutorado eliminado exitosamente del curso. Respuesta en formato JSON con un mensaje de éxito.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error en caso de fallo en la operación.

### 4. Obtener los nombres de usuario de todos los tutorados de un curso

- **URL**: `/usernames`
- **Método HTTP**: GET
- **Cuerpo**: No se requiere cuerpo
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Éxito. Respuesta en formato JSON con los nombres de usuario de todos los tutorados del curso.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error en caso de fallo en la operación.

# Autenticacion API 

Esta API proporciona endpoints para el registro de usuarios y el inicio de sesión de usuarios existentes. 

## Endpoints

### Registro de Usuario

- **URL:** `/api/register`
- **Método:** `POST`
- **Cuerpo de la Solicitud (JSON):**
  - `username` (string): Nombre de usuario.
  - `password` (string): Contraseña del usuario.
  - `nombre` (string): Nombre del usuario.
  - `tipo` (string): Tipo de usuario.
  - `imagen` (string): URL de la imagen del usuario.
- **Respuestas:**
  - Código HTTP 201 (Éxito):
    ```json
    {
        "user_id": "ID_DEL_USUARIO"
    }
    ```
  - Código HTTP 400 (Error de Solicitud):
    ```json
    {
        "error": "Bad Request"
    }
    ```
  - Código HTTP 500 (Error Interno del Servidor):
    ```json
    {
        "error": "Internal Server Error"
    }
    ```

### Inicio de Sesión

- **URL:** `/api/login`
- **Método:** `POST`
- **Cuerpo de la Solicitud (JSON):**
  - `id` (string): Nombre de usuario o correo electrónico.
  - `password` (string): Contraseña del usuario.
- **Respuestas:**
    ```
  - Código HTTP 401 (Error de Autenticación):
    ```json
    {
        "error": "Incorrect Password"
    }
    ```
  - Código HTTP 404 (Usuario no Encontrado):
    ```json
    {
        "error": "User not found"
    }
    ```
  - Código HTTP 500 (Error Interno del Servidor):
    ```json
    {
        "error": "Internal Server Error"
    }
    ```

## Uso

1. **Registro de Usuario:** Envía una solicitud `POST` a `/api/register` con los datos del usuario en el cuerpo de la solicitud. Si el registro es exitoso, recibirás el ID del usuario.

2. **Inicio de Sesión:** Envía una solicitud `POST` a `/api/login` con las credenciales de inicio de sesión en el cuerpo de la solicitud. Si las credenciales son correctas, recibirás un token de acceso que puedes usar para autenticarte en otras partes de la aplicación.

## Autenticación

Para acceder a rutas protegidas en tu aplicación, incluye el token de acceso en la cabecera de la solicitud HTTP utilizando el encabezado `Authorization`. Por ejemplo:

# Usuarios API

## Descripción
Esta API permite realizar operaciones relacionadas con los usuarios, como obtener información de usuarios, filtrar usuarios por nombre, actualizar perfiles, agregar y eliminar materias de interés, y eliminar usuarios.

## URL Base
`/api/usuarios`

## Métodos

### 1. Obtener todos los usuarios

- **URL**: `/`
- **Método HTTP**: GET
- **Cuerpo**: No se requiere cuerpo
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Éxito. Respuesta en formato JSON con la lista de usuarios.
    - Código 404: Usuarios no encontrados. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error en caso de fallo en la operación.

### 2. Filtrar usuarios por nombre

- **URL**: `/filtrar`
- **Método HTTP**: POST
- **Cuerpo**: Datos para filtrar usuarios por nombre en formato JSON.
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Éxito. Respuesta en formato JSON con la lista de usuarios que coinciden con el filtro.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error en caso de fallo en la operación.

### 3. Añadir una nueva materia de interés a un usuario

- **URL**: `/:userId/materia`
- **Método HTTP**: POST
- **Cuerpo**: Datos de la materia de interés a agregar en formato JSON.
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 201: Materia de interés agregada exitosamente al usuario. Respuesta en formato JSON con la lista actualizada de materias de interés del usuario.
    - Código 404: Usuario no encontrado. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error en caso de fallo en la operación.

### 4. Obtener el perfil de un usuario por ID

- **URL**: `/:userId/perfil`
- **Método HTTP**: GET
- **Cuerpo**: No se requiere cuerpo
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Éxito. Respuesta en formato JSON con el perfil del usuario.
    - Código 404: Usuario no encontrado. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error en caso de fallo en la operación.

### 5. Actualizar el perfil de un usuario

- **URL**: `/:userId/perfil`
- **Método HTTP**: PUT
- **Cuerpo**: Datos actualizados del perfil del usuario en formato JSON.
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Perfil de usuario actualizado exitosamente. Respuesta en formato JSON con el perfil actualizado del usuario.
    - Código 404: Usuario no encontrado. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error en caso de fallo en la operación.

### 6. Eliminar una materia de interés de un usuario

- **URL**: `/:userId/materia/:materiaId`
- **Método HTTP**: DELETE
- **Cuerpo**: No se requiere cuerpo
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Materia de interés eliminada exitosamente del usuario. Respuesta en formato JSON con un mensaje de éxito.
    - Código 404: Usuario no encontrado. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error en caso de fallo en la operación.

### 7. Eliminar un usuario por ID

- **URL**: `/:userId`
- **Método HTTP**: DELETE
- **Cuerpo**: No se requiere cuerpo
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Usuario eliminado exitosamente. Respuesta en formato JSON con un mensaje de éxito.
    - Código 404: Usuario no encontrado. Respuesta en formato JSON con un mensaje de error.
    - Código 500: Error interno del servidor. Respuesta en formato JSON con un mensaje de error en caso de fallo en la operación.



# Correo Electrónico API

## Descripción
Esta API permite enviar correos electrónicos a través de un servicio de correo electrónico configurado en la aplicación.

## URL Base
`/api/correo`

## Métodos

### 1. Enviar un correo electrónico

- **URL**: `/enviar`
- **Método HTTP**: POST
- **Cuerpo**: Datos del correo electrónico a enviar en formato JSON, que incluye destinatarios, asunto y mensaje.
- **Cabeceras**: No se requieren cabeceras específicas
- **Respuestas**:
    - Código 200: Correo enviado exitosamente. Respuesta en formato de texto con un mensaje de éxito.
    - Código 500: Error interno del servidor. Respuesta en formato de texto con un mensaje de error en caso de fallo en el envío del correo.

**********************************

# Guía de Instalación para Studium 
Esta guía proporciona las instrucciones necesarias para realizar una correcta instalación del trabajo de manera local.

# Requisitos Previos
Asegurarse que en el dispositivo donde desea utilizar el proyecto posea los siguientes componentes: 
-*Node.js*
-*Yarn*
-*Sistema Operativo: Linux*

# Pasos de instalación
# Paso 1
Clonar el repositorio del proyecto utilizando “git clone https://github.com/Programacion-Web-02-2023/proyecto-equipo-05-sec-01-grupo-05.git”

# Paso 2
Acceder al directorio del proyecto e instalar las dependencias enumeradas a continuación, asumiendo que ya posee una versión de yarn en su dispositivo se utiliza “yarn install” seguido de su respectivo nombre:

-**2.1. Axios**
Biblioteca popular de JavaScript para realizar peticiones HTTP desde el navegador o Node.js. Proporciona una interfaz simple para realizar solicitudes HTTP, admite promesas y puede ser utilizado tanto en el lado del cliente como en el servidor; utilizado para realizar solicitudes a API y servicios web.

-**2.2 jwt-decode**
Biblioteca que decodifica tokens JSON Web (JWT) en el lado del cliente. Los tokens JWT son comúnmente utilizados para la autenticación y contienen información sobre el usuario. jwt-decode facilita la decodificación de estos tokens y la obtención de la información contenida en ellos.

-**2.3 React-router**
Biblioteca para la navegación en aplicaciones React. Permite la creación de rutas en una aplicación de una sola página (SPA) para gestionar la navegación entre diferentes vistas. Proporciona un enfoque declarativo para definir las rutas y vincularlas a componentes específicos.

-**2.4 react-router react-icons**
Extensión de React Router que facilita la integración de íconos en React. 

# Paso 3
Dirigirse a la carpeta titulada “Servicio web”, en la cual se encuentra la base de datos, en terminal utilizar los comando “yarn dev” y esperar confirmación que está funcionando correctamente.

# Paso 4
Ahora navegar a la carpeta “ Frontend” se encuentra las vistas, por lo cual se ejecuta nuevamente el comando “yarn dev”, el cual proporcionará un link para dirigirse a su navegador web.

# Paso 5
Ahora posee la dirección para acceder a la aplicación y el proyecto estará funcionando localmente.

# Problemas comunes
Se debe asegurar en caso de correr el servicio web localmente, que este se corra en el puerto http://localhost:5173 para una correcta configuración entre el servicio backend y frontend. 


****************************

# Manual de usuario - Studium 
La plataforma Studium fue diseñada para facilitar la carga de trabajo de los tutores de los círculos de estudio que ofrece la universidad Centroamericana José Simeón Cañas, y sirviendo como medio para que estudiantes se unan a espacios virtuales con recursos de la asignatura e incluyendo la funcionalidad que los catedráticos pueden buscar instructores para su asignatura.
A continuación, encontrarás un manual que te guiará a través de diversas acciones en nuestra página web.

# Iniciar sesión 
Para iniciar sesión en la plataforma visite https://studium-seven.vercel.app/ en su navegador y da click en “Iniciar sesión”. Su cuenta debe de ser creada con el correo institucional de la UCA.

# Cerrar sesión
Presione el icono de salida al lado izquierdo superior de la pantalla y de click en “Cerrar sesión”.

# Creación de cursos 
Para crear un curso debe dirigirse a su perfil y al lado derecho de su información apretar en el botón “Crear curso” y completar los campos que solicita, recuerde presionar la opción “Guardar” para que su curso sea creado exitosamente.

# Unirse a un curso 
Puede navegar en los cursos disponible, si desea unirse a un curso presione en el botón titulado “Unirse” que posee un icono de correo

# Enviar correos
En el menú lateral que se encuentra al lado izquierdo de la pantalla, seleccionar la opción “Correo”, y en la sección puede encontrar el campo necesario para la información del correo, incluyendo su cuerpo y asunto. Para seleccionar los destinatarios seleccione el botón ubicado debajo del curso donde se encuentran las personas inscritas al mismo, finalmente presione enviar.

# Metabuscador
En la barra de búsqueda seleccione al lado izquierdo las condiciones por las que desea realizar su consulta: Por cursos, por materia o por perfiles. Luego digite la información requerida y se mostrarán las coincidencias al presionar enter o al presionar en el botón “Buscar”.

# Actualizar o registrar información de perfil
En el aparta “Perfil” del menú aparecerá la información ingresada de su usuario, dentro del mismo puede introducir información de la cantidad de materias cursadas, CUM, materias cursadas y su nota final, así como también la eliminación respectiva de dicha materia mediante el icono de borrar ubicado al lado derecho de la tabla.

# Recurso
Dentro de los cursos el dueño del mismo puede agregar elementos de apoyo para estudio en el apartado de “Crear nuevo recurso” donde le solicitará el título del recurso y su descripción, donde también puede incluir link a videos, documentos, páginas, etc. y el tutorado puede acceder a dicha información. 

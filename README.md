# Ejercicio: Página de Perfil de Usuario con React y Bootstrap

**Objetivo**: Crear una página de perfil de usuario utilizando React y Bootstrap, dividida en varios componentes, incluyendo encabezado, foto de perfil, información personal, y lista de hobbies.

---

## Paso a Paso: Creación de la Página Web con React + Bootstrap

### 1. Configuración Inicial:
- Crea un nuevo proyecto React utilizando `create-react-app`.
- Instala Bootstrap en tu proyecto.

### 2. Componente Encabezado (`Header.js`):
- Crea un componente que muestre un encabezado con el nombre del usuario.
- Usa la clase `navbar` de Bootstrap para estilizarlo.

### 3. Componente Foto de Perfil (`ProfilePicture.js`):
- Crea un componente que muestre la foto del usuario.
- Utiliza la clase `card-img-top` de Bootstrap.

### 4. Componente Información Personal (`PersonalInfo.js`):
- Crea un componente que muestre información básica del usuario, como nombre completo, edad, y descripción breve.
- Utiliza clases como `card-title` y `card-text`.

### 5. Componente Lista de Hobbies (`HobbiesList.js`):
- Crea un componente que muestre una lista de hobbies o intereses del usuario.
- Usa una lista desordenada (`<ul>`) y estilízala con clases de Bootstrap.

### 6. Componente Principal (`UserProfile.js`):
- Este componente integrará todos los componentes anteriores.
- Usa la clase `card` de Bootstrap para envolver todo y darle un estilo cohesivo.

### 7. Integración en `App.js`:
- Importa y utiliza el componente `UserProfile` en `src/App.js`.

### 8. Estilización Adicional:
- Añade cualquier estilización adicional que desees, ya sea utilizando más componentes de Bootstrap o añadiendo tu propio CSS.

---

## Paso a Paso: Desplegar en GitHub Pages

### 1. Preparativos:
- Asegúrate de tener un repositorio en GitHub donde esté tu proyecto React.
- Instala el paquete `gh-pages` en tu proyecto.

### 2. Configura `package.json`:
- Añade la propiedad `"homepage"` a tu `package.json`.
- Añade scripts para desplegar tu aplicación.

### 3. Despliega tu Aplicación:
- Ejecuta el comando de despliegue.

### 4. Configura GitHub:
- Ve a tu repositorio en GitHub.
- Configura la fuente de GitHub Pages para que use la rama `gh-pages`.

### 5. ¡Listo!:
- Tu aplicación React ahora debería estar disponible en la URL que especificaste en la propiedad `"homepage"` de tu `package.json`.

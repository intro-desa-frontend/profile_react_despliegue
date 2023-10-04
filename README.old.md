# Ejercitación Práctica: Creación de un Perfil de Usuario con React y Bootstrap

**Objetivo General**: 
Desarrollar una aplicación React que simule una página de perfil de usuario, utilizando múltiples componentes y navegación con React Router DOM. La aplicación debe estar estilizada con Bootstrap y finalmente, se desplegará en GitHub Pages.

## Especificaciones:

### 1. Componentes Principales:
   - **Encabezado**: Debe contener el nombre de la aplicación y un menú de navegación.
   - **Página Principal (`Home`)**: Una breve introducción o bienvenida al perfil del usuario.
   - **Información Personal (`About`)**: Detalles como nombre, edad, ocupación y una breve biografía.
   - **Hobbies (`Hobbies`)**: Una lista o galería de hobbies o intereses del usuario.
   - **Contacto (`Contact`)**: Un formulario ficticio para contactar al usuario (no es necesario que funcione).

### 2. Navegación:
   - Implementar React Router DOM para navegar entre los diferentes componentes.
   - El menú en el encabezado debe permitir al usuario cambiar entre las páginas principales, información personal, hobbies y contacto.

### 3. Estilización:
   - Utilizar Bootstrap para estilizar la aplicación, asegurándose de que sea responsiva.

### 4. Despliegue:
   - La aplicación debe ser desplegada en GitHub Pages.

## Creación y Configuración del Proyecto React
1. Crear el proyecto:
```bash
npx create-react-app profile_react_despliegue
cd profile_react_despliegue
```

2. Instalar las dependencias necesarias:
```bash
npm install react-router-dom bootstrap
```

3. Importar Bootstrap en src/index.css:
```css
@import "~bootstrap/dist/css/bootstrap.min.css";
```

4. Configurar React Router DOM:
En src/App.js, importa los componentes necesarios de react-router-dom y configura las rutas para cada componente de tu aplicación.
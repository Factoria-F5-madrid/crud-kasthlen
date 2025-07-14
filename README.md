# 📚 Sistema de Gestión de Libros en Django

Este proyecto es una aplicación web construida con Django que permite **crear, leer, actualizar y eliminar libros**. Es un sistema básico de gestión de libros, ideal para aprender sobre aplicaciones CRUD, patrones de arquitectura como MVT, y cómo Django estructura sus proyectos.
<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/59d92d8e-aa24-4150-b856-d4774df82a3c" />


---

## 1. ¿Qué es un CRUD y cuál es su propósito en el desarrollo de aplicaciones web?

**CRUD** es un acrónimo en inglés que significa:

- **C**reate → Crear datos.
- **R**ead → Leer datos.
- **U**pdate → Actualizar datos.
- **D**elete → Eliminar datos.

El propósito de un CRUD en una aplicación web es permitir que los usuarios **interactúen con los datos de forma completa**, es decir, que puedan agregar, ver, editar y borrar información a través de una interfaz sencilla.

### 🧩 Ejemplo de aplicación CRUD:
**Instagram** es un ejemplo:  
- Crear: puedes subir una nueva foto (crear un post).
- Leer: puedes ver tus publicaciones y las de otros.
- Update: puedes editar la descripción o eliminar comentarios.
- Delete: puedes borrar tus publicaciones.
<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/ab43a3e4-cbbb-4fb1-9be3-18326f29f064" />


---

## 2. ¿Qué son los patrones de arquitectura en desarrollo de software?

Los **patrones de arquitectura** son formas organizadas de estructurar el código de un proyecto. Ayudan a separar responsabilidades para que el software sea **más ordenado, mantenible y escalable**.

### 📌 ¿Qué es el patrón MVC (Modelo–Vista–Controlador)?

- **Modelo:** Gestiona los datos (base de datos).
- **Vista:** Muestra los datos al usuario.
- **Controlador:** Maneja la lógica y decide qué datos mostrar y cómo responder.
  <img width="640" height="480" alt="image" src="https://github.com/user-attachments/assets/30e48459-4d72-4af6-b198-131052ad379c" />

Es como un restaurante:
- Modelo: la cocina (prepara los datos).
- Controlador: el camarero (recibe pedidos y entrega resultados).
- Vista: el plato en la mesa (la interfaz que el cliente ve).

### 📌 ¿Qué es el patrón MVT (Modelo–Vista–Template)?
<img width="310" height="163" alt="image" src="https://github.com/user-attachments/assets/91fb48e9-f9e6-43c1-aff3-9e2404630810" />

Django usa una variación de MVC llamada **MVT**:

- **Modelo:** igual que en MVC, gestiona los datos.
- **Vista:** contiene la lógica (funciones que responden a una solicitud).
- **Template (Plantilla):** es el HTML que se muestra al usuario.

En MVT, Django ya se encarga del "Controlador", por eso tú solo te enfocas en **Modelos, Vistas y Plantillas**.

### 🆚 Diferencias entre MVC y MVT

| Concepto | MVC | MVT |
|----------|-----|-----|
| Modelo   | ✔️ Gestiona datos | ✔️ Gestiona datos |
| Vista    | Interfaz (HTML) | Lógica (respuesta de solicitud) |
| Controlador | Lógica (acciones del usuario) | Implícito (Django lo maneja) |
| Template | No existe como tal | HTML que se muestra al usuario |

### ✅ ¿Cuál se usa en Django?
Django usa el patrón **MVT**.
<img width="900" height="628" alt="image" src="https://github.com/user-attachments/assets/73a23dc4-7bb3-4fab-b7b7-342b6c474da0" />

---

## 3. ¿Cómo se estructura un proyecto en Django?

Un proyecto en Django se divide en varias partes:

1. Carpeta Raíz del proyecto:
   
- **manage.py**: Utilidad de línea de comandos para administrar el proyecto, como ejecutar el servidor de desarrollo, realizar migraciones, etc. 
- **nombre_proyecto/**: Subcarpeta con el nombre del proyecto, que contiene:
- ** __init__.py:** Archivo vacío que marca el directorio como un paquete Python. 
- **settings.py:** Archivo de configuración del proyecto, donde se definen variables como la base de datos, las aplicaciones instaladas, la configuración regional, etc. 
- **urls.py:** Archivo que define las rutas (URLs) del proyecto y las vistas asociadas. 
- **wsgi.py y asgi.py:** Puntos de entrada para la comunicación con servidores web, utilizados para el despliegue. 

2. Aplicaciones:
- **Modelos (`models.py`)**: Definen las tablas de la base de datos. Cada clase representa un tipo de dato (por ejemplo: Libro).
- **Vistas (`views.py`)**: Son funciones que procesan las solicitudes y deciden qué se muestra o se guarda.
- **Templates (`templates/`)**: Son archivos HTML donde se muestra la información al usuario.
- **URLs (`urls.py`)**: Conectan las direcciones web (como `/libros/1/`) con la vista que se debe ejecutar.

3. Beneficios:
**Modularidad:**
Facilita la organización y el desarrollo de proyectos complejos dividiéndolos en partes más pequeñas y manejables.
**Reutilización:**
Las aplicaciones pueden ser reutilizadas en otros proyectos Django con relativa facilidad.
**Mantenibilidad:**
La estructura clara facilita la comprensión y el mantenimiento del código, especialmente en proyectos a largo plazo.
**Escalabilidad:**
Permite agregar nuevas funcionalidades o modificar las existentes sin afectar a otras partes del proyecto. 
Por lo tanto, la estructura de Django promueve un desarrollo organizado, modular y mantenible, permitiendo a los desarrolladores construir aplicaciones web complejas de manera eficiente.

---

### 🧠 ¿Para qué se usa el signo `{{ }}` y `{% %}` en los templates?

- `{{ dato }}`: Muestra un valor o variable en el HTML.
- `{% instrucción %}`: Se usa para ejecutar instrucciones como bucles o condiciones (por ejemplo: `{% for libro in libros %}`).
#### Ejemplo con static
 ¿Qué es {% static %}?
Es una etiqueta del sistema de plantillas de Django que genera la URL absoluta del archivo estático indicado.

Por ejemplo:


```
<link rel="stylesheet" href="{% static 'libros/css/lista_libros.css' %}">
```
Esto se convertirá en el navegador en algo como:

```
<link rel="stylesheet" href="/static/libros/css/lista_libros.css">
```
Asumiendo que tu configuración en settings.py tiene:
```
STATIC_URL = '/static/'
```
#¿Por qué no usar simplemente /static/libros/css/lista_libros.css directamente?
Podrías hacerlo, pero:

1. No es portable: si cambias STATIC_URL a otra cosa (por ejemplo, /assets/ en producción), tendrías que cambiar todos los href/src manualmente.

2. Es mala práctica: Django recomienda siempre usar {% static %} para evitar errores y adaptarse a entornos de desarrollo y producción.

3. Soporta almacenamiento externo: si usas Amazon S3, CDN u otra configuración más avanzada, Django sabe cómo resolver la URL correcta.
---

## 4. ¿Cuál es el flujo de datos entre un formulario HTML y la base de datos en Django?

1. El usuario **llena un formulario HTML** (por ejemplo, para crear un libro).
2. Al hacer clic en "Enviar", el formulario envía los datos al servidor.
3. Django recibe esos datos en una **vista**.
4. La vista **valida y guarda los datos** usando un **formulario de Django (ModelForm)**.
5. Los datos se **guardan en la base de datos**.
6. Se muestra una página de confirmación o se redirige a la lista de libros.

---

## 5. ¿Qué herramientas o comandos ofrece Django para facilitar el desarrollo de un CRUD?

| Herramienta/Comando | Función |
|---------------------|---------|
| `startapp`          | Crea una nueva aplicación (como "libros"). |
| `makemigrations`    | Crea archivos para aplicar cambios a la base de datos. |
| `migrate`           | Aplica las migraciones y crea/modifica las tablas. |
| `runserver`         | Inicia el servidor local de desarrollo. |
| `ModelForm`         | Crea formularios automáticos basados en modelos. |
| `admin`             | Panel web automático para gestionar los datos sin programar nada. |
| `createsuperuser`   | Crea un usuario administrador para entrar al panel de administración. |
| `python manage.py shell` | Abre una consola, es ideal para depurar y probar rápidamente. |


---

## 6. ¿Cómo funciona el Admin de Django?

Django tiene un panel llamado **admin** (http://localhost:8000/admin) que permite:

- Ver, crear, editar y eliminar datos de cualquier modelo.
- Acceder solo con usuarios con permisos de administrador.
- Es muy útil para gestionar datos **sin tener que crear páginas manuales**.

### ¿Cómo se usa?

1. Activas los modelos en `admin.py` con:
   ```python
   from .models import Libro
   admin.site.register(Libro)
2. Inicias sesión con tu superusuario.

3. Ya puedes gestionar libros y cualquier otro modelo desde una interfaz web sencilla.

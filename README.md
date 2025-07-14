# 📚 Sistema de Gestión de Libros en Django

Este proyecto es una aplicación web construida con Django que permite **crear, leer, actualizar y eliminar libros**. Es un sistema básico de gestión de libros, ideal para aprender sobre aplicaciones CRUD, patrones de arquitectura como MVT, y cómo Django estructura sus proyectos.

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

---

## 2. ¿Qué son los patrones de arquitectura en desarrollo de software?

Los **patrones de arquitectura** son formas organizadas de estructurar el código de un proyecto. Ayudan a separar responsabilidades para que el software sea **más ordenado, mantenible y escalable**.

### 📌 ¿Qué es el patrón MVC (Modelo–Vista–Controlador)?

- **Modelo:** Gestiona los datos (base de datos).
- **Vista:** Muestra los datos al usuario.
- **Controlador:** Maneja la lógica y decide qué datos mostrar y cómo responder.

Es como un restaurante:
- Modelo: la cocina (prepara los datos).
- Controlador: el camarero (recibe pedidos y entrega resultados).
- Vista: el plato en la mesa (la interfaz que el cliente ve).

### 📌 ¿Qué es el patrón MVT (Modelo–Vista–Template)?

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

---

## 3. ¿Cómo se estructura un proyecto en Django?

Un proyecto en Django se divide en varias partes:

- **Modelos (`models.py`)**: Definen las tablas de la base de datos. Cada clase representa un tipo de dato (por ejemplo: Libro).
- **Vistas (`views.py`)**: Son funciones que procesan las solicitudes y deciden qué se muestra o se guarda.
- **Templates (`templates/`)**: Son archivos HTML donde se muestra la información al usuario.
- **URLs (`urls.py`)**: Conectan las direcciones web (como `/libros/1/`) con la vista que se debe ejecutar.

### 🧠 ¿Para qué se usa el signo `{{ }}` y `{% %}` en los templates?

- `{{ dato }}`: Muestra un valor o variable en el HTML.
- `{% instrucción %}`: Se usa para ejecutar instrucciones como bucles o condiciones (por ejemplo: `{% for libro in libros %}`).

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

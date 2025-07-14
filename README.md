# 📚 Sistema de Gestión de Libros en Django

Este proyecto es una aplicación web construida con Django que permite **crear, leer, actualizar y eliminar libros**. Es un sistema básico de gestión de libros, ideal para aprender sobre aplicaciones CRUD, patrones de arquitectura como MVT, y cómo Django estructura sus proyectos.

<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/59d92d8e-aa24-4150-b856-d4774df82a3c" />


---

## 1. ¿Qué es un CRUD y cuál es su propósito en el desarrollo de aplicaciones web?

**CRUD** es un acrónimo en inglés que significa:

:cherries: **C**reate → Crear datos. <br>
:cherries: **R**ead → Leer datos. <br>
:cherries: **U**pdate → Actualizar datos. <br>
:cherries: **D**elete → Eliminar datos. <br>

El propósito de un CRUD en una aplicación web es permitir que los usuarios **interactúen con los datos de forma completa**, es decir, que puedan agregar, ver, editar y borrar información a través de una interfaz sencilla.

### 🧩 Ejemplo de aplicación CRUD:
**Instagram** es un ejemplo:  
:cherries: Crear: puedes subir una nueva foto (crear un post). <br>
:cherries: Leer: puedes ver tus publicaciones y las de otros. <br>
:cherries: Update: puedes editar la descripción o eliminar comentarios. <br>
:cherries: Delete: puedes borrar tus publicaciones. <br>
  
<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/ab43a3e4-cbbb-4fb1-9be3-18326f29f064" />


---

## 2. ¿Qué son los patrones de arquitectura en desarrollo de software?

Los **patrones de arquitectura** son formas organizadas de estructurar el código de un proyecto. Ayudan a separar responsabilidades para que el software sea **más ordenado, mantenible y escalable**.

### :star2:  ¿Qué es el patrón MVC (Modelo–Vista–Controlador)?

:cherries:  **Modelo:** Gestiona los datos (base de datos). <br>
:cherries:  **Vista:** Muestra los datos al usuario. <br>
:cherries:  **Controlador:** Maneja la lógica y decide qué datos mostrar y cómo responder. <br>
  
<img width="640" height="480" alt="image" src="https://github.com/user-attachments/assets/30e48459-4d72-4af6-b198-131052ad379c" />

🧑‍🍳 Es como un restaurante:

:cherries:  Modelo: la cocina (prepara los datos).  <br>
:cherries:  Controlador: el camarero (recibe pedidos y entrega resultados). <br>
:cherries:  Vista: el plato en la mesa (la interfaz que el cliente ve). <br>

---
### :star2:  ¿Qué es el patrón MVT (Modelo–Vista–Template)?

<img width="900" height="628" alt="image" src="https://github.com/user-attachments/assets/73a23dc4-7bb3-4fab-b7b7-342b6c474da0" />

Django usa una variación de MVC llamada **MVT**:

:cherries:  **Modelo:** igual que en MVC, gestiona los datos. <br>
:cherries:  **Vista:** contiene la lógica (funciones que responden a una solicitud). <br>
:cherries:  **Template (Plantilla):** es el HTML que se muestra al usuario. <br>

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

<img width="310" height="163" alt="image" src="https://github.com/user-attachments/assets/91fb48e9-f9e6-43c1-aff3-9e2404630810" />

---

## 3. ¿Cómo se estructura un proyecto en Django?

Un proyecto en Django se divide en varias partes:

**1. Carpeta Raíz del proyecto:**
   
:cherries:  **manage.py**: Utilidad de línea de comandos para administrar el proyecto, como ejecutar el servidor de desarrollo, realizar migraciones, etc.  <br>
:cherries:  **nombre_proyecto/**: Subcarpeta con el nombre del proyecto, que contiene: <br>
:cherries:  **__init__.py:** Archivo vacío que marca el directorio como un paquete Python.  <br>
:cherries:  **settings.py:** Archivo de configuración del proyecto, donde se definen variables como la base de datos, las aplicaciones instaladas, la configuración regional, etc.  <br>
:cherries:  **urls.py:** Archivo que define las rutas (URLs) del proyecto y las vistas asociadas.  <br>
:cherries:  **wsgi.py y asgi.py:** Puntos de entrada para la comunicación con servidores web, utilizados para el despliegue.  <br>

**2. Aplicaciones:**

:cherries:  **Modelos (`models.py`)**: Definen las tablas de la base de datos. Cada clase representa un tipo de dato (por ejemplo: Libro). <br>
:cherries:  **Vistas (`views.py`)**: Son funciones que procesan las solicitudes y deciden qué se muestra o se guarda. <br>
:cherries:  **Templates (`templates/`)**: Son archivos HTML donde se muestra la información al usuario. <br>
:cherries:  **URLs (`urls.py`)**: Conectan las direcciones web (como `/libros/1/`) con la vista que se debe ejecutar. <br>

**3. Beneficios:**

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

### :star2:  ¿Para qué se usa el signo `{{ }}` y `{% %}` en los templates?

- `{{ dato }}`: Muestra un valor o variable en el HTML. <br>
- `{% instrucción %}`: Se usa para ejecutar instrucciones como bucles o condiciones (por ejemplo: `{% for libro in libros %}`). <br>
- 
### Ejemplo con static

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
----
### ¿Por qué no usar simplemente /static/libros/css/lista_libros.css directamente?
Podrías hacerlo, pero:

**1. No es portable:** si cambias STATIC_URL a otra cosa (por ejemplo, /assets/ en producción), tendrías que cambiar todos los href/src manualmente.

2. **Es mala práctica:** Django recomienda siempre usar {% static %} para evitar errores y adaptarse a entornos de desarrollo y producción.

3. **Soporta almacenamiento externo:** si usas Amazon S3, CDN u otra configuración más avanzada, Django sabe cómo resolver la URL correcta.
   
---

### 4. ¿Cuál es el flujo de datos entre un formulario HTML y la base de datos en Django?

1. El usuario **llena un formulario HTML** (por ejemplo, para crear un libro).
2. Al hacer clic en "Enviar", el formulario envía los datos al servidor.
3. Django recibe esos datos en una **vista**.
4. La vista **valida y guarda los datos** usando un **formulario de Django (ModelForm)**.
5. Los datos se **guardan en la base de datos**.
6. Se muestra una página de confirmación o se redirige a la lista de libros.

----

### ¿Qué es un formulario HTML?

Es una parte de una página web que te permite escribir información, por ejemplo:

```
<form method="post"> <br/>
<input type="text" name="titulo"> <br/>
<button type="submit">Guardar</button> <br/>
</form><br/>
```

Es como llenar una ficha de papel, solo que lo haces en una página web. Esa información necesita ser enviada a algún lugar… y aquí es donde entra Django.

----

###  ¿A dónde va la información del formulario?

Cuando haces clic en el botón de "Guardar" (o "Enviar"), la información que escribiste se envía al servidor, es decir, al "cerebro" de tu aplicación Django. El servidor recibe los datos, los procesa y, si todo está bien, los guarda en una base de datos (un lugar que almacena toda la información).
----

### Flujo completo, paso a paso

**1. El usuario abre una página para llenar un formulario**

Por ejemplo: una página para crear un nuevo libro. Django te muestra un formulario en HTML con campos como:

:cherries: Título <br>
:cherries: Autor <br>
:cherries: Descripción <br>
:cherries: ISBN <br>

**2. El usuario llena el formulario**
   
La persona escribe:

:cherries:  Título: Cien Años de Soledad <br>
:cherries:  Autor: Gabriel García Márquez <br>
:cherries:  ... <br>

Y hace clic en "Guardar".

---

**3. El navegador envía los datos al servidor de Django**
   
Django recibe esos datos como un "paquete" que contiene:

`
titulo = "Cien Años de Soledad" <br/>
autor = "Gabriel García Márquez" <br/>
descripcion = "Una novela sobre..." <br/>
` 
**4. Django procesa y valida los datos**

Django revisa:

:cherries:  ¿Faltó algún campo obligatorio?  <br>
:cherries:  ¿El ISBN es un número válido? <br>
:cherries:  ¿El título ya existe? <br>
  
Para hacer esto, Django suele usar una clase llamada ModelForm, que verifica que los datos cumplan las reglas.

**5.  Si los datos son válidos, Django los guarda en la base de datos**
   
Django convierte ese "paquete" en un nuevo registro de libro, y lo guarda en la base de datos (como si fuera una gran hoja de cálculo).

**6. Django responde al usuario**
   
Después de guardar los datos, Django puede hacer varias cosas:

:cherries:  Mostrar un mensaje de "Libro guardado con éxito". <br>
:cherries:  Llevar al usuario a otra página (como la lista de libros). <br>
:cherries:  Volver al formulario para crear otro. <br>
----

### Ejemplo 

| Paso | Acción                               | ¿Qué hace Django?              |
| ---- | ------------------------------------ | ------------------------------ |
| 1    | Llenas un formulario                 | HTML                           |
| 2    | Lo envías (click en Guardar)         | Recibe los datos               |
| 3    | Django revisa si todo está bien      | `ModelForm` valida             |
| 4    | Guarda los datos en la base de datos | Usando el modelo (ej: `Libro`) |
| 5    | Muestra una respuesta al usuario     | Redirecciona o muestra mensaje |

🌟 ¿Qué archivos están involucrados en Django?
 
| Archivo            | Rol                                                      |
| ------------------ | -------------------------------------------------------- |
| `forms.py`         | Define el formulario (con validaciones)                  |
| `views.py`         | Recibe y maneja los datos del formulario                 |
| `models.py`        | Define cómo se guarda la información en la base de datos |
| `templates/*.html` | Contiene el formulario que ve el usuario                 |

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

:cherries:  Ver, crear, editar y eliminar datos de cualquier modelo. <br>
:cherries:  Acceder solo con usuarios con permisos de administrador. <br>
:cherries:  Es muy útil para gestionar datos **sin tener que crear páginas manuales**. <br>

### ¿Cómo se usa?

**1. Activas los modelos en `admin.py` con:**
   `
   from .models import Libro <br/>
   admin.site.register(Libro)<br/>
   `
   
3. **Inicias sesión con tu superusuario.**

4. **Ya puedes gestionar libros y cualquier otro modelo desde una interfaz web sencilla.**

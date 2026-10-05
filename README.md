# Ferretería El Tornillo

Proyecto desarrollado con Django para la Evaluación Sumativa 1 de Programación Back End. Corresponde a la variante A de la pauta: un catálogo online para una ferretería con 40 productos cargados desde un archivo JSON.

## Funcionalidades principales

- Landing de presentación con ideas de proyectos, nuestra historia, contacto, guía de compra y botón hacia el catálogo independiente.
- Catálogo completo con nombre, categoría, precio y stock de cada producto.
- Datos cargados desde `data/catalogo.json` en la vista de Django.
- Listado generado con un bucle en el template.
- Detalle de cada producto mediante su ID y página de error si el producto no existe.
- Resumen con el total de productos, productos con stock, productos agotados y categorías.
- Destaque visual para los productos sin stock.
- Herencia de templates mediante `base.html` y diseño adaptable a celulares.

El proyecto también incluye búsqueda, filtros, carrito de compras, registro e inicio de sesión. Los clientes pueden confirmar pedidos de demostración y revisar sus compras. El administrador puede crear, editar y eliminar productos, actualizar el stock y consultar los pedidos realizados.

## Instalación

Se necesita Python 3 y `pip`.

En Linux o macOS:

```bash
python3 -m venv venv
source venv/bin/activate
python -m pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

En Windows:

```bash
py -m venv venv
venv\Scripts\activate
python -m pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

Luego se puede abrir la tienda en <http://127.0.0.1:8000/>.

## Credenciales de prueba

Las cuentas están guardadas en `data/usuarios.json` con las contraseñas visibles para facilitar la revisión de la evaluación.

| Tipo de cuenta | Usuario | Contraseña |
| --- | --- | --- |
| Administrador | `admin` | `AdminTornillo2026!` |
| Cliente | `cliente` | `ClienteTornillo2026!` |

Ambas cuentas ingresan desde <http://127.0.0.1:8000/cuenta/ingresar/>. Los usuarios creados desde el formulario de registro también se guardan en `data/usuarios.json` con el rol de cliente.

## Rutas principales

- `/`: landing de presentación de la ferretería.
- `/catalogo/`: catálogo de productos con búsqueda, filtros y orden.
- `/#historia`: sección Nuestra historia.
- `/#como-comprar`: guía de compra de demostración.
- `/#contacto`: sección de contacto y orientación para pedidos.
- `/carrito/`: carrito de compras.
- `/cuenta/ingresar/`: ingreso de clientes y administrador.
- `/cuenta/registro/`: registro de clientes.
- `/gestion/`: gestión de productos y stock para el administrador.
- `/gestion/pedidos/`: pedidos registrados.

## Archivos principales

- `catalogo/views.py`: vistas, carga del JSON y cálculos del catálogo.
- `catalogo/urls.py`: rutas de la aplicación.
- `catalogo/templates/`: templates del catálogo, carrito, cuentas y administración.
- `catalogo/static/catalogo/`: estilos, JavaScript e imágenes del sitio.
- `data/catalogo.json`: catálogo inicial de 40 productos.
- `data/usuarios.json`: usuarios y roles de acceso.
- `config/`: configuración general del proyecto Django.

## Comprobación

Con el entorno virtual activado se pueden ejecutar estas comprobaciones:

```bash
python manage.py check
python manage.py test
```

Las compras son solo una demostración académica: no se realizan pagos ni envíos reales. Los pedidos y los cambios hechos desde la administración se guardan localmente durante el uso de la aplicación.

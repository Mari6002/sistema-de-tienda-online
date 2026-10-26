

Plataforma web para que los negocios de Nueva Loja (Lago Agrio), Ecuador, publiquen sus productos con precio y disponibilidad, y para que los compradores encuentren lo que buscan sin recorrer toda la ciudad.

> **Estado:** en desarrollo (MVP). Meta de lanzamiento del piloto: temporada de Navidad.

## ¿Qué problema resuelve?

- **Compradores:** ahorran tiempo y caminata al ver qué hay, a qué precio y dónde, antes de salir de casa.
- **Negocios:** reciben más clientes y ordenan sus números: costos, precios sugeridos, stock y ganancia.

## Funcionalidades

### MVP (piloto)
- [ ] Registro e inicio de sesión con roles (negocio, comprador, administrador)
- [ ] Perfil del negocio y verificación básica
- [ ] Productos con variantes (talla, color), costo, precio y stock
- [ ] Vigencia de publicaciones (el negocio confirma que sigue disponible)
- [ ] Catálogo público con búsqueda y filtros
- [ ] Pedido por WhatsApp con mensaje prellenado
- [ ] Pedidos pendientes y "venta confirmada" (ticket interno, no es factura)
- [ ] Panel con ganancias y estadísticas básicas
- [ ] Plan gratuito y plan de pago

### Más adelante
- [ ] Servicios (sin stock, con vigencia)
- [ ] Reseñas de compradores con venta confirmada
- [ ] Código de referidos para negocios
- [ ] Avisos automáticos

## Tecnologías

- **Backend:** Python, Flask
- **Base de datos:** PostgreSQL
- **Frontend:** HTML, CSS, JavaScript (plantillas Jinja)
- **Control de versiones:** Git y GitHub

## Estructura del proyecto

```
.
├── app/
│   ├── __init__.py
│   ├── models/
│   ├── routes/          # auth, negocios, productos, pedidos, publico
│   ├── templates/
│   └── static/
├── migrations/
├── tests/
├── docs/                # decisiones, diagrama de la base de datos
├── config.py
├── run.py
├── requirements.txt
├── .env.example
└── README.md
```

## Instalación local

```bash
# 1. Clonar el repositorio
git clone https://github.com/TU_USUARIO/TU_REPOSITORIO.git
cd TU_REPOSITORIO

# 2. Crear y activar el entorno virtual
python -m venv venv
source venv/bin/activate        # En Windows: venv\Scripts\activate

# 3. Instalar dependencias
pip install -r requirements.txt

# 4. Configurar variables de entorno
cp .env.example .env            # y completa los valores

# 5. Ejecutar
flask run
```

## Variables de entorno

Copia `.env.example` a `.env`. **Nunca subas el archivo `.env` a GitHub.**

```
SECRET_KEY=cambia-esto
DATABASE_URL=postgresql://usuario:clave@host:5432/nombre_bd
FLASK_ENV=development
```

## Seguridad

- Contraseñas con hash seguro
- Consultas parametrizadas (sin SQL armado a mano)
- Protección CSRF y cookies de sesión seguras
- Límite de intentos de inicio de sesión
- Cada negocio solo accede a sus propios datos
- Secretos fuera del código, en variables de entorno

Si encuentras una vulnerabilidad, por favor repórtala de forma privada a: `tu-correo@ejemplo.com`.

## Decisiones del proyecto

- La plataforma es intermediaria: no procesa pagos. El cobro lo gestiona cada negocio.
- Por ahora solo productos nuevos. No se permiten medicinas, ropa usada, imitaciones, pirotecnia, armas, alcohol ni tabaco.
- El detalle está en la carpeta `docs/`.

## Cómo se avanza en el repositorio

- Rama `main`: versión estable.
- Una rama por funcionalidad (`feature/login`, `feature/productos`).
- Commits pequeños y claros, por ejemplo: `Agrega registro de negocios`.
- Al terminar cada funcionalidad, se marca en la lista de arriba.

## Licencia

Por definir.

## Autor

[Tu nombre] · Nueva Loja, Sucumbíos, Ecuador

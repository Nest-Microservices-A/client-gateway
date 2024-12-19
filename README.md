# Client Gateway Microservice

Este proyecto es un microservicio de gateway CRUD desarrollado con [NestJS](https://nestjs.com/) y [NATS](https://nats.io/). Actúa como un punto de entrada para conectar y coordinar otros microservicios en el sistema.

## Características

- **NestJS**: Un framework progresivo de Node.js para construir aplicaciones eficientes y escalables del lado del servidor.
- **NATS**: Un sistema de mensajería distribuido que permite la comunicación entre microservicios.
- **CRUD**: Implementación de operaciones CRUD para gestionar recursos a través de microservicios.

## Requisitos previos

- Node.js (versión 14 o superior)
- npm (versión 6 o superior)
- NATS Server

## Instalación

1. Clona el repositorio:

   ````bash
   git clone https://github.com/Nest-Microservices-A/client-gateway.git
   cd client-gateway   ```

   ````

2. Instala las dependencias:

   ````bash
   npm install   ```

   ````

3. Configura las variables de entorno:

   Crea un archivo `.env` en la raíz del proyecto basado en el archivo `.env.template` y ajusta los valores según sea necesario.

   ````plaintext
   PORT=3000
   PRODUCTS_MICROSERVICE_HOST=localhost
   PRODUCTS_MICROSERVICE_PORT=3001
   ORDERS_MICROSERVICE_HOST=localhost
   ORDERS_MICROSERVICE_PORT=3002
   NATS_SERVERS="nats://localhost:4222,nats://localhost:4223"   ```
   ````

## Ejecución

1. Asegúrate de que el servidor NATS esté en ejecución.

2. Inicia el microservicio:

   ````bash
   npm run start:dev   ```

   Esto iniciará el servidor en modo de desarrollo con recarga automática.
   ````

## Arquitectura

El microservicio está estructurado en módulos que representan diferentes dominios de la aplicación:

- **AuthModule**: Maneja la autenticación de usuarios.
- **OrdersModule**: Gestiona las operaciones relacionadas con pedidos.
- **ProductsModule**: Gestiona las operaciones relacionadas con productos.
- **NatsModule**: Configura la conexión con el servidor NATS.

## Uso

El microservicio expone varias rutas HTTP para interactuar con los recursos. Aquí hay algunos ejemplos:

- **POST /api/auth/register**: Registra un nuevo usuario.
- **POST /api/auth/login**: Inicia sesión un usuario.
- **GET /api/orders**: Obtiene una lista de pedidos.
- **POST /api/orders**: Crea un nuevo pedido.
- **GET /api/products**: Obtiene una lista de productos.
- **POST /api/products**: Crea un nuevo producto.

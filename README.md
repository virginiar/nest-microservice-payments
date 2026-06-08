<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

# Nest-MicroServices - Payments microservice

Repositorio para el microservicio Payments de la aplicación Products realizada en [Nest](https://github.com/nestjs/nest). 
Basado en el curso de "NestJs + Microservicios: Aplicaciones escalables y modulares" de [DevTalles](https://cursos.devtalles.com/) en Udemy.

## Configuración del proyecto

1. Instalar NestJS CLI

```bash
$ npm i -g @nestjs/cli
```

2. Clonar el repositorio

3. Instalar las dependencias

```bash
$ npm install
```

4. Crear el endpoint local de Hookdeck

```bash
$ npm install hookdeck-cli -g
$ hookdeck login
$ hookdeck listen 3003 stripe --path /payments/webhook
```

5. Crear un archivo ```.env``` basado en ```.env.template```.

6. Ejecutar el proyecto

```bash
$ npm run start:dev
```

## Aspectos estudiados

En este repositorio se trabajan los siguientes aspectos de Nest:
-	Crear el RESTful API para crear sesiones de pago
-	Crear un webhook para avisar cuando un pago es realizado

## Librerías utilizadas

Para la gestión de variables de entorno:

```bash
$ npm install dotenv
```

Para los esquemas de validación:

```bash
$ npm install joi
```

Para acceder a la API de Stripe:

```bash
$ npm install stripe
```

Para las validaciones se utilizan:

```bash
$ npm install class-validator class-transformer
```

Para utilizar NATS para las comunicaciones del microservicio:

```bash
$ npm i --save nats
```

Para la gestión de microservicios:

```bash
$ npm i --save @nestjs/microservices
```

Para las pruebas del webhook de Stripe:
- Crear una cuenta en [Stripe](https://www.stripe.com)
- Crear un webhook

```bash
$ stripe --version
$  stripe login
$  stripe listen --forward-to localhost:3003/payments/webhook
$  stripe trigger payment_intent.succeeded
```

Para las pruebas de Hookdeck:
- Crear una cuenta en [Hookdeck](https://www.hookdeck.com)
- Crear una conexión entre el webhook de Stripe y nuestro ordenador local

```bash
$ npm install hookdeck-cli -g
$ hookdeck login
$ hookdeck listen 3003 stripe --path /payments/webhook
```

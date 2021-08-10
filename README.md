#### Teniendo mi primera implementacion con mercado pago, tuve mucha dificultad para poder lograr que funcione esto, debido a la poca claridad de la documentacion.
#### Es por eso que dejo una guia para poder facilitar esto.
## 
### - Tener instalado Composer
### - Tener instalado Apache2

## Pasos

- Clonar repo

- Una vez clonado el repo, abrir la terminal / bash y escribir lo siguiente :

    1- composer init
    <ul> Aparecera lo siguiente:
    
    <li>a) Package name -> Enter</li>
    <li>b) Descripcion -> Enter</li>
    <li>c) Author -> Enter</li>
    <li>d) Minimum Stability -> Enter</li>
    <li>e) Package type -> Enter</li>
    <li>f) License -> Enter</li>
    <li>g) Would you like to define you dependencies (Require) interactively [yes]? --> Escribir NO y enter</li>
    <li>h) Would you like to define your dev dependencies (require-dev) interactively [yes]? --> Escribir NO y enter</li>
    <li>i) Do you confirm generation [yes]? --> Escribir YES y enter</li>
    </ul>
    
    2- composer install
    
    3- composer require "mercadopago/dx-php"

## Una vez terminado de instalar todo esto, haremos lo siguiente

### Mercado Pago

- Iniciar sesion con nuestro usuario

- Ir a credenciales / Credenciales de Prueba

- copiar Access Token

### Vs code

- En el archivo credenciales.php pegamos (de forma temporal) el token

### Curl

copiamos el siguiente CURL que encontraremos en la pagina de MP para generar los usuarios de testing (Vendedor y comprador) :

<code>
curl -X POST \
-H "Content-Type: application/json" \
-H 'Authorization: Bearer PROD_ACCESS_TOKEN' \
"https://api.mercadopago.com/users/test_user?access_token=#ACCESS_TOKEN DEL USUARIO#" \
-d '{"site_id":"MLA"}'
</code>


## Atencion

- En el curl reemplazar #access_token del usuario# (incluyendo los hash tambien) por el token nuestro que pegamos en credenciales.php

- Una vez pegado el token alli, copiamos todo el CURL y lo pegamos en la terminal/bash.

Esto nos devuelve lo siguiente :

- Nickname
- Password
- Site_status
- email

Estos datos que obtenemos, podemos tomarlo como el usuario vendedor. Lo siguiente que haremos es:
- copiar el email e iniciar sesion con ese usuario de prueba en Mercado Pago.
- Obtener el ACCESS TOKEN del usuario de prueba y reemplazarlo por la credencial que teniamos en "credenciales.php".

Guardamos.

Para obtener el usuario comprador haremos lo mismo que hicimos con el usuario vendedor. Copiamos y pegamos el mismo CURL sin modificar nada para que nos genere otro usuario. Obtendremos lo mismo :

- Nickname
- Password
- Site_status
- email

Estamos en condiciones de levantar el proyecto en localhost.

Hacemos click en comprar y tenemos dos opciones :

1) Ingresar con mi cuenta de mercado pago ( Usuario comprador para testing que generamos)
    <ul>a) Ingresamos email y password y, como usuario ya logueado, seguir la compra con:
    <ul>
        <li>I - Tarjeta debito - credito</li>
        <li>II - Efectivo</li>
    </ul>
    </ul>

2) Modo invitado
<ul>
    <li>a) Nueva tarjeta y simular pago</li>
    <li>b) Efectivo</li>
    </ul>

Para cualquiera de los casos, podemos excluir algun medio de pago o modificar la cantidad de cuotas.


## Tarjetas de prueba 

### VISA

- Numero : 4509 9535 6623 3704

- Vencimiento : 11/25

- CVV : 123

- Nombre : cualquiera

- DNI : Cualquiera

### American Express

- Numero : 3711 803032 57522

- Vencimiento : 11/25

- CVV : 1234

- Nombre : cualquiera

- DNI : Cualquiera

### Mastercard

- Numero : 5031 7557 3453 0604

- Vencimiento : 11/25

- CVV : 123

- Nombre : cualquiera

- DNI : Cualquiera
##

### Les dejo tambien un link de YouTube como base guia tambien
https://www.youtube.com/watch?v=S35KFp23HH4&list=PLLdQjTnpjYBLHozKgp3KG5MSCcfxTgO9V



### Espero y deseo que les haya sido util

- - - ##### <em> @ACaminos </em>

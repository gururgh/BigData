# Big-Data

# Acceso Mediante Reconocimiento Facial.

### Cool Matú Miguel Alejandro.
### Gurubel Romero Javier Jeremias.
### Suarez Alonzo Fernando Enrique.

# Descripción general.

## Este proyecto se lleva a cabo para ayudar a las personas a mantener sus bienes seguros, está diseñado con ayuda de dos placas de pruebas como base, la ESP32CAM y el NodemCU, los cuales permiten o deniegan el acceso a usuarios a determinadas áreas.


# Diagrama de flujo de datos.

## Se recolectara información mediante los sensores (distancia, luminosidad, cámara).

## Dependiendo de las entradas se determinara la función a realizar:

### En el caso de la luminosidad, se leerá el valor de luminosidad del sensor y se enviará al NodemCU, para ser comparado con el valor de la distancia.

### Para la cámara, se mandará un stream de video, el cual será “monitoreado” por el ESP32CAM en busca de caras conocidas/desconocidas.

### El sensor ultrasónico, nos ayudará para calcular la distancia del usuario a nuestro dispositivo, esta distancia se enviará al NodemCU para comparar con el valor de distancia.

### Una vez recolectada la información del sensor de luminosidad y el ultrasónico, el relevador encargado de controlar el encendido de las luces puede estar en los siguientes estados.

#### -Cerrado: cuando la luminosidad es muy baja y la distancia es menor a 1 metro.
#### -Abierto: cuando la luminosidad es alta y la distancia menor a 1 metro.
#### -Abierto: cuando la luminosidad es baja y la distancia mayor a 1 metro.
#### -Abierto: cuando la luminosidad es alta y la distancia mayor a 1 metro.

### El stream capturado de la cámara realizará un verificacion del rostro “leído”, dependiendo de si este se reconoce o no, el relevador estará en alguno de los siguientes estados:

#### -Cerrado: cuando la cara ha sido reconocida por el sistema.
#### -Abierto: cuando la cara no ha sido reconocida. 

### La información recolectada por los sensores será recolectada, concatenada y enviada en formato JSON a nuestra API, la cual guardará la información en la base de datos de nuestra página WEB.


### La base de datos puede ser consultada, para ser su visualización en las gráficas requeridas.

# Las 5 V´s del Big Data 

## + Variedad: 
### Nuestro proyecto procesa datos como luminosidad, distancia y la llave de acceso (Cara del usuario), todo lo anterior será validado y en dado caso enviado a la Base de Datos.

## + Velocidad:
### Nuestro proyecto es muy eficiente en cuanto la captura de rostros, captura el rostro un número determinado de veces  y permite o niega el acceso. 

## + Volumen:
### En cuanto al volumen es determinado por el número de usuarios e imágenes de usuario  ya que contiene 5 capturas variadas del rostro y permite a un número indefinido de usuarios.

## + Veracidad:

 ### El stream de nuestra cámara se analiza y se verifica antes de permitir el acceso, la imagen del rostro del usuario es comparada con los rostros previamente agregados, para minimizar la transferencia de información innecesaria.



## + Valor: 

### Los datos que más relevancia tienen son los de acceso, ya que estos son los que nos pueden ayudar a monitorear los accesos o intentos de accesos a determinadas áreas.


# Diagrama ETL
### + Extracción: Obtendremos información de nuestros sensores, en nuestro caso, nos servirán los sensores de distancia y luminosidad, al igual que obtendremos del stream de la cámara la cara del usuario que funcionará como llave de acceso.
### + Transformación: Al obtener los datos de la luminosidad, la distancia y el rostro del usuario, estos son transformados en una señal, esta señal activara un LED de color verde si cumplen con los requisitos necesarios, permitiendole el acceso al usuario, si no, activará un LED rojo, dando a entender que nego el acceso.

### + Load (carga): Esta señal lo que hace es permitir o negar el acceso del usuario, abriendo o manteniendo cerrada la cerradura de la puerta, al igual que el dato de la luminosidad es enviada a una API en la cual se graficara para que el administrador de la página pueda llevar un control de ello, al igual que el usuario es guardado en la base de datos.

![image](https://user-images.githubusercontent.com/78035963/111945695-c1c0c000-8a9f-11eb-891e-24eda9f325de.png)


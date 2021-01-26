# BigData

# Acceso mediante reconocimiento facial.

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

###Una vez recolectada la información del sensor de luminosidad y el ultrasónico, el relevador encargado de controlar el encendido de las luces puede estar en los siguientes estados.

#### -Cerrado: cuando la luminosidad es muy baja y la distancia es menor a 1 metro.
#### -Abierto: cuando la luminosidad es alta y la distancia menor a 1 metro.
#### -Abierto: cuando la luminosidad es baja y la distancia mayor a 1 metro.
#### -Abierto: cuando la luminosidad es alta y la distancia mayor a 1 metro.



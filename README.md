# BigData

# Acceso mediante reconocimiento facial.

### Cool Matú Miguel Alejandro.
### Gurubel Romero Javier Jeremias.
### Suarez Alonzo Fernando Enrique.

# Descripción general.

## Este proyecto se lleva a cabo para ayudar a las personas a mantener sus bienes seguros, está diseñado con ayuda de dos placas de pruebas como base, la ESP32CAM y el NodemCU, los cuales permiten o deniegan el acceso a usuarios a determinadas áreas.


#Diagrama de flujo de datos.

## Se recolectara información mediante los sensores (distancia, luminosidad, cámara).

## Dependiendo de las entradas se determinara la función a realizar:

En el caso de la luminosidad, se leerá el valor de luminosidad del sensor y se enviará al NodemCU, para ser comparado con el valor de la distancia.


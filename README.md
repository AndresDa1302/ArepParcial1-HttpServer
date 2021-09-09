# Parcial primer corte
El servidor httpserver escucha las solicitudes del servidor fachada que es la que utiliza las operaciones dentro de esta aplicacion

## Autor
* Andres Felipe Davila Gutierrez

## Contrucción
* Visual Studio Code - Editor de código y ambiente de desarrollo
* Maven - Gestor de dependencias


# Lenguajes
* HTTP
* JavaScript
* Java
* Css

## Utilización
Esta aplicación se encuentra desplegada en Heroku

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://parcialarephttp.herokuapp.com)


Construir una  aplicación web usando sockets que reciba un número y una cadena de tres caracteres. La cadena puede ser una de tres opciones: "cos", "sin", "tan". La aplicación asume que el número que recibe está en radianes y muestra el valor de la función trigonométrica correspondiente.
Arquitectura:
La aplicación tendrá tres componentes distribuidos: Una fachada de servicios, un servicio de calculadora trigonomética, y un cliente web (html +js).
Los servicios de la fachada y de la calculadora deben estar desplegados en dynos diferentes.
El cliente se descarga desde un servicio en la fachada (Puede entregar el cliente directamente desde un método no es necesario que lo lea desde el disco).
La comunicación se hace usando http y las respuestas de los servicios son en formato JSON.
La caculadora trigonométrica (TrigCalculator) es la que hace el computo real de las funciones. La fachada de servicios (ServiceFacade) solo delega el ccomputo al TrigCalculator.
Su diseño debe soportar la composición de nuevas operaciones para modificar servicios existentes o componer nuevos servicios. Por ejemplo, piense que en el futuro podemos solicitar que se creen nuevos servicios sobre  el API web, es decir,  debe ser fácilmente extensible.
El diseño de los servicios WEB debe tener en cuenta buenas prácticas de diseño OO.
Despliegue los servicios en Heroku en dynos separados.
Los llamados al servicio de calculadora desde el cliente deben ser asíncronos usando el mínimo JS prosible. No actualice la página en cada llamado, solo el resultado.
El API de la fachada será
[url de la app en Heroku]/calculadora : Este servicio entrega el cliente web en formato html + js.
[url de la app en Heroku]/[operación de tres letras: cos, sin, tan]?[numero] : retorna el valor solicitado en formato JSON
El API de la calculadora será
[url de la app en Heroku]/[operación de tres letras: cos, sin, tan]?[numero] : retorna el valor solicitado en formato JSON
Asegúrese de retornar los encabezados correctos en HTTP y de responder mensajes válidos de HTTP ante solicitudes inesperadas (Hroku hace algunas solicitudes iniciales al publicar la aplicación)
Entregue dos repositorios GITHUB, uno para la fachada y otro para la calculadora, y entregue el enlace a las dos app Heroku, uno para la fachada y otro para la calculadora. Incluya en el README la información necesaria  para verificar que los requerimientos servicios individuales.
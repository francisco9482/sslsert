# sslsert
Las políticas de SSL convergen en localhost con la adecuada configuración

## Encuestas SSL

Se realizaron varias encuestas para examinar las conexiones SSL que brindaron información sobre el estado de SSL/TLS en la naturaleza.
En 2012, había un subprograma Shockwave (SWF) del lado del cliente desarrollado por [3] y alojado en Facebook que intentaba detectar un certificado falsificado. El applet imitó el protocolo de enlace SSL del navegador al abrir una conexión de socket al sitio de Facebook. El applet registra el protocolo de enlace SSL e informa la cadena de certificados observada a los servidores de registro.

Entre noviembre de 2009 y abril de 2011, se realizó un análisis de la PKI x.509 utilizando la metodología de mediciones activas y pasivas. El escaneo activo en la lista de Alexa Top 1 Million Hosts usaba nmap y OpenSSL para sondear la cadena de certificados completa y las propiedades de conexión TLS/SSL. El escaneo pasivo usó procesamiento de dos pasos utilizando Bro como herramienta de procesamiento TLS/SSL de forma independiente del puerto.
Los resultados de las encuestas SSL/TLS anteriores para las condiciones anormales de un certificado se pueden resumir a continuación. Estos resultados se utilizarán como guía para redactar las [reglas especificadas](https://github.com/aaran1/genexis) de la política.

• El tamaño de los certificados es pequeño, inferior a un kilobyte.
• Las cadenas de certificados tienen una profundidad de uno sin certificados intermedios. Si hay más de una cadena, generalmente es una cadena rota, no se emite un certificado de CA raíz, el certificado en la cadena ha caducado o no se pueden verificar sus firmas en la cadena.
• Sujetos de certificados con organización de emisor vacía y uso de dominios no relacionados, como direcciones IP en [192.168.l.254](https://isproto.com/192-168-1-254/), el dominio comodín*. El valor puede pertenecer al nombre del dispositivo, software proxy, antivirus, cortafuegos, software de control parental,
adware y malware. Puede tener un valor fraudulento como "Facebook" o un nombre común predeterminado como 'plesk', 'localhost', 'localhost.localdomain' para un certificado autofirmado usando la biblioteca OpenSSL.

## Método no intrusivo propuesto para proxy SSL/TLS

Esta investigación se centrará en contratar un proxy de reenvío no intrusivo con funciones de seguridad adaptables para conexiones SSL/TLS. La metodología utilizada no requiere que los clientes instalen un archivo ejecutable binario o una extensión de navegador personalizada para examinar las conexiones y los certificados SSL. El único requisito por parte del usuario es establecer la configuración del proxy para que apunte al proxy. Es escalable a un gran número de usuarios normales con pocos conocimientos técnicos.

## Política de seguridad SSL/TLS

La política de seguridad es la base del componente de análisis y se crea bajo las características de atributos SSL/TLS para pruebas estáticas y dinámicas. Los atributos estáticos consisten en la lista de versiones para SSL/TLS, conjuntos de cifrado, certificados raíz, intercambios de claves, cifrados y hashes. Estos atributos se almacenan en una base de datos para el componente de análisis. [192.168.o.1](https://inuchat.net/ip/192-168-0-1/)

## Atributos estáticos

Conjuntos de cifrado
 
Se requiere una colección de conjuntos de cifrado para diagnosticar el conjunto de cifrado admitido en un host remoto mediante SSL/TLS. Hay 357 conjuntos de cifrado que se han recopilado hasta ahora para SSL v2.0 hasta TLS v1.2 de RFC y documentación de OpenSSL. Estos conjuntos de cifrado se clasifican según su versión SSL/TLS (SSL v2.0, TLS v1.0, etc.), intercambios de claves, algoritmos de cifrado y algoritmos de firma, así como sus nombres equivalentes en OpenSSL.

Por ejemplo, el conjunto de cifrado TLS_RSA_WITH_RC4_128_MD5 también se conoce como RC4-MD5 en OpenSSL. Sin embargo, no todos los conjuntos de cifrado tienen equivalencias OpenSSL. También se captura más información, como la codificación de 2 bytes. Ejemplo para SSL, el primer byte es 0x00 y el segundo byte es la representación hexadecimal del número del conjunto de cifrado

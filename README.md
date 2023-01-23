
# Implantación del servicio DNS en el entorno de trabajo
#### SER - Guillermo Bárcena López, Francisco Mejías de Matos y Alvaro Jimenez talaverón <br>
![Foto de la portada](https://github.com/guillermo2005200/ProyectoSR-BLG-2223/blob/main/imagenes/download%20(6).jpeg)
---
Este es un proyecto el cuál hemos realizado con el fin de poner en práctica todo lo aprendido sobrer DNS y resolucion de nombres. Para explicarlo utilizaremos el guión proporcionado por nuestro profesor Jose Luis Rodríguez.
---
1. **Figura con la infraestructura del entorno** <br>
La infraestructura que hemos desarrollado ha sido la siguiente:<br>
![Infraestructura](https://github.com/guillermo2005200/ProyectoSR-BLG-2223/blob/main/imagenes/DiagramaProyectoDNS.png)
[Enlace al diagrama](https://drive.google.com/file/d/1OGA-V4_20N8UnIGlXNveywVdCZCEsaSm/view?usp=sharing)
---
2. **Tener Instalado el servicio DNS en DEbian5-pruebas y en Debian6-pruebas** <br>
Lo debemos tener instalado en los dos equipos para dividir la resolución de nombres por igual y repartirse el trabajo entre los dos, además nos proporciona una resistencia mayor a los fallos, ya que, si falla un servidor estará el otro para suplirlo.<br>
Esto se puede comprobar mediante el comando "sudo service bind9 status" y debería salirnos este resultado.
![status](imagenes/status.PNG)
---
3. **Espacio de nombres** <br>
Este es nuestro espacio de nombres que explicaremos a continuación:<br>
![Espacio de nombres](imagenes/espacionombres.PNG)
[Enlace al diagrama](https://drive.google.com/file/d/1t0toJ2aAeeb92nNTWth2CG8ceuFkpZOH/view?usp=sharing)<br>
Todas las máquinas virtuales de las que disponemos, es decir las DebianX-pruebas estan dotadas de su correspondiente nombre, además de las maquinas adicionales para completar la red. Los equipos de cada zona no han sido colocados al azar, ya que tienen influencia en el balanceo de carga del que hablaremos en el punto 7. <br>
Llegamos, y superamos los dominios hasta tercer nivel en la zona c, donde un ejemplo sería: ("PC1.almacen.equipos.produccion.com). <br>
Hablando de que hemos puesto en cada zona:
- En la zona A, basicamemnte se encuntran todos los servidores, excepto los DNS.
- En la zona B, hemos colocado los routers de los que disponemos.
- EN la zona C, hemos colocado todos los equipos y los servidores DNS.

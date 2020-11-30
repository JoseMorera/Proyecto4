---
### Universidad de Costa Rica
#### IE0405 - Modelos Probabilísticos de Señales y Sistemas

Segundo semestre del 2020  
Proyecto 4

---

* Estudiante: **José Alberto Morera Guzmán**
* Carné: **B85431**
* Grupo: **1**
---
#### Documente la solución 
Para la primera parte de las asignaciones, se llevó a cabo una simulación del sistema de comunicaciones utilizando una modulación QPSK, para esto, se tomó como base el archivo P4.ipynb brindado por el profesor, en el cual se utilizó una modulación BPSK. Las funciones fuente_info, rgb_a_bit y bits_a_rgb quedaron intactas ya que son igulaes para ambas modulaciones.  
En la función modulador se crearon dos distintas portadoras, una para I y otra para Q, también dos señales senal_Tx_I y senal_Tx_Q, las cuales fueron sumadas al final de la función. El método o la lógica utilizada para separar los bits de 2 en 2 (y mandarlos a I y Q según corresponda) fue convertir el vector de bits en una matriz de dos columnas de manera de que todos los que corresponden a I vayan en la primera columna y todos los que correspondan a Q en la segunda columna, luego se aplica el mismo for para asignar formas de onda para ambas columnas, después de este for se suman ambas señales como se mencionó anteriormente y se obtiene una sola señal. finalmente se calcula la potencia promedio de la señal modulada y se retornan la senal_Tx (suma de ambas señales Q e I), Pm, portadora_I, portadora_Q y moduladora.  
Para la siguiente función, canal_ruidoso, se recibe la señal senal_Tx, la potencia promedio de la señal modulada y la relación señal-a-ruido del canal. A partir de este último parámetro se calcula la potencia del ruido generado por el canal de acuerdo con la fórmula vista en la nota teórica.  
Para la función demodulador se crean producto_I, producto_Q, Ep_I y Ep_Q cumplen con funciones casi idéticas a las que se tenían en el P4.ipynb base, en el criterio de decisión por detección de energía se crean dos if y dos for, uno para I y otro para Q.  
Finalmente se le brinda la frecuencia de la portadora (en este caso se asigna 5kHz), el número de muestras por periodo (20) y la relación señal ruido (SNR) que en este caso se le asignó un valor de 0, lo que quiere decir que la potencia de la señal y la potencia del ruido son iguales, según la fórmula vista. Las imágenes transmitida y recibida fueron las siguientes, con un total de al rededor de 500 errores para un SNR=0.
![Imgur](https://i.imgur.com/oJc7cls.png)  
Las señales obtenidas fueron las siguientes, la lima corresponde a la señal modulada por QPSK, la azul corresponde a la señal Tx + ruido y la color oro corresponde la señal demodulada.
![Imgur](https://i.imgur.com/A9KX8xV.png)


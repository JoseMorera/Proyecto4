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
En las pruebas de estacionaridad y ergodicidad a la señal modulada senal_Tx se crea un algoritmo que nos brinde los resultados esperados según la teoría y la nota teórica del proyecto para la señal modulada por QPSK, en resumen, se obtienen todas las posibles combinaciones según los valores que puede tomar A (1 y -1) y para todos los tiempos del muestreo, estos valores se guardan en una matriz llamada X_t, se grafican y se obtienen los valores teóricos y esperados, para la media se obtiene el siguiente gráfico.
![Imgur](https://i.imgur.com/K9G5O0A.png)  
Como se puede observar, el valor esperado teórico coincide con el valor esperado de las realizaciones (para las cuatro curvas mostradas), el cual es constante, además se sabe por teoría que un proceso aleatorio se dice que es estacionario si ninguna sus propiedades estadísticas cambian con el tiempo, por lo tanto se puede concluir que esta señal es estacionaria en sentido amplio, también se sabe que la ergodicidad establece la igualdad entre el promedio estadístico y el promedio temporal de un proceso aleatorio, algo que se puede deducir de esta gráfica.  
Finalmente, para la densdad espectral de potencia, se puede observar que el pico más importante está ubicado en 5kHz, la cual fue la frecuencia fc definida, los otros picos, que se encuentran a ambos lados de 5kHz son los compenentes de frecuencia de la moduladora.
![Imgur](https://i.imgur.com/MlTkExF.png)

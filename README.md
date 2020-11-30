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
Hola



![Imgur](https://i.imgur.com/A9KX8xV.png)


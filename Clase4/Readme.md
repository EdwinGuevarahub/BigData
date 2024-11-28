## Hipótesis probadas

1. **Número de clases diferente de 10:**  
   Se validaron mediante una función `countClassesFromOneHot`, la cual imprime un array con la cantidad de clases y la distribución de la misma, obteniendo 10 clases con las siguientes cantidades:  
   - 0: 6424  
   - 1: 7314  
   - 2: 6502  
   - 3: 6648  
   - 4: 6289  
   - 5: 5879  
   - 6: 6375  
   - 7: 6743  
   - 8: 6363  
   - 9: 6463  

2. **Red Neuronal demasiado compleja, por ende sobreentrenamiento:**
   Debido a que alcanza el 90% de accuracy en la primera, a lo sumo segunda iteración, se ajustó la red neuronal experimentando con lo siguiente ademas de graficar los valores de acc y loss en funcion de la cantidad de epocas:
   
   ![image](https://github.com/user-attachments/assets/4c8dd863-c35a-48c3-af36-69f97b757037)  
   - **Añadir capas de drop:** No se evidenció nada concluyente y además tardaba más el proceso de entrenamiento.  
   - **Disminuir la complejidad de la red disminuyendo la cantidad de filtros:** Esto aceleraba la "convergencia", garantizando que en la primera iteración se llegaba al 90% con delta bastante pequeño.  
   - **Disminuir la complejidad de la red quitando 1 capa convolucional y 1 capa de pooling:** Esto hizo que la diferencia entre el error de entrenamiento y de prueba fuese menor desde la primera iteración en comparación al resto de pruebas.  
   - **Reemplazar avgpooling por maxpooling:** No se evidenció ninguna repercusión.  
   - **Modificar la proporción entre datos de entrenamiento y datos de prueba:** No se evidenció ninguna repercusión.  

   Se añadió código para graficar los valores de error y accuracy en función de la cantidad de épocas. De ahí se pudo evidenciar que la primera ejecución bastaba para obtener un accuracy del 90%.

4. **Clase faltante en subset de pruebas:**  
   Se imprimieron las clases para el dataset tanto de entrenamiento como de prueba, no se evidenció que este estuviera desbalanceado.

### Conclusiones

1. Ninguna de las hipótesis descritas en la sección anterior pudo ayudar en la mejora o siquiera modificación del valor de accuracy.  
2. El accuracy no pudo ni ser modificado, siempre terminó convergiendo hacia el 90%.



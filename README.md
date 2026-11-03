# Investigación de Operaciones (IO)

Aquí voy guardando mis notebooks y ejercicios de Investigación de Operaciones. En cada uno dejo el código, las gráficas y una explicación paso a paso de lo que hago y de los resultados que obtengo.

## Notebooks disponibles

### Tutorial de NetworkX

En este notebook resuelvo tres problemas de redes: árbol de expansión mínima, ruta más corta y flujo máximo. Primero construyo la red con los datos del ejercicio, después la resuelvo con NetworkX y dibujo la solución para ver cómo queda.

Voy explicando los comandos conforme los uso. También incluyo las imágenes del enunciado y las comprobaciones de cada resultado.

- [Ver el notebook en GitHub](notebooks/TutorialNetworkx.ipynb).
- [Abrir el notebook en Google Colab](https://colab.research.google.com/github/Mar9718/Investigacion-de-operaciones/blob/main/notebooks/TutorialNetworkx.ipynb).

En el primer inciso busco conectar todos los nodos con el menor costo total. En el segundo encuentro las rutas más cortas del nodo 1 al nodo 7. En el tercero calculo el flujo máximo con Edmonds–Karp y reviso que respete las capacidades y que el flujo que entra a cada nodo intermedio sea igual al que sale. Para comprobar que es máximo, comparo su valor con la capacidad de un corte mínimo. También muestro distintas formas de repartir el flujo que alcanzan ese mismo valor.

### Cadenas absorbentes: laberinto y tablero (Tarea 5)

En este notebook resuelvo dos ejercicios mediante simulación. Incluyo el enunciado y la figura de cada uno, seguidos de su código, la comparación analítica y una interpretación de los resultados.

En el laberinto elijo una puerta al azar y sigo hasta llegar a la comida o a la descarga. Como el enunciado no fija el compartimento inicial, calculo las probabilidades desde los estados 0 a 6 y destaco el inicio en 0. En el tablero comienzo en 1, aplico las escaleras y serpientes sin añadir tiradas y termino al alcanzar o rebasar 20. También aclaro cómo cambia la respuesta si se exige llegada exacta.

Uso un millón de trayectorias completas por caso y la semilla `20261102`. Comparo las estimaciones con los valores analíticos y calculo el error estándar Monte Carlo. Para el promedio de tiradas también muestro un intervalo aproximado al 95%.

- [Ver el notebook en GitHub](notebooks/IO_Tarea5_Cadenas_absorbentes_simulacion.ipynb).
- [Abrir el notebook en Google Colab](https://colab.research.google.com/github/Mar9718/Investigacion-de-operaciones/blob/main/notebooks/IO_Tarea5_Cadenas_absorbentes_simulacion.ipynb).
- [Ver el enunciado original](materiales/Tarea5_Cadenas_absorbentes/enunciado_original.png).

Desde 0 obtengo una probabilidad simulada de **0.499697**, frente al valor exacto **0.5**. Para el tablero obtengo **6.894569 tiradas**, frente a **6.898346651** analíticas, bajo la regla de alcanzar o rebasar 20.

## Cómo ejecuto los notebooks

Abro los notebooks en Google Colab con los enlaces de arriba y ejecuto las celdas de principio a fin. También puedo abrirlos en Jupyter con Python 3.

Los ejercicios de redes usan **NetworkX** y **Matplotlib**. Si necesito instalarlos en el notebook, ejecuto:

```python
%pip install networkx matplotlib
```

La simulación de cadenas absorbentes usa **NumPy** y **Numba**:

```python
%pip install numpy numba
```

Antes de repetir una ejecución completa, reinicio el kernel y ejecuto todas las celdas en orden. Las figuras de los enunciados están incluidas dentro de los notebooks.

## Sobre los ejercicios

En los ejercicios de redes trabajo con los datos del enunciado. Para el árbol de expansión mínima tomo la red sin dirección. Para las rutas más cortas y el flujo máximo sí respeto la dirección de los arcos.

Al dibujar las redes uso semillas para que los nodos queden en las mismas posiciones cada vez que ejecuto el código. Esto solo fija cómo se ve la gráfica; los costos y las capacidades siguen siendo los del ejercicio.

En la simulación de cadenas absorbentes, la semilla fija los movimientos aleatorios. Cada recorrido continúa hasta la absorción; las probabilidades y los promedios son estimaciones sujetas a variación Monte Carlo.

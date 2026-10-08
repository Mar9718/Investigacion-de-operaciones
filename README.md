# Investigación de Operaciones (IO)

Aquí voy guardando mis notebooks y ejercicios de Investigación de Operaciones. En cada uno dejo el código, las gráficas y una explicación paso a paso de lo que hago y de los resultados que obtengo.

## Notebooks disponibles

### Tutorial de NetworkX

En este notebook resuelvo tres problemas de redes: árbol de expansión mínima, ruta más corta y flujo máximo. Primero construyo la red con los datos del ejercicio, después la resuelvo con NetworkX y dibujo la solución para ver cómo queda.

Voy explicando los comandos conforme los uso. También incluyo las imágenes del enunciado y las comprobaciones de cada resultado.

- [Ver el notebook en GitHub](notebooks/TutorialNetworkx.ipynb).
- [Abrir el notebook en Google Colab](https://colab.research.google.com/github/Mar9718/Investigacion-de-operaciones/blob/main/notebooks/TutorialNetworkx.ipynb).

En el primer inciso busco conectar todos los nodos con el menor costo total. En el segundo encuentro las rutas más cortas del nodo 1 al nodo 7. En el tercero calculo el flujo máximo con Edmonds–Karp y reviso que respete las capacidades y que el flujo que entra a cada nodo intermedio sea igual al que sale. Para comprobar que es máximo, comparo su valor con la capacidad de un corte mínimo. También muestro distintas formas de repartir el flujo que alcanzan ese mismo valor.

### Ejemplo básico de un grafo

Este es un ejemplo sencillo en el que agrego seis nodos y sus conexiones a un grafo no dirigido. Después lo dibujo con las etiquetas de los nodos. Me sirve para mostrar cómo se construye una red con NetworkX.

- [Ver el notebook en GitHub](arbol_.ipynb).
- [Abrir el notebook en Google Colab](https://colab.research.google.com/github/Mar9718/Investigacion-de-operaciones/blob/main/arbol_.ipynb).

Al ejecutarlo, la figura se guarda como `GraphUndirected.png`. Aquí solo construyo y dibujo el grafo; el cálculo del árbol de expansión mínima está en el tutorial.

## Cómo ejecuto los notebooks

Uso Python, NetworkX y Matplotlib. Para ejecutar los notebooks, los abro en Google Colab con los enlaces de arriba.

Ejecuto las celdas de arriba hacia abajo, porque voy usando los grafos y las variables que definí en las anteriores. Si en Colab necesito instalar las bibliotecas, ejecuto `%pip install networkx matplotlib` en una celda.

Las imágenes del enunciado y las gráficas del tutorial ya están dentro del notebook.

## Sobre los ejercicios

En cada problema trabajo con los datos de la red del enunciado. Para el árbol de expansión mínima tomo la red sin dirección. Para las rutas más cortas y el flujo máximo sí respeto la dirección de los arcos.

Uso semillas al dibujar las redes para que los nodos queden en las mismas posiciones cada vez que ejecuto el código. Esto solo fija cómo se ve la gráfica; los costos y las capacidades siguen siendo los del ejercicio.

# Segmentación de colores en imágenes aplicando clustering no supervisado con 'k-means'.

---

### Creador:
- Wilbert Vong

---

#### **Este trabajo consiste en la detección y segmentación de colores en imágenes aplicando el clustering no supervisado 'k-means'.**

#### Este tipo de procesos convierte cada uno de los píxeles de la imagen, ya sea en el espacio de color 'RGB' *(Red, Green, Blue)*, o 'HSV' *(Hue, Saturation, Value)*, o HSL *(Hue, Saturation, Lightness)*, o 'LAB' *(Lightness, A=Green to Red, B=Blue to Yellow)*, en un vector. Luego de ello, cada vector es tomado para ser un elemento a segmentar aplicando el algoritmo de clustering no supervisado 'k-means'.

---

## **Funcionamiento del Clustering No Supervisado 'K-Means'**:

El algoritmo K-means es un método de agrupamiento (clustering) no supervisado que organiza un conjunto de datos en 
$𝐾$ grupos (o clusters) según la similitud entre los puntos. Aquí detallo la manera en que se aplica:

#### *Inicialización*:
Se elige un número $𝐾$ de clusters (grupos) que se desea crear. Luego, se seleccionan aleatoriamente $𝐾$ centroides iniciales, que son puntos en el espacio que representan temporalmente el centro de cada cluster.

#### *Asignación de puntos*:
Cada punto de datos se asigna al cluster cuyo centroide esté más cerca, utilizando una métrica de distancia, donde la más aplicada es la **distancia euclidiana**, cuya fórmula es la siguiente:

$$
d(x, y) = \sqrt{\sum_{i=1}^{n} (y_i - x_i)^2}
$$

Donde:

* $x = (x_1, x_2, \dots, x_n)$ y $y = (y_1, y_2, \dots, y_n)$ son los dos puntos en el espacio.
* $x_i$ y $y_i$ son las coordenadas de los puntos $x$ y $y$ en la dimensión $i$.
* $d(x, y)$ es la distancia euclidiana entre los puntos $x$ y $y$.

#### *Actualización de centroides*:
Después de asignar todos los puntos a clusters, se recalculan los centroides. El nuevo centroide de cada cluster se calcula como el promedio de todos los puntos asignados a ese cluster.
La fórmula para actualizar el centroide de un cluster es:

$$
\mu_j = \frac{1}{|C_j|} \sum_{x \in C_j} x
$$

Donde:

- $\mu_j$ es el nuevo centroide del cluster $j$.

- $C_j$ es el conjunto de puntos que pertenecen al cluster $j$.

- $|C_j|$ es el número de puntos en el cluster $j$.

+ $x$ son los puntos de datos asignados al cluster $j$.

La suma $\sum_{x \in C_j} x$ calcula la suma de todas las coordenadas de los puntos en $C_j$, y luego se divide por el número total de puntos en ese cluster para obtener el promedio.

#### *Iteración*:
El proceso de asignar puntos a clusters y recalcular los centroides se repite hasta que los centroides ya no cambien significativamente o hasta que se alcance un número máximo de iteraciones. Este estado se denomina *convergencia*.

---

**Usos prácticos**:

*Análisis de mercado y tendencias de productos*: Las empresas pueden usar lo información de los colores para analizar las preferencias de los consumidores y desarrollar productos en colores que estén de moda para cierto tipo de clientes.

*Optimización de anuncios publicitarios y marketing visual*: Se puede usar este tipo de análisis para crear campañas publicitarias más impactantes y dirigidas, personalizando anuncios según los colores que más atraen a sus clientes potenciales. Por ejemplo, se pueden optimizar anuncios que usan combinaciones de colores que mejor se alineen con los gustos de diferentes segmentos de usuarios.

*Mejora de la experiencia de usuario en E-Commerce*: Las plataformas de E-Commerce pueden utilizar la segmentación de colores para mejorar la experiencia de compra al recomendar productos de colores similares basados en las preferencias visuales de los usuarios.

*Gestión de inventarios y visualización de productos*: Aplicando la segmentación de colores se puede ayudar a organizar y gestionar los productos por colores en los inventarios. Esto no solo mejora la presentación visual de los productos, sino que también puede facilitar la toma de decisiones en términos de reposición de stock.

---

## Notebooks

[Detección y segmentación de colores con el Clustering no supervisado con 'k-means'](https://colab.research.google.com/drive/1toVQribmDpOV54OwMU38iu3YmiuiY9JL?usp=sharing)

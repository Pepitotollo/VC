El video utilizado en la tarea, además del entrenamiento y el data set se encuentras en el siguiente Drive.

Drive: https://drive.google.com/drive/folders/1qRWvBriHVL11vqBOdtsOXPU7QW8SeH7I?usp=drive_link

Tarea realizada por Noel Padrón Jiménez y Joel Rodríguez González

Proyecto de Visión por Computador

Descripción:

En esta práctica, el objetivo es desarrollar un prototipo que procese videos para la detección y seguimiento de personas y vehículos. Más concretamente se debe realizar el entrenamiento para un modelo que reconozca las matrículas de los coches. 
La conclusión de la detección se visualizará en un vídeo, junto a un archivo csv que muestra los resultados del seguimiento.

1. Detectar y seguir personas y vehículos.
   
Para este apartado nos apoyamos en el modelo preentrenado de YOLO 'yolo11n.pt'

Ejemplo de detección de coches:

![imagen_apartado_1](https://github.com/user-attachments/assets/b81bca4c-d580-4c4a-b6f1-eb305c16857d)

Ejemplo de detección de personas:

![imagen_apartado_1_2](https://github.com/user-attachments/assets/5a312de9-fb43-4441-bdc5-0aaf6e765ed6)

2. Detectar y reconocer texto en matrículas.

Para este apartado de la tarea se ha realizado un entrenamiento con un dataset de imágenes de coches en los que se visualiza con claridad la matrícula. El dataset posee aproximadamente 450 imágenes con sus respectivas anotaciones de imagenes en formato txt, tal y como se indica en el guión de la práctica.

![imagen_apartado_2](https://github.com/user-attachments/assets/5318e113-0ab4-40f8-97af-61c72c956c74)

3. Contar las instancias de cada clase detectada.

La variable total_cars cuenta los coches detectados, guardándolos en un diccionario. Para cada detección de 'car', se verifica si ya está rastreado calculando la distancia con coches anteriores. Si es un coche nuevo, se asigna un identificador único ("car_X") y se incrementa total_cars.

La variable total_people cuenta las personas detectadas. Para cada detección de 'person', se verifica si ya está rastreada. Si es una persona nueva, se le asigna un identificador único ("person_X") y se incrementa total_people.

Al final de la ejecución, se imprime el total de coches y personas detectados

4. Guardar un archivo CSV con la información de las detecciones.

Cada detección de coche o persona se guarda en el diccionario results_list, que contiene información como el número de cuadro (frame), tipo de objeto (tipo_objeto), confianza (confianza), identificador de seguimiento (identificador_tracking), coordenadas de la caja delimitadora (x1, y1, x2, y2), y campos relacionados con la detección de matrícula.

Cada vez que se detecta una matrícula en un coche, el código actualiza la entrada correspondiente en results_list con la información de la matrícula (matricula_en_su_caso, texto_matricula y coordenadas mx1, my1, mx2, my2).

Una vez finalizada la detección y el procesamiento, el código convierte results_list en un DataFrame de pandas y lo guarda en un archivo CSV llamado resultados_deteccion.csv.

5. Principales dificultades.

Nuestro modelo es capaz de detectar y leer matrículas generalmente bajo condiciones que impliquen un vídeo a una velocidad no muy alta y que la calidad del mismo sea elevada.

Proyecto de Filtro Animado con Detección de Rostros y Efectos de Energía

Tarea realizada por Noel Padrón Jiménez y Joel Rodríguez González

Drive: https://drive.google.com/drive/folders/1YY00QwHe9IGmZkIes-seHlqaKCGcKwDM?usp=sharinghttps://drive.google.com/drive/folders/1YY00QwHe9IGmZkIes-seHlqaKCGcKwDM?usp=sharing

Descripción general:
Este proyecto utiliza OpenCV y dlib para detectar rostros en tiempo real desde la cámara web y aplicar efectos visuales. Cuando se detecta que la boca está abierta, el script aplica una distorsión en la cara y genera bolas de varios colores que se desplazan 
por la pantalla en direcciones aleatorias.

Funcionamiento del código.
A continuación, se describe cómo funciona cada sección principal del código:

Importación de Librerías:
Se utilizan cv2 (de OpenCV) para el procesamiento de imágenes y video, dlib para la detección de rostros y puntos faciales, y numpy para cálculos matemáticos.
Inicialización de Detección Facial:

Se utiliza dlib.get_frontal_face_detector() para detectar rostros.
El archivo shape_predictor_68_face_landmarks.dat es utilizado para identificar 68 puntos específicos en el rostro (como los ojos, nariz, boca, etc.).
Configuración del Video:

Se inicia la captura de video desde la cámara con cv2.VideoCapture().
Se utiliza cv2.VideoWriter() para guardar la salida en un archivo MP4 (resultado_video.mp4).
Funciones Personalizadas:

calcular_distancia(): Calcula la distancia entre dos puntos, útil para medir la apertura de la boca.
aplicar_distorsion(): Amplía y distorsiona la región de la cara cuando se detecta que la boca está abierta. La distorsión se ajusta para no salir del área visible del marco.
generar_bolas_energia(): Genera bolas de energía con colores y tamaños variables según la apertura de la boca:
Amarillo para aperturas leves.
Naranja para aperturas medias.
Rojo para aperturas considerables.
Verde para aperturas muy amplias.
Las bolas se mueven aleatoriamente y desaparecen si salen de la pantalla.

Bucle Principal:
Captura fotogramas en tiempo real y los convierte a escala de grises para la detección de rostros.
Para cada rostro detectado:
Determina si la boca está abierta midiendo la distancia entre los puntos superiores e inferiores de la boca.
Si la boca está abierta:
Se aplica un efecto de distorsión en la región facial.
Se generan bolas de energía que se mueven en direcciones aleatorias con colores basados en la apertura de la boca.

El video se muestra en una ventana en tiempo real y se guarda en un archivo de salida.
El programa se detiene al presionar la tecla q.

Requisitos
Python 3.x
opencv-python
dlib
numpy
Instalación de Dependencias

Asegurarse de que el archivo shape_predictor_68_face_landmarks.dat esté en la ruta correcta.
Ejecuta el script de Python:
bash
Copiar código
python nombre_del_script.py
El programa comenzará a capturar video desde tu cámara web. Abre la boca para activar los efectos visuales.

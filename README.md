# PLN-Proyecto Final

La salud mental es un tema que en la actualidad está siendo considerado como uno de los problemas sociales que afectan a cada vez más personas. 
Las redes sociales han permitido que podamos expresar nuestros pensamientos y emociones con una mayor libertad y Twitter es la plataforma más utilizada para esto.Esto permite que podamos obtener bases de datos con tweets para generar modelos que permitan detectar si un usuario pudiera tener depresión. Esto permitirá que se les pudiera identificar y asi poder ofrecerles el apoyo adecuado.
En este proyecto se proponen varios modelos que permitan detectar depresión a través de texto como SS3 y BERT. Además se realizaron pruebas con un modelo que permite traducir audio a texto Speechbrain. 


Como trabajo futuro se pretende crear un modelo que involucre una validación a través de la voz, video y texto escrito de una persona. 


### Dataset 

El dataset fue obtenido de 4 fuentes distintas ya que pudimos percatarnos que casi todas las oraciones contenian la palabra depresion, y por lo tanto el modelo iba a tener overfitting, este proceso puede visualizarse en https://docs.google.com/document/d/1ESw64C7C9L6zr-nKeDmi0CD6De8gAFJOyMwi_1TWkoQ/edit. Al final obtuvimos un dataset con 3000 registros y con una distribución apropiada. 



### Rendimiento de los modelos 
Para elegir los hiperparametros y para evaluar la efectividad del modelo se tomaron dos principales métricas. La primera es el accuracy del módelo, que es el porcentaje de clasificaciones correctas del total de clasificaciones, asi como el recall, que se calcula de la siguiente manera: 
### Recall = TP/(TP+FN)
### Precision = TP/(TP+FP)
### Accuracy= (TP+TN)/(TP+FN+TN+FP)
TP= True Positive, 
TN= True Negative,
FP= False Positive, 
FN= False Negative.
Se eligió el recall, ya que se está prediciendo la depresión de una persona. Es más importante minimizar los Falsos negativos, ya que puede ser peligroso no tratar un caso positivo, y que este se empeore.

Para poder ver el rendimiento de manera gráfica, se utilizó la herramienta de matriz de confusión.

### Modelos
#### SS3
El primer modelo que se utilizó fue el modelo SS3, introducido por primera vez en la sección 3 del paper cientifico "A text classification framework for simple and effective early depression detection over social media streams" (arXiv preprint). SS3 es un modelo de clasificación de texto. que su característica principal es que tiene la habilidad de explicar de manera natural la racionalidad de los textos.

Se implementó usando la librería de python PySS3.
#### Bert model
El modelo de bert fue creado con el dataset 'Fulldata2.csv' este fue creado con 4 datasets diferentes para tener una gran riqueza de metodologías diferentes. 
Para usar el modelo de bert es necesario usar esta carpeta: https://drive.google.com/drive/folders/1yW85oTu1QoWCcHDDWXHuZPz_1FzHkC-Y?usp=sharing.
Una vez descargada 'sys.path.append(os.path.abspath('/content/drive/MyDrive/bert'))' y 'cd drive/MyDrive/bert' deben ser cambiados a la ubicación de la carpeta descargada. Una vez logrado esto e instalado las librerías necesarias la última celda del notebook Bert_test_depre detectara con que porcentaje cree que un texto es depresivo. Para testear el texto deseado solo es necesario cambiar la variable "text=''" a lo requerido. 

Para más información de los resultados de entrenamiento, pruebas y proceso del modelo bert ver:https://docs.google.com/document/d/1ESw64C7C9L6zr-nKeDmi0CD6De8gAFJOyMwi_1TWkoQ/edit?usp=sharing.

### Modelo de reconocimiento facial y detección de emociones
Para complementar el proyecto y como trabajo a futuro se comenzaron a realizar pruebas de un modelo de reconocimiento facial y detección de emociones para detectar tristeza , el dataset de imágenes utilizado fue el siguiente: https://www.kaggle.com/deadskull7/fer2013 . Para poder utilizar la webcam en google colab es necesario correr un snippet de codigo de google colab asi como en el siguiente link https://colab.research.google.com/drive/1QnC7lV7oVFk5OZCm75fqbLAfD9qBy9bw?usp=sharing. Para hacer el reconocimiento se utilizan los clasificadores cascada y para la detección de emociones una DCNN.  

A pesar de que no existe algún dataset especializado en imágenes de personas que padecen depresión, esto representa una oportunidad para crear uno y poder hacer una predicción real. 
En el siguiente paper se observa un ejemplo del estado del arte de esta tecnica https://www.acadpubl.eu/jsi/2018-118-7-9/articles/7/61.pdf




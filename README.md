# PLN-ProyectoFinal


### Rendimiento de los módelos 
Para elegir los hiperparamteros y para evaluar la efectividad del modelo se tomaron dos principales metricas. La primera es el accuracy del módelo, que es el porcentaje de clasificaciones correctas del total de clasificaciones, asi como el recall, que se calcula de la siguiente manera: 
### Recall = TP/(TP+FN)
### Precision = TP/(TP+FP)
### Accuracy= (TP+TN)/(TP+FN+TN+FP)
TP= True Positive, 
TN= True Negative,
FP= False Positive, 
FN= False Negative.
Se eligío el recall, ya que se esta prediciendo la depresión de una persona. Es mas importante minimizar los Falsos negativos, ya que puede ser peligroso no tratar un caso positivo, y que este se empeore.

Para poder ver el rendimiento de manera grafica, se utilizó la herramienta de matriz de confusión.

### Módelos
#### SS3
El primer módelo que se utilzó fue el módelo SS3, introducido por primera vez en la section 3 del paper cientifico "A text classification framework for simple and effective early depression detection over social media streams" (arXiv preprint). SS3 es un modelo de clasificación de texto. que su caracteristica principal es que tiene la hablidad de explicar de manera natural la racionalidad de los textos.

Se implementó usando la libreria de python PySS3.
#### Bert model
El modelo de bert fue creado con el dataset 'Fulldata2.csv' este fue creado con 4 datasets diferentes para tener una gran riqueza de metodologías diferentes. 
Para usar el modelo de bert es necesario usar esta carpeta: https://drive.google.com/drive/folders/1yW85oTu1QoWCcHDDWXHuZPz_1FzHkC-Y?usp=sharing.
Una vez descargada 'sys.path.append(os.path.abspath('/content/drive/MyDrive/bert'))' y 'cd drive/MyDrive/bert' deben ser cambiados a la ubicación de la carpeta descargada. Una vez logrado esto e instalado las librerías necesarias la última celda del notebook Bert_test_depre detectara con que porcentaje cree que un texto es depresivo. Para testear el texto deseado solo es necesario cambiar la variable "text=''" a lo requerido.


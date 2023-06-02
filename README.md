#######################################
## SIS 420                           ##
## Alumno: Sanchez Calvimontes Pablo ##
## Carrera: Ingenieria de Sistemas   ##
## Grupo laboratorio:  Miercoles     ##
#######################################

#REPOSITORIO DE GITHUB
# https://github.com/Pablo-SC/Sis420_SegundoParcial

#INSTRUCCION DE ECAMPUS 
1. A partir del dataset que se le asigne de forma aleatoria, considerar generar datos 
sinteticos si el valor de m es menor a 10000, posteriormente analize si el dataset corresponde a una regresion, 
clasificacion binario o clasificacion multiclase y aplique el codigo correspondiente de los revisados en clase. 
Se debe incluir una explicacion detallada de la resolucion del ejercicio.

EXPLICACION DEL CODIGO  

EL DATAset asignado es tortuga dataset, es de una empresa/ academia de software tiene originalmente mas de 20000 por lo que no fue necesario usar una 
funcion para crear datos sinteticos

# primero se verifico si se debia hacer un tratamiento de datos, para datos tipo str, tipo date, o datos null	

Se elimino las primeras 3 columnas que no son relevantes para el caso

Existen 6 tipos de clasifaciones para Y

Despues de asignar los valores a las columnas X y Y se normalizo los datos y se aplico el tratamiento de datos 
para que no existan valores null ni str ni datetime

tambien se uso una funcion para rellenar los valores que faltaban en algunas columnas y de esta  manera todas
las columnas tengas la misma cantidad de datos
depues se aplico el cuadernillo visto en clases de one vs all que se uso para clasificar el perfil del estudiante


Se uso la libreria pandas y numpy

la prediccion del conjunto es:

Precision del conjuto de entrenamiento: 70.32% 



2. EJERCICIO 2 

#######################################
## SIS 420                           ##
## Alumno: Sanchez Calvimontes Pablo ##
## Carrera: Ingenieria de Sistemas   ##
## Grupo laboratorio:  Miercoles     ##
#######################################

#REPOSITORIO DE GITHUB
# https://github.com/Pablo-SC/Sis420_SegundoParcial



#INSTRUCCION DE ECAMPUS 
# 2. A partir del dataset de emnist, 
# construir un modelo que permita predecir con la mayor precision el tipo de caracter que 
# corresponde una imagen, el dataset debe ser descargado de su sitio oficial 
# https://www.nist.gov/itl/products-and-services/emnist-dataset. Se debe incluir una explicacion detallada de la resolucion del ejercicio.

# de la pagina oficial se descargo un archivo . rar que contenia los siguientes archivos
# EMNIST ByClass: 814,255 characters. 62 unbalanced classes.
# EMNIST ByMerge: 814,255 characters. 47 unbalanced classes.
# EMNIST Balanced:  131,600 characters. 47 balanced classes.
# EMNIST Letters: 145,600 characters. 26 balanced classes.
# EMNIST Digits: 280,000 characters. 10 balanced classes.
# EMNIST MNIST: 70,000 characters. 10 balanced classes.

# como en clase ya se trabajo con numeros ahora se escogio trabajar con letras del abecedario
# el archivo .mat es: # EMNIST Letters: 145,600 characters. 26 balanced classes


#EXPLICACION DEL CODIGO

# El código proporcionado realiza la identificación de letras escritas a mano utilizando 
# el algoritmo "one vs all" en el conjunto de datos EMIST. 

# La variable "input_layer_size" se establece en 784, que es el número de píxeles en una imagen 
# de dígito de 28x28. Esto se debe a que las imágenes se representan como vectores de tamaño 784 en lugar de matrices 2D.

# La variable "num_labels" se establece en 26, lo que indica que hay 26 letras en el conjunto de datos EMIST.

# Se carga el conjunto de datos EMIST utilizando la función "loadmat" de la biblioteca "scipy.io". 
# Las imágenes y las etiquetas se extraen del conjunto de entrenamiento.

# Las imágenes se almacenan en la variable "X", y las etiquetas se almacenan en la variable "y". 
# Las imágenes son un arreglo 4D, donde la primera dimensión representa las imágenes individuales.

#En el punto 4, después de cargar el conjunto de datos EMIST, las imágenes se almacenan en la variable "X" y las etiquetas se almacenan en la variable "y". 
Sin embargo, es importante destacar que las imágenes se almacenan en un formato particular.

# En este caso, las imágenes se representan como un arreglo 4D. La primera dimensión del arreglo corresponde a las imágenes individuales. 
# Esto significa que si hay, por ejemplo, 1000 imágenes en el conjunto de datos, la primera dimensión del arreglo "X" tendría un tamaño de 1000.
# Cada imagen en el arreglo "X" es una matriz 2D de 28x28 píxeles. La segunda dimensión del arreglo "X" representa las filas de la matriz, 
# y la tercera dimensión representa las columnas de la matriz. Por lo tanto, si se toma una imagen específica de "X", se puede acceder a 
# los píxeles de la imagen utilizando índices de fila y columna.

# La variable "m" se establece en el tamaño de las etiquetas "y", lo que representa el número total de ejemplos de entrenamiento.

# Despues se procede con el codigo de one vs all que se vio en clases, usando la libreia de numpy en este caso
# se cambio el valor lambda a un valor de 0.01 y se obtuvo los siguientes resultados
# como resultado el modelo obtuvo:
# Precision del conjuto de entrenamiento: 70.59%

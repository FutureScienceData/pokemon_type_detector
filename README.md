# Pokemon Type Detector

![cvmod](https://img.shields.io/static/v1.svg?label=version&message=v1.0&color=green)  ![python](https://img.shields.io/static/v1.svg?label=python&message=3.7&color=blue)

El proyecto fue probado en distribuciones basadas en  **debian**, **ubuntu** y **windows 10**

## Overview

**Pokemon Type Detector** es un modelo de deeplearning pre-entrenado que tiene la finalidad de detectar el tipo de pokemon que se le ingrese.
El modelo es una variante del **VGG16** con los pesos de imagenet. Puede ser usado desde el archivo .py o ejecutando el projecto de django.




Las clases de salida del modelo son las siguientes: 

```python
classes = ['Bug', 'Dark', 'Dragon', 'Electric', 'Fairy', 'Fighting', 'Fire',
           'Flying', 'Ghost', 'Grass', 'Ground', 'Ice', 'No 2nd type', 'Normal',
           'Poison', 'Psychic', 'Rock', 'Steel', 'Water']
```



## Getting Started

Para poder ejecutar el código es necesario instalar los requerimientos incluidos en el archivo [requirements.txt](inc/requirements.txt)

El modelo puede ser importado desde el archivo [pokemon_detector_type.py](src/pokemon_detector_type.py) con la función 

```python
predict_type(image):
    """
    Display image, with predictions.
    Parameters
    ----------
    pokemon_img : PIL.Image
        Image open with pillow 
        
    pokemon : str
        Pokemon name with base on data/pokedex_(Update_04.21).csv

    Returns
    -------
    PIL image with  comparing the input and the prediction

    """

```

<p align="center">
<img src="imgs/output_notebook.png">
</p>



También puede ser usado con un front hecho en django ejecutando:

```console
django-admin python front/pokemon_type_detector_app/manage.py runserver
```
<p align="center">
<img src="imgs/output_pagina.png">
</p>



## Dataset
El dataset para obtener los nombres y los tipos:https://www.kaggle.com/mariotormo/complete-pokemon-dataset-updated-090420

Para obetener las imagenes de cada pokemon se ejecuta el  notebook [image_downloader.ipynb](notebooks/image_downloader.ipynb)



## Training

El entrenamiento se realiza con las imagenes descargadas y se genera la variable objetivo juntando los dos tipos de cada pokemon.
También es creada la clases de "No_type" como una carencia de segundo tipo.

El entrenamiento es hecho en el notebook  [pokemon_type_detector_train.ipynb](notebooks/pokemon_type_detector_train.ipynb)



## Reference 

Imgs logos: https://es.vecteezy.com/arte-vectorial/119820-libre-tipo-pokemon-vector
Pokedex: https://www.kaggle.com/mariotormo/complete-pokemon-dataset-updated-090420

Nota: Para más acerca del proceso https://www.youtube.com/channel/UCDGBKWc6sHALO1a1Oou8o4w/

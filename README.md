# HACKATON & MARKETPLACE / SALÓ DE L'OCUPACIÓ - SPAIN OCT 2024

### 1. Introducció: Presentació del conjunt de dades i de les variables seleccionades.

En el presente estudio se analizan los accidentes según sus causas, gestionados por la Guardia Urbana en la Ciudad de Barcelona.

Se ha seleccionado únicamente los datasets para los años 2016, 2017, 2018, 2019 y 2020; debido a su homegeneidad entre sí. Además, una vez realizado el análisis del mejor modelo para el pronóstico podríamos someter su nível de predicción contrastándolo con datos reales de los datasets para los años subsiguientes (2021, 2022,2023). Aunque esto último, no forma parte del presente estudio.

Se utilizan técnicas de Análisis Exploratorio de Datos y Pipeline para el modelaje de los datos. 

De esta manera se busca obtener algunos insights a cerca de los accidentes de tránsito en Barcelona ciudad, sus características principales y que variables más relevantes están relacionadas a sus causas. 


### 2. Depuració de dades: Descripció detallada de les tècniques de preprocessat aplicades i els criteris d’avaluació utilitzats.

- #### Limpieza de datos:
  Se han **eliminado** las columnas Numero_expedient, Coordenades_UTM_X_ED50 y Coordenades_UTM_Y_ED50 pues se considera que su ausencia no impacta significativamente en el análisis.
  Solo hallamos 15 valores nulos y todos contenidos en el campo Num_postal, con lo cual su impacto es mínimo. Aún así, se han completado aquellos valores bajo la técnica forward fill con el comando     ffill. 

- ### Codificación de variables categóricas:
  Las variables categóricas del dataset se codificaron usando get_dummies.

- ### Corrección de inconsistencias: 
  Se realizó una modificación del nombre de los campos "Descripcio_torn" y "Descripcio_causa_conductor" pues sus valores estaban intercambiados.


### 3. Resultats: Presentació dels resultats obtinguts.

### EDA: Análisis Exploratorio de Datos
   Mediante esta serie de análisis se ha obtenido las estadísticas más importantes para todos los campos, comenzando que en total para el conjunto de datasets se tienen 51056 filas y 20 columnas. 15 son los valores nulos, como ya se mencionó. 
   
   Visualmente hablando se han obtenido insights importantes como que la mayor cantidad de accidentes tuvieron lugar en el distrito de Eixample. Por otro lado la falta de atención en la conducción se corona como el principal motivo de los accidentes. Así mismo, no hubo gran variación en la cantidad de accidentes a excepción del año 2020, año de pandemia, donde cayeron considerablemente.
  
### Modelos de Predicción

  Se entrenaron modelos de Regresión Logística y Random Forest. Ambos modelos tienen un valor de F1-score muy similar. Esto indica que tanto la precisión como el recall son razonablemente altos. 

  No obstante, Random Forest es el modelo que ofrece un mejor rendimiento en general, en este caso. Aunque su desempeño en la clase positiva (True) es bajo, detecta algunos casos positivos, lo que lo hace superior a la Regresión Logística, que no detecta ningún caso positivo. Por ello nos decantamos por el modelo Random Forest.

### 4. Conclusions: Principals inferències derivades dels resultats aconseguits.

A partir del análisis mostrado se puede inferir que hay políticas que se pueden implementar a fin de reducir la cantidad de accidentes. 

Ya que estos han sucedido en mayor número durante la tarde y los viernes, se podría aumentar el control por parte de las autoridades en aquellos días para disuadir a los conductores imprudentes que por falta de poner atención al volante cometen accidentes. Todo ello, enfatizándose en el distrito de Eixample, que es donde suceden en mayor cantidad.








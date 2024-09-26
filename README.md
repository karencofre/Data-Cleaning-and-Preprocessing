# Análisis de Datos Limpieza y Preprocesado

Ficha Técnica: Proyecto de Análisis de Datos

Título del Proyecto: Análisis de Datos limpieza y preprocesado

Objetivo:
Limpiar, preprocesar los datos y estandariza para aplicar una reducción de dimensionalidad.

Equipo:
Trabajo Individual.

Herramientas y Tecnologías:
- Python
- Pandas
- sklearn
- Google Colab

Procesamiento y análisis:
- limpieza de datos
- exploración de datos
- Técnica de Análisis de datos
  
Resultados y Conclusiones:
Se hizo una limpieza, un preprocesado y luego de una previa estandarizacion de los datos se logro aplicar un PCA.

PCA:

```python
# justificacion el df debe reducirse por su numero elevado de variables
from sklearn.decomposition import PCA

columnas = ['c_int_rate','c_installment','c_annual_inc','c_dti',
           'c_revol_util',
            'c_out_prncp','c_out_prncp_inv',
          'c_total_rec_prncp','c_total_rec_late_fee',
            'c_recoveries','c_collection_recovery_fee','c_last_pymnt_amnt',
            'c_tot_cur_bal','c_total_rev_hi_lim']
pca = PCA(n_components=2)

varianza_explicada = pca.explained_variance_ratio_
print(varianza_explicada) # justificacion esta varianza explicada me indica cuantos n_components escoger ya que dos componentes explican mas del 95% de la varianza

filas= scaled_df[columnas]

pca_resultados = pca.fit_transform(filas)
df_pca = pd.DataFrame(data=pca_resultados,columns=['C1','C2'])
df_pca['Muestra'] = scaled_df.index
print(df_pca.head())
```

Limitaciones/Próximos Pasos:
Identifica y describe cualquier limitación o desafío encontrado durante el proyecto.
Sugiere posibles próximos pasos para extender o mejorar el proyecto de análisis de datos.

Enlaces de interés:
[google colab](https://colab.research.google.com/drive/1-XCbLXKM_HDzkfcr5Ul_9cnTesS6H6c6?usp=sharing)

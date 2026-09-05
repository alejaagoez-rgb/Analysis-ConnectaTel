# # # 📊 Análisis de clientes y patrones de uso — ConnectaTel

## 📌 Descripción del proyecto

Este proyecto presenta un análisis exploratorio y de segmentación de clientes de **ConnectaTel**, con el objetivo de identificar patrones de comportamiento, niveles de uso y oportunidades comerciales que permitan mejorar la oferta de planes de telecomunicaciones.

El análisis se enfoca principalmente en:

* Calidad y limpieza de los datos.
* Distribución de clientes según edad.
* Comportamiento de uso de llamadas y mensajes.
* Comparación de los planes Básico y Premium.
* Identificación de patrones de uso extremo (*outliers*).
* Identificación de segmentos de clientes de interés comercial.
* Generación de recomendaciones orientadas a la toma de decisiones.

---

## 🎯 Objetivo de negocio

El objetivo principal es transformar los datos de clientes y uso de servicios en **insights accionables para ConnectaTel**.

A partir del análisis se busca responder:

1. ¿Qué problemas de calidad presentaban originalmente los datos?
2. ¿Qué segmentos de clientes existen según edad y nivel de uso?
3. ¿Qué segmentos pueden representar mayor valor para ConnectaTel?
4. ¿Qué patrones de uso extremo se presentan?
5. ¿Qué oportunidades existen para mejorar los planes actuales o crear nuevas ofertas?

---

## 🗂️ Datasets utilizados

El proyecto utiliza información relacionada con clientes y consumo de servicios de telecomunicaciones.

### `users`

Contiene información de los clientes, incluyendo variables como:

* `user_id`
* `first_name`
* `last_name`
* `age`
* `city`
* `reg_date`
* `plan`
* `churn_date`

### `usage`

Contiene información sobre las interacciones realizadas por los clientes:

* `id`
* `user_id`
* `type`
* `date`
* `duration`
* `length`

A partir de estas variables se construyeron métricas agregadas para analizar el comportamiento individual de cada cliente.

---

## 🔎 Metodología

El análisis se desarrolló mediante las siguientes etapas:

### 1. Exploración inicial

Se revisó la estructura de los datasets, tipos de datos, valores únicos y presencia de valores faltantes.

### 2. Calidad y limpieza de datos

Se identificaron y trataron diferentes situaciones:

* Valores nulos en `city`.
* Valor sentinel `-999` en `age`.
* Valores nulos en `churn_date`.
* Valores faltantes en `usage.date`.
* Valores nulos en `duration` y `length`.
* Fechas futuras en `reg_date`.

Los valores faltantes de `duration` y `length` fueron interpretados considerando el tipo de interacción: los mensajes no requieren duración y las llamadas no requieren longitud de mensaje.

---

## 👥 Segmentación de clientes

### Segmentación por edad

Se definieron tres grupos:

| Segmento        | Rango de edad | Clientes | Participación |
| --------------- | ------------: | -------: | ------------: |
| Jóvenes         |     < 30 años |      760 |       19,00 % |
| Adultos         |    30–59 años |    2.018 |       50,45 % |
| Adultos mayores |     ≥ 60 años |    1.222 |       30,55 % |

El segmento **Adulto** concentra la mayor cantidad de clientes, seguido por los adultos mayores. Esto indica que las estrategias comerciales deberían considerar especialmente las necesidades y patrones de consumo de estos grupos.

---

### Segmentación por nivel de uso

Los clientes fueron clasificados considerando su actividad de llamadas y mensajes:

| Nivel de uso | Clientes | Participación |
| ------------ | -------: | ------------: |
| Bajo uso     |      778 |       19,45 % |
| Uso medio    |    2.943 |       73,58 % |
| Alto uso     |      279 |        6,98 % |

El **uso medio es claramente el segmento dominante**, representando aproximadamente tres cuartas partes de la base de clientes.

---

## 📈 Principales hallazgos

### 1. Predominio del segmento de uso medio

El **73,58 % de los clientes** pertenece al segmento de uso medio.

Esto representa una oportunidad para evaluar si la estructura actual de los planes responde adecuadamente a las necesidades de este grupo.

### 2. Existencia de clientes de alto consumo

Aunque los clientes de alto uso representan solo el **6,98 %**, constituyen un segmento estratégico debido a su mayor intensidad de consumo.

Estos clientes pueden tener potencial para:

* Migración hacia planes Premium.
* Venta de servicios adicionales.
* Ofertas personalizadas.
* Programas de fidelización.

### 3. Oportunidad en clientes de bajo uso

El **19,45 % de los clientes presenta bajo nivel de uso**.

Este segmento puede representar una oportunidad para incrementar la utilización de los servicios mediante campañas de activación, beneficios temporales y ofertas personalizadas.

### 4. Concentración por edad

Los adultos representan el **50,45 % de la base**, mientras que los adultos mayores representan el **30,55 %**.

En conjunto, estos dos grupos constituyen la mayor parte de la base analizada, por lo que deberían ser considerados en las estrategias de producto, comunicación y fidelización.

---

## 📊 Análisis de outliers

Durante el análisis se identificaron valores extremos en las variables de consumo:

* **46 outliers** en cantidad de mensajes.
* **30 outliers** en cantidad de llamadas.
* **109 outliers** en total de minutos de llamadas.

Estos registros no deben interpretarse automáticamente como errores. Algunos pueden corresponder a clientes reales con un nivel de consumo considerablemente superior al promedio.

Desde una perspectiva comercial, estos clientes pueden ser considerados como posibles **usuarios intensivos (*heavy users*)**.

Los valores extremos fueron tratados para evitar que distorsionaran las estadísticas descriptivas, conservando al mismo tiempo la información relevante para el análisis.

---

## 💼 Segmentos de mayor interés comercial

A partir del análisis realizado, se identifican tres grupos prioritarios:

### ⭐ Clientes de alto uso

Representan un grupo pequeño pero estratégico.

**Oportunidad:** desarrollar estrategias de migración a Premium, beneficios adicionales y ofertas personalizadas.

### 🎯 Clientes de uso medio

Representan el **73,58 % de la base**, por lo que constituyen el principal mercado objetivo.

**Oportunidad:** evaluar un plan intermedio que se adapte mejor a sus necesidades de consumo.

### 🔄 Clientes de bajo uso

Representan el **19,45 % de los clientes**.

**Oportunidad:** desarrollar campañas de activación y fidelización para aumentar su utilización de los servicios y reducir el riesgo de abandono.

---

## 💡 Recomendaciones de negocio

### 1. Crear una estrategia de migración a Premium

Identificar clientes de alto uso que actualmente pertenecen al plan Básico y ofrecerles beneficios que incentiven la migración.

### 2. Evaluar un plan intermedio

Debido a que el uso medio representa el **73,58 % de los clientes**, ConnectaTel podría evaluar un plan ubicado entre Básico y Premium.

Este producto podría ofrecer una cantidad de servicios superior al plan Básico, pero sin llegar necesariamente al nivel de consumo del Premium.

### 3. Activar clientes de bajo uso

Diseñar campañas dirigidas a clientes con bajo consumo mediante:

* Bonificaciones temporales.
* Paquetes promocionales.
* Beneficios por aumentar el uso.
* Comunicaciones personalizadas.

### 4. Fortalecer la propuesta de valor del Premium

La estrategia Premium debería diferenciarse mediante beneficios adicionales y una propuesta de valor clara, además de la cantidad de minutos o mensajes incluidos.

### 5. Aprovechar los usuarios intensivos

Los *heavy users* identificados mediante el análisis de outliers pueden convertirse en un segmento específico para ofertas personalizadas y servicios adicionales.

### 6. Mejorar la calidad de los datos

Es recomendable continuar mejorando la captura de información de ciudad y otros atributos relevantes para permitir una segmentación comercial más precisa.

---

## 🛠️ Tecnologías utilizadas

El análisis fue desarrollado utilizando:

* **Python**
* **Pandas** — manipulación y análisis de datos.
* **NumPy** — operaciones numéricas.
* **Matplotlib** — visualización de datos.
* **Seaborn** — visualización estadística.
* **Jupyter Notebook / Google Colab** — desarrollo y documentación del análisis.
* **GitHub** — almacenamiento y versionamiento del proyecto.

---

## 📁 Estructura del repositorio

```text
connectatel-analysis/
│
├── README.md
│
├──
│   └── S7_Version_Estudiante_Project_ConnectaTel.ipynb
│
├── data/
│   ├── users.csv
│   └── usage.csv
│
└── images/
    └── visualizations/

## ▶️ Cómo ejecutar el proyecto

### Opción 1 — Google Colab

1. Abrir el archivo `.ipynb`.
2. Seleccionar **Open in Colab**.
3. Ejecutar las celdas en orden.
4. Verificar que los datasets se encuentren en la ruta utilizada por el notebook.

### Opción 2 — Jupyter Notebook

Instalar las principales dependencias:

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

Posteriormente ejecutar:

```bash
jupyter notebook
```

Abrir el notebook:

```text
/S7_Version_Estudiante_Project_ConnectaTel.ipynb
```

y ejecutar las celdas en orden.


## 🔁 Reproducibilidad

Para reproducir el análisis:

1. Clonar o descargar este repositorio.
2. Mantener los datasets en la carpeta correspondiente.
3. Abrir el notebook.
4. Instalar las librerías necesarias.
5. Ejecutar las celdas en orden.
6. Revisar las tablas, visualizaciones e insights generados.


## 📌 Conclusión ejecutiva

El análisis muestra que ConnectaTel cuenta principalmente con una base de clientes **adultos y de uso medio**. El segmento de uso medio representa el **73,58 % de los clientes**, mientras que los usuarios de alto consumo constituyen un grupo más pequeño pero con potencial comercial.

Los resultados sugieren que la compañía puede trabajar simultáneamente en tres frentes: **monetizar a los clientes de alto uso, desarrollar una oferta más ajustada para el amplio segmento de uso medio y aumentar la activación de los clientes de bajo uso**.

De esta manera, el análisis de datos puede utilizarse no solo para describir el comportamiento actual de los clientes, sino también para apoyar decisiones relacionadas con **segmentación, diseño de planes, fidelización y crecimiento de ingresos**.


## 👩‍💻 Autora

**Alejandra Aguirre**

Analista de Datos | Contadora Pública Especialista en Impuestos

Proyecto desarrollado como parte del proceso de formación en análisis de datos.


## 🔗 Repositorio

**GitHub:**
`[(https://github.com/alejaagoez-rgb/Analysis-ConnectaTel.git)]`



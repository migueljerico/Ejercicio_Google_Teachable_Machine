# Guía de Ejercicio: Aprendizaje Supervisado con Google Teachable Machine para Clasificación de Imágenes

## 📋 Resumen
Este documento describe un ejercicio práctico para comprender el aprendizaje supervisado y su aplicación en la clasificación de imágenes. Utilizando Google Teachable Machine, se guía al usuario paso a paso para entrenar un modelo que pueda distinguir entre imágenes de perros y gatos, desde la configuración inicial hasta la prueba y mejora del modelo. Es un ejercicio accesible diseñado para iniciarse en el Machine Learning de forma práctica.

## 🔑 Puntos clave
- **Introducción al Aprendizaje Supervisado:** El ejercicio demuestra cómo una inteligencia artificial "aprende" a clasificar información visual a través de ejemplos etiquetados.
- **Uso de Google Teachable Machine:** Herramienta accesible para la creación de modelos de aprendizaje automático sin necesidad de codificación avanzada.
- **Clasificación de Imágenes:** Enfoque en la distinción entre dos categorías específicas (perros y gatos).
- **Importancia de la Variedad de Datos:** Se enfatiza la necesidad de utilizar un conjunto diverso de imágenes para un entrenamiento robusto del modelo.
- **Prueba y Mejora del Modelo:** Se exploran métodos para evaluar la precisión del modelo, identificar sus limitaciones y optimizar su rendimiento.

## 📝 Detalle

Este ejercicio, parte de la formación INAEM en Análisis de Datos e IA, utiliza Google Teachable Machine (Standard Image Model) para la clasificación supervisada de imágenes.

### 01. Acceso a Teachable Machine
1.  Acceder a la plataforma a través de: `https://teachablemachine.withgoogle.com`.
2.  Pulsar `Get Started`.
3.  Seleccionar `Image Project`.
4.  Elegir `Standard Image Model`.

### 02. Elección y Nombramiento de Categorías
Se procede a definir las clases que el modelo aprenderá a distinguir:
-   Renombrar `Clase 1` a **Perro**.
-   Renombrar `Clase 2` a **Gato**.

### 03. Búsqueda de Imágenes para Entrenamiento
Es fundamental recolectar un conjunto de datos variado para cada categoría.
1.  Abrir una nueva pestaña e ir a Google Imágenes.
2.  Buscar imágenes de **Perro** y **Gato**.
3.  Descargar aproximadamente 20 imágenes diferentes por categoría, procurando la mayor variedad posible en:
    -   Diferentes razas
    -   Distintos colores
    -   Diferentes posiciones
    -   Distintos fondos
    -   Distintos tamaños
4.  Guardar las imágenes en dos carpetas separadas: "Perro" y "Gato".

> **Importancia de la Variedad:** Esta diversidad es crucial para que el modelo aprenda a reconocer perros y gatos en múltiples situaciones, y no se limite a identificar solo características muy específicas de las imágenes de entrenamiento.

### 04. Importación de las Imágenes
1.  En Google Teachable Machine, dentro de cada clase, pulsar `Upload`.
2.  Seleccionar y cargar todas las imágenes de la carpeta "Perro" en la clase `Perro`.
3.  Repetir el proceso con las imágenes de la carpeta "Gato" en la clase `Gato`.

### 05. Entrenamiento del Modelo
1.  Pulsar el botón `Train Model`.
2.  Esperar unos segundos mientras la inteligencia artificial procesa las imágenes y aprende los patrones asociados a cada categoría.

### 06. Prueba Inicial del Modelo
Una vez entrenado, es momento de probar su capacidad de predicción con datos nuevos.
1.  En la sección de `Preview` (o previsualización), pulsar `Upload Image`.
2.  Descargar imágenes nuevas de perros y gatos de Google que *no* se hayan utilizado en el entrenamiento.
3.  Ir probando estas imágenes una a una y observar:
    -   La categoría predicha por el modelo.
    -   El porcentaje de confianza de la predicción.

### 07. Búsqueda de Errores y Limitaciones
Este paso es esencial para comprender los límites del modelo y cómo puede fallar.
1.  Intentar "engañar" al modelo probando con imágenes que podrían generar confusión o ser ambiguas:
    -   Lobo
    -   Zorro
    -   Cachorro
    -   Peluche de perro
    -   Dibujo animado de un gato
2.  Observar qué ocurre con las predicciones: si son incorrectas, dudosas o inesperadas.

> **Reflexión sobre los Errores:** Al identificar predicciones incorrectas o dudosas, es útil reflexionar sobre por qué el modelo pudo haberse equivocado. Esto a menudo se debe a la falta de ejemplos similares en los datos de entrenamiento, o a la ambigüedad de la imagen para el modelo.

### 08. Mejora del Modelo
Para aumentar la precisión y robustez del modelo:
1.  Descargar aproximadamente 20 imágenes adicionales de cada animal.
2.  Enfocarse en añadir aún más variedad a las imágenes:
    -   De noche
    -   De perfil
    -   Tumbados
    -   Corriendo
    -   Con personas
    -   Varios animales en la misma imagen
3.  Volver a importar estas nuevas imágenes a sus respectivas clases.
4.  Entrenar nuevamente el modelo (pulsando `Train Model`).
5.  Repetir los pasos de prueba para verificar la mejora.

## ✅ Conclusiones / siguientes pasos
Este ejercicio proporciona una base sólida en el aprendizaje supervisado y el uso de Google Teachable Machine para la clasificación de imágenes. Se ha demostrado la importancia de un conjunto de datos diverso y la iteración en el proceso de entrenamiento para mejorar el rendimiento del modelo.

Para seguir explorando y profundizando, se sugieren los siguientes pasos:
-   **Experimentar con otras categorías:** Aplicar la misma metodología para clasificar otros animales, tipos de plantas, objetos cotidianos o cualquier otra clasificación visual de interés.
-   **Aumentar la complejidad:** Si se tienen los conocimientos, exportar el modelo de Teachable Machine e integrarlo en una aplicación web o móvil para una demostración interactiva.
-   **Profundizar en la teoría:** Investigar los fundamentos de las redes neuronales y los algoritmos de clasificación utilizados por Teachable Machine para una comprensión más profunda.
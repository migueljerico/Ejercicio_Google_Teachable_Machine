# Guía Práctica de Clasificación de Imágenes con Google Teachable Machine

## 📋 Resumen
Este documento detalla un ejercicio de aprendizaje supervisado utilizando Google Teachable Machine para entrenar un modelo de clasificación de imágenes. El objetivo principal es distinguir entre perros, gatos y caballos, explorando el proceso completo desde la recolección de datos y el entrenamiento hasta la evaluación de la fiabilidad del modelo y sus limitaciones en un entorno práctico.

## 🔑 Puntos clave
-   **Aprendizaje Supervisado Práctico**: Guía paso a paso para entrenar un modelo de clasificación de imágenes con Google Teachable Machine.
-   **Clasificación Multiclase**: Creación y entrenamiento de un modelo para categorizar imágenes de perros, gatos y caballos.
-   **Importancia de la Variedad de Datos**: Énfasis en la necesidad de imágenes diversas para mejorar la generalización del modelo y evitar la memorización de ruido.
-   **Análisis Crítico de Errores**: Metodología para identificar, comprender y analizar los fallos del modelo, incluyendo falsos positivos al clasificar objetos no entrenados o ambiguos (lobos, peluches, caballos).
-   **Limitaciones y Aplicabilidad en Producción**: Reflexión sobre por qué un prototipo básico no es adecuado para entornos empresariales reales, destacando la necesidad de entrenamiento riguroso, balanceo de datos y una clase de "rechazo".
-   **Conceptos Fundamentales**: Definición de datos etiquetados y explicación del comportamiento de los algoritmos ante datos nunca vistos.

## 📝 Detalle

### Introducción al Ejercicio
Este ejercicio de formación de INAEM, realizado por Miguel Jericó, se centra en el bloque de Redes Neuronales y Clasificación Supervisada de Imágenes. Utiliza Google Teachable Machine (Standard Image Model) como herramienta principal para construir un clasificador visual de animales.

### Proceso de Entrenamiento del Modelo
El proceso para entrenar el modelo de clasificación de imágenes se estructura en los siguientes pasos:

1.  **Acceso a Teachable Machine**:
    *   Navegar a `https://teachablemachine.withgoogle.com`.
    *   Seleccionar "Get Started", luego "Image Project" y finalmente "Standard Image Model".

2.  **Elección de Categorías (Clases)**:
    *   Se renombran las clases iniciales a "Perro" y "Gato".
    *   Posteriormente, se añade una tercera categoría: "Caballo".

3.  **Búsqueda y Recopilación de Imágenes**:
    *   Se buscan aproximadamente 20 imágenes diferentes por cada categoría (Perro, Gato, Caballo) en Google Imágenes.
    *   Es crucial que las imágenes sean variadas en:
        *   Diferentes razas/tipos de animales
        *   Distintos colores
        *   Diferentes posiciones (de pie, tumbados, corriendo)
        *   Distintos fondos
        *   Distintos tamaños
        *   Escenarios complejos (de noche, de perfil, con personas, varios animales).
    *   Las imágenes se guardan en carpetas separadas con los nombres de las clases.

4.  **Importación de Imágenes**:
    *   En Teachable Machine, se utiliza la función "Upload" para cargar todas las imágenes correspondientes a cada clase desde las carpetas locales.

5.  **Entrenamiento del Modelo**:
    *   Se pulsa el botón "Train Model".
    *   El sistema de IA procesa las imágenes y ajusta los pesos internos de la red neuronal para aprender los patrones distintivos de cada clase.

6.  **Prueba Inicial del Modelo**:
    *   Una vez entrenado, se pulsa "Upload Image" para probar el modelo.
    *   Se descargan y prueban imágenes nuevas de perros, gatos y caballos (no utilizadas en el entrenamiento) para observar la categoría predicha y el porcentaje de confianza.

7.  **Búsqueda de Errores e Intento de "Engaño"**:
    *   Se intenta "engañar" al modelo probando imágenes de animales o conceptos similares que no forman parte de las clases entrenadas:
        *   Lobo
        *   Zorro
        *   Cachorro
        *   Peluche de perro
        *   Dibujo animado de un gato

8.  **Mejora del Modelo**:
    *   Se descargan 20 imágenes adicionales por cada animal, aumentando aún más la variedad para cubrir escenarios más complejos (imágenes de noche, de perfil, con varios animales).
    *   El modelo se entrena nuevamente para incorporar estos nuevos datos y mejorar su robustez.

### Análisis del Modelo y Resultados
Tras el entrenamiento con tres clases (Perro, Gato, Caballo) y la adición de imágenes variadas, se realizó un análisis de las predicciones:

| Imagen      | Predicción | Probabilidad | ¿Ha acertado? | Observaciones                                              |
| :---------- | :--------- | :----------- | :------------ | :--------------------------------------------------------- |
| Perro 1     | Perro      | 61,00 %      | Sí            |                                                            |
| Perro 2     | Perro      | 100,00 %     | Sí            |                                                            |
| Gato 1      | Gato       | 100,00 %     | Sí            |                                                            |
| Gato 2      | Gato       | 100,00 %     | Sí            |                                                            |
| Caballo 1   | Perro      | 91,00 %      | No            | **Error:** Un caballo fue clasificado como perro con alta confianza. |
| Lobo        | Perro      | 82,00 %      | No            | **Error:** El lobo fue clasificado como perro.            |
| Peluche     | Perro      | 100,00 %     | No            | **Error:** Un objeto inanimado (peluche) fue clasificado como perro. |

### Preguntas de Reflexión y Conceptos Clave

1.  **¿Qué son los datos etiquetados?**
    Son conjuntos de datos clasificados o anotados previamente con la respuesta correcta antes de ser introducidos en la red neuronal. En este ejercicio, las clases se renombraron ("Perro", "Gato", "Caballo") y las carpetas con imágenes correspondientes actuaron como etiquetas.

2.  **¿Por qué es importante utilizar muchas imágenes diferentes?**
    Es vital para que el modelo generalice correctamente y no memorice el "ruido" o particularidades de las imágenes iniciales. La variedad (razas, colores, posiciones, fondos, tamaños, escenarios complejos) permite al modelo aprender patrones robustos aplicables a diversas situaciones.

3.  **¿Qué ocurre cuando el modelo intenta clasificar una imagen que nunca ha visto?**
    El algoritmo carece de contexto real y calcula distancias matemáticas para encajar la nueva imagen en las categorías que domina, basándose en patrones de píxeles compartidos. Esto puede llevar a clasificaciones forzadas, como un lobo o un caballo siendo identificados como "Perro" con alta confianza.

4.  **¿Ha mejorado el modelo después de añadir más imágenes?**
    Sí, la precisión del modelo es mayor. Al incrementar el volumen y la variedad de la muestra, los pesos del modelo se ajustan mejor, haciéndolo más resistente ante imágenes que se desvían de los ejemplos iniciales.

5.  **¿Qué imágenes han producido más errores?**
    Los errores principales surgieron con las imágenes seleccionadas para "engañar" al sistema. El caballo, el lobo y el peluche de perro provocaron falsos positivos hacia la categoría "Perro", debido a que compartían texturas, formas (hocicos, orejas) o paletas de color presentes en las imágenes de entrenamiento de la clase "Perro".

6.  **¿Crees que este modelo sería suficientemente fiable para utilizarse en una empresa?**
    **No**. Un prototipo como este no sería viable en un entorno empresarial de producción real. Necesitaría un entrenamiento inmensamente mayor, balanceado y auditado. La ausencia de una clase "Desconocido" o un umbral de descarte lleva a errores críticos, como clasificar un objeto inanimado (el peluche) como perro con un 100% de seguridad.

### Aplicaciones Reales de Sistemas Similares
Aunque el prototipo no es apto para producción, sistemas similares, debidamente entrenados y validados, podrían aplicarse en:
-   **Control de calidad en manufactura**: Sistemas de visión que clasifican productos como "Aptos" o "Defectuosos" por anomalías visuales.
-   **Clasificación documental automatizada**: Motores de OCR y visión que escanean documentos y los categorizan (facturas, contratos, currículums).
-   **Gestión inteligente de residuos**: Cámaras en plantas de reciclaje que identifican y separan plásticos, metales y cartones en la cinta transportadora.

## ✅ Conclusiones / siguientes pasos
El ejercicio demuestra la facilidad de uso de Google Teachable Machine para iniciarse en el aprendizaje supervisado y la clasificación de imágenes. Sin embargo, resalta la importancia crítica de la calidad y cantidad de los datos de entrenamiento para la robustez del modelo, así como la necesidad de un análisis riguroso de sus limitaciones.

Para futuras mejoras y la viabilidad de un modelo en un entorno de producción, sería esencial:
-   Aumentar significativamente la cantidad y diversidad de imágenes de entrenamiento.
-   Explorar y añadir una clase de "Desconocido" o establecer un umbral de confianza para el descarte, evitando clasificaciones erróneas de elementos fuera de las categorías entrenadas.
-   Implementar procesos de validación y auditoría mucho más estrictos para garantizar la fiabilidad del modelo.
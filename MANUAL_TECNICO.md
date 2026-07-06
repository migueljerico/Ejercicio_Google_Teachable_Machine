## Arquitectura General
La arquitectura de este ejercicio se enfoca en la interacción con una herramienta web de aprendizaje automático, siguiendo un flujo conceptual simplificado:

```
└── Interfaz de Usuario (Google Teachable Machine) → Capa de Lógica de Aprendizaje (Servicios de Google Teachable Machine) → Capa de Datos (Imágenes de entrenamiento)
```

## Descripción de Módulos
- **docs/Ejercicio_3-3_Teachable_Machine_Miguel_Jerico.md**: Este documento es una guía detallada para el ejercicio de aprendizaje supervisado con Google Teachable Machine. Describe paso a paso cómo configurar un proyecto, seleccionar y nombrar categorías (perros y gatos), buscar e importar imágenes diversas para el entrenamiento, ejecutar el entrenamiento del modelo, realizar pruebas iniciales, identificar errores y limitaciones, y finalmente, mejorar la precisión del modelo mediante la adición de más datos variados. Es el componente principal que detalla la metodología práctica del ejercicio.

## APIs y Endpoints
Este proyecto no expone ni consume APIs o endpoints directamente, ya que se centra en el uso de la interfaz web de Google Teachable Machine.

## Variables de Entorno
No aplica. Este ejercicio no utiliza variables de entorno.

## Guía de Despliegue
El "despliegue" de este proyecto se refiere al proceso de utilización de la plataforma Google Teachable Machine para entrenar y probar el modelo.

1.  **Acceder a Google Teachable Machine**: Abre tu navegador web y navega a [https://teachablemachine.withgoogle.com](https://teachablemachine.withgoogle.com).
2.  **Iniciar un Nuevo Proyecto**: Haz clic en `Get Started` y luego selecciona `Image Project`, eligiendo el `Standard Image Model`.
3.  **Configurar Clases**: Renombra las clases predeterminadas a `Perro` y `Gato`.
4.  **Recopilar Datos de Entrenamiento**: Busca y descarga aproximadamente 20 imágenes variadas de perros y 20 de gatos. Guarda estas imágenes en carpetas separadas (`Perro`, `Gato`).
5.  **Importar Imágenes**: Dentro de cada clase en Teachable Machine, haz clic en `Upload` y sube las imágenes correspondientes a cada categoría.
6.  **Entrenar el Modelo**: Una vez cargadas las imágenes, haz clic en el botón `Train Model` y espera a que el proceso se complete.
7.  **Probar el Modelo**: Utiliza la sección `Preview` para cargar nuevas imágenes (no usadas en el entrenamiento) de perros y gatos y observa las predicciones del modelo.
8.  **Identificar Limitaciones y Mejorar**: Prueba el modelo con imágenes ambiguas o no entrenadas para entender sus fallos. Para mejorar, añade más imágenes diversas a las categorías y vuelve a entrenar el modelo.

## Limitaciones y Mejoras Futuras
**Limitaciones Conocidas**:
*   La precisión del modelo está directamente ligada a la cantidad y diversidad de los datos de entrenamiento. Un conjunto de datos pequeño o poco variado puede llevar a un modelo con baja precisión o sobreajuste.
*   La herramienta Google Teachable Machine ofrece opciones limitadas de configuración avanzada del modelo, lo que puede ser una limitación para casos de uso más complejos.
*   El modelo puede confundir categorías con características visuales similares (ej. lobos con perros, zorros con gatos si no hay suficientes ejemplos distintivos).

**Posibles Mejoras Futuras**:
*   **Aumento de Datos**: Incrementar significativamente la cantidad de imágenes de entrenamiento para cada clase, incluyendo una mayor variedad de razas, fondos, ángulos y condiciones de iluminación.
*   **Aumento de Clases**: Extender el ejercicio para incluir más categorías de animales o objetos, aumentando la complejidad del problema de clasificación.
*   **Análisis de Errores**: Dedicar más tiempo a analizar los casos en los que el modelo falla, para entender mejor sus debilidades y cómo abordarlas (ej. añadir datos específicos que cubran esos fallos).
*   **Comparación de Herramientas**: Realizar el mismo ejercicio utilizando otras plataformas de Machine Learning sin código o librerías de programación (ej. TensorFlow Lite, Keras) para comparar el proceso y los resultados.
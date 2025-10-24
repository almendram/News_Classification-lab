# News_Classification-lab
En este repositorio se subirá la tarea 4 del curso Data Science con Python del año 2025-2.

## Interpretación de resultados – Clasificación RSS de RPP

### 1️⃣ Consistencia de las predicciones con el LLM
Al comparar las predicciones de los tres modelos entrenados en AG News frente a las etiquetas generadas por el LLM:

- Ningún modelo alcanza F1 perfecto, lo que indica que **las predicciones no son completamente consistentes** con el LLM.
- Esto es esperable, ya que los artículos de RPP no pertenecen exactamente al mismo dominio que AG News, y los modelos pueden tener dificultades para generalizar.

---

### 2️⃣ Modelo que se alinea mejor
Según los valores de F1 Score:

| Modelo      | F1 Score |
|------------|-----------|
| RoBERTa    | 0.40      |
| DeBERTa    | 0.60      |
| ModernBERT | 0.20      |

- **DeBERTa** es el modelo que mejor se alinea con la clasificación del LLM.
- RoBERTa tiene desempeño intermedio, y ModernBERT el más bajo, probablemente debido a diferencias en preentrenamiento o capacidad de generalización.

---

### 3️⃣ Posibles razones de las discrepancias

1. **Dominio de preentrenamiento**:  
   - Los modelos fueron entrenados en AG News (noticias internacionales), pero los artículos de RPP son específicos de Perú y su estilo de redacción puede diferir, afectando la generalización.

2. **Longitud y complejidad del texto**:  
   - Algunos artículos de RPP pueden ser más largos o contener descripciones más complejas que los ejemplos de AG News, lo que dificulta la predicción correcta.

3. **Categorías semánticas ambiguas**:  
   - Algunos artículos pueden tocar varios temas a la vez (por ejemplo, economía y tecnología), y los modelos solo predicen una categoría, mientras que el LLM puede interpretar mejor el contexto global.

4. **Tamaño del dataset LLM**:  
   - Solo se clasificaron 50 artículos, lo que es un conjunto pequeño. Las métricas F1 pueden variar con pocos datos.

---

### 4️⃣ Conclusión
- **DeBERTa** es el modelo más confiable para este conjunto de noticias en términos de alineación con el LLM.  
- Las diferencias entre modelos resaltan la importancia de **adaptar modelos preentrenados a nuevos dominios** y considerar **el contexto y longitud del texto** para mejorar la consistencia.
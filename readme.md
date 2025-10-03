# Proyecto Tesis UNI

## 📂 Estructura del repositorio
- **data/raw/** → Dataset original (1000 frases políticas en español).
- **notebooks/** → EDA y fine-tuning BETO.
- **src/web/** → Prototipo en Flask.
- **src/beto_gpu/** → Documentación del modelo fine-tuned.
- **logs/** → Resultados y métricas.
- **README.md** → Documento principal.

## 📊 Dataset
- **Fuente:** Dataset propio recopilado y etiquetado manualmente.
- **Clases:** 4 categorías de retórica política.
- **Formato:** CSV y XLSX.

## 🧠 Modelos
- **Baseline:** Modelo simple (Naive Bayes, Regresión logística).
- **Fine-tuned BETO:**  
  - Modelo base: `dccuchile/bert-base-spanish-wwm-cased`  
  - Épocas: 5  
  - Batch size: 8  
  - Learning rate: 3e-5  
  - Métrica principal: Accuracy y F1-score  

## 📈 Resultados
- Baseline: Accuracy ≈ 0.65  
- BETO Fine-tuned: Accuracy ≈ 0.88, F1 ≈ 0.87  

## 🌐 API Publicada en Hugging Face
El modelo fine-tuned BETO para clasificación de frases políticas está disponible en:
👉 [Hugging Face Hub – jcam121212/beto-politico](https://huggingface.co/jcam121212/beto-politico)

## 🌐 Prototipo Web
- Implementado en Flask.  
- Permite ingresar frases políticas y clasificarlas automáticamente.

### Cómo usarlo en Python
```python
from transformers import pipeline

# Cargar el modelo publicado
classifier = pipeline("text-classification", model="jcam121212/beto-politico")

# Ejemplo de uso
texto = "Reduciremos la pobreza en un 10% en los próximos años"
print(classifier(texto))

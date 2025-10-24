# 🧠 Sprint 2 – Experimentos BETO (Clasificación Retórica Multiclase)

Este módulo contiene los experimentos del **Sprint 2** del proyecto **EnTuPePa**, cuyo objetivo es detectar estrategias retóricas en discursos políticos peruanos mediante modelos de lenguaje en español (BETO).


## 📂 Estructura del repositorio
- **data/raw/** → Dataset original (1000 frases políticas en español).
- **notebooks/** → EDA y fine-tuning BETO.
- **src/web/** → Prototipo en Flask.
- **src/beto_gpu/** → Documentación del modelo fine-tuned.
- **logs/** → Resultados y métricas.
- **README.md** → Documento principal.

## 📊 Dataset
- **Fuente:** Dataset propio con 1000 frases recopiladas y etiquetadas manualmente.
- **Clases:** 4 categorías de retórica política.
- **Formato:** CSV

## 🧠 Modelos
- **Baseline:** Modelo simple (Naive Bayes, Regresión logística).
- **Fine-tuned BETO:**  
  - Modelo base: `dccuchile/bert-base-spanish-wwm-cased`  
  - Épocas: 5  
  - Batch size: 8  
  - Learning rate: 3e-5  
  - Métrica principal: Accuracy y F1-score  

# 🧠 Sprint 2 – Experimentos BETO (Clasificación Retórica)

Este repositorio contiene los experimentos realizados para el Sprint 2 del proyecto *EnTuPePa*, enfocado en la detección de estrategias retóricas en discursos políticos peruanos.

## 📂 Estructura
- `notebooks/Experimentos/`: contiene los notebooks de entrenamiento y comparación
- `logs/Experimentos/metrics_experimentos.csv`: métricas registradas de cada variante
- `results/`: resultados comparativos (tabla y gráfico de F1)
- `data/raw/`: corpus político utilizado (no se versiona por tamaño)

## ⚙️ Experimentos
| Variante | Descripción | Cambios |
|-----------|-------------|----------|
| Baseline | Configuración estándar de BETO | — |
| Var1 | Aumento de tasa de aprendizaje | `learning_rate = 3e-5` |
| Var2 | Aumento de longitud máxima | `max_length = 256` |

## 📊 Resultados
| Variante | Accuracy | F1 | Tiempo (s) |
|-----------|-----------|----|-------------|
| Baseline | 0.85 | 0.83 | 52 |
| Var1 | 0.87 | 0.85 | 56 |
| Var2 | 0.89 | 0.87 | 63 |




## 🌐 Prototipo Web
- Implementado en Flask.  
- Permite ingresar frases políticas y clasificarlas automáticamente.


## 🧩 Cómo reproducir
```bash
pip install -r requirements.txt
cd notebooks/Experimentos/
jupyter notebook run_experimento_sprint2_beto_baseline.ipynb
jupyter notebook run_experimento_sprint2_beto_var1.ipynb
jupyter notebook run_experimento_sprint2_beto_var2.ipynb

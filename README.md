# Beta Bank — Churn (Sprint 10)

Predicción de deserción de clientes (*churn*) para **Beta Bank**. El objetivo fue **maximizar F1** y reportar **AUC-ROC** usando un pipeline reproducible.

## Enlace al notebook
- GitHub: https://github.com/christiansandovalgarcia01-creator/beta-bank-churn-report/blob/main/notebook.ipynb  
- nbviewer (render rápido): https://nbviewer.org/github/christiansandovalgarcia01-creator/beta-bank-churn-report/blob/main/notebook.ipynb

## Resumen técnico
- **Preprocesamiento**: imputación *(num: median; cat: most_frequent)* → **One-Hot** → **escalado** (todo dentro de `Pipeline` para evitar leakage).
- **Modelos base**: Logistic Regression / Decision Tree / RandomForest.
- **Desbalance**: `class_weight='balanced'` + **ajuste de umbral** para maximizar **F1**. *(Opcional probado: upsampling simple)*.
- **Selección**: comparación por F1 en validación, umbral óptimo por búsqueda en rejilla.
- **Métricas (test)**:  
  - **F1**: PON_AQUI_EL_VALOR  
  - **AUC-ROC**: PON_AQUI_EL_VALOR

## Estructura del trabajo
1. Carga y limpieza
2. Exploración y balance de clases
3. Partición estratificada (train/valid/test)
4. Pipeline con imputación + OHE + escalado
5. Baselines sin tratar desbalance
6. Estrategias contra el desbalance (class_weight, umbral; upsampling opcional)
7. Búsqueda breve de hiperparámetros
8. Entrenamiento final + evaluación en test
9. Interpretabilidad (coeficientes/importancias)
10. Conclusiones y próximos pasos

## Datos
`Churn.csv` (variables demográficas, comportamiento y objetivo `Exited`).

---

**Autor:** Christian Sandoval — Data Science & SAP (FI/MM/PP)  
**Contacto:** LinkedIn / GitHub

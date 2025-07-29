# 🔍 Projeto de Classificação de Viabilidade de Projetos

Este projeto utiliza **Regressão Logística** para classificar a **viabilidade de projetos** com base em três atributos principais:

- `investment` (investimento necessário)
- `expected_return` (retorno esperado)
- `impact_score` (pontuação de impacto)

O modelo é treinado usando dados históricos e depois pode ser reutilizado para prever a viabilidade de novos projetos.

---

## 🧠 Tecnologias Utilizadas

- Python
- Pandas
- NumPy
- Scikit-learn
- Joblib

---

## 📁 Estrutura do Projeto

- `projects_data.csv` - Conjunto de dados de entrada com projetos rotulados.
- `logistic_model.joblib` - Modelo treinado salvo para reuso.
- `logistic_model_scaler.joblib` - Scaler utilizado na padronização dos dados.
- `logistic_model_metrics.joblib` - Métricas de avaliação do modelo.

---

## 🚀 Como Funciona

1. Se o modelo treinado **já existir**, ele será carregado.
2. Caso contrário:
   - Os dados são carregados de `projects_data.csv`.
   - Os dados são padronizados.
   - O modelo é treinado com **Regressão Logística**.
   - As métricas de avaliação são calculadas e salvas.
3. Com o modelo carregado ou recém-treinado, novos projetos podem ser avaliados quanto à viabilidade.

---

## 📊 Exemplo de Uso

```python
new_projects = [{
    "investment": 13000,
    "expected_return": 69000,
    "impact_score": 7
}]

predictions, metrics = train_or_predict(new_projects)

if predictions is not None:
    print("\nNovos Projetos e Viabilidade")
    print(predictions)

    print("\nMétricas do Modelo:")
    print(metrics)

# telco-churn-logistic-regression
# Previsão de Churn de Clientes com Regressão Logística

## 📌 Visão Geral do Projeto

Este projeto utiliza **Regressão Logística** para prever o churn (cancelamento) de clientes em uma empresa de telecomunicações.  
O churn ocorre quando um cliente deixa a empresa para migrar para um concorrente. Como reter clientes é geralmente mais barato do que adquirir novos, a previsão de churn é um problema estratégico importante para o negócio.

O objetivo principal é identificar **quais clientes têm maior probabilidade de deixar a empresa**, com base em informações demográficas e de uso de serviços.

---

## 📊 Descrição do Conjunto de Dados

O conjunto de dados utilizado é o **Telco Churn**, um dataset hipotético de telecomunicações no qual:

- Cada linha representa um cliente
- As colunas descrevem características demográficas, informações de conta e serviços contratados
- A variável alvo é **`churn`**, que indica se o cliente deixou a empresa

### Principais variáveis utilizadas:
- `tenure` – Tempo de relacionamento com a empresa
- `age` – Idade do cliente
- `address` – Tempo de residência no endereço atual
- `income` – Renda do cliente
- `ed` – Nível de escolaridade
- `employ` – Tempo de emprego
- `equip` – Informações relacionadas a equipamentos
- `callcard` – Uso de cartão telefônico (quando aplicável)
- `wireless` – Uso de serviços sem fio (quando aplicável)
- `churn` – Variável alvo (0 = não cancelou, 1 = cancelou)

---

## 🧠 Metodologia

O projeto segue um pipeline padrão de Machine Learning:

1. **Carregamento dos Dados**
   - Dataset carregado a partir do arquivo `ChurnData.csv`

2. **Pré-processamento**
   - Seleção de variáveis relevantes
   - Conversão da variável alvo para formato binário
   - Normalização dos dados utilizando `StandardScaler`

3. **Divisão em Treino e Teste**
   - 80% dos dados para treino
   - 20% dos dados para teste

4. **Modelagem**
   - Treinamento de um classificador de Regressão Logística com Scikit-learn

5. **Avaliação do Modelo**
   - Predição das probabilidades com `predict_proba`
   - Avaliação do desempenho usando **Log Loss**

---

## 📉 Métrica de Avaliação: Log Loss

O **Log Loss (Binary Cross-Entropy)** mede o quão bem as probabilidades previstas pelo modelo se aproximam dos valores reais.

- Penaliza fortemente previsões erradas com alta confiança
- Quanto menor o valor do log loss, melhor o desempenho do modelo
- Métrica especialmente adequada para modelos probabilísticos, como a Regressão Logística

---

## 🧪 Análise de Variáveis

Foram realizados experimentos de **seleção de variáveis**, incluindo:

- Adição de novas variáveis (`callcard`, `wireless`)
- Remoção de variáveis potencialmente irrelevantes (`equip`, `income`, `employ`)

O impacto de cada modificação foi avaliado observando-se a variação do log loss, permitindo identificar quais variáveis contribuem positivamente ou negativamente para o desempenho do modelo.

---

## 🛠️ Tecnologias Utilizadas

- Python
- NumPy
- Pandas
- Scikit-learn
- Jupyter Notebook

---

## 📌 Principais Conclusões

- A Regressão Logística é eficaz para problemas de classificação binária
- A seleção adequada de variáveis impacta significativamente o desempenho do modelo
- Remover variáveis irrelevantes pode melhorar a capacidade de generalização
- O log loss é uma métrica mais informativa do que a acurácia para modelos probabilísticos

---

## 🚀 Possíveis Melhorias Futuras

- Aplicar regularização L1 ou L2 para seleção automática de variáveis
- Comparar o desempenho com outros algoritmos (Random Forest, SVM, XGBoost)
- Utilizar métricas adicionais como ROC-AUC
- Implementar validação cruzada para maior robustez

---

## 👤 Autor

Projeto desenvolvido com fins educacionais para demonstrar a aplicação de Regressão Logística na previsão de churn de clientes.


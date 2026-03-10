# 📊 Análise de Evasão de Clientes (Churn) — Telecom X

Desafio Telecom X - Parte 2 da Alura / Oracle Next Education

---

# 🤖 Modelagem Preditiva de Churn

Após a etapa inicial de análise exploratória, o projeto evolui para a **construção de modelos de Machine Learning** capazes de prever a evasão de clientes.

O objetivo dessa etapa é transformar os insights obtidos na análise exploratória em um **modelo preditivo capaz de identificar clientes com risco de cancelamento**.

Isso permite que empresas adotem **estratégias proativas de retenção**, reduzindo perdas financeiras e melhorando a experiência do cliente.

---

# 🧠 Abordagem de Machine Learning

O processo de modelagem seguiu as seguintes etapas:

1. Separação dos dados em **treino e teste**
2. Criação de um **modelo baseline (Dummy Classifier)**
3. Treinamento de modelos de Machine Learning
4. Validação cruzada
5. Comparação de métricas
6. Otimização de variáveis
7. Otimização de hiperparâmetros
8. Análise de importância das variáveis

Essa abordagem garante que os modelos sejam avaliados de forma **justa, robusta e confiável**.

---

# 🤖 Modelos Utilizados

Foram avaliados três modelos:

### Dummy Classifier

Utilizado como **baseline**, esse modelo sempre prevê a classe majoritária.

Seu objetivo é estabelecer um **nível mínimo de desempenho** que qualquer modelo real deve superar.

---

### Regressão Logística

Modelo estatístico amplamente utilizado em problemas de classificação binária.

Vantagens:

* Fácil interpretação
* Boa generalização
* Permite análise de importância das variáveis

---

### Árvore de Decisão

Modelo baseado em regras que divide os dados em diferentes ramos até chegar a uma decisão.

Vantagens:

* Fácil interpretação
* Capaz de capturar relações não lineares

---

# 📊 Métricas de Avaliação

Os modelos foram avaliados utilizando as seguintes métricas:

* **Accuracy (Acurácia)**
* **Precision (Precisão)**
* **Recall**
* **F1-Score**

Para o problema de churn, a métrica mais importante é o **Recall da classe de churn**, pois indica a capacidade do modelo de identificar clientes que realmente irão cancelar.

---

# 🔁 Validação Cruzada

Foi utilizada **validação cruzada com 5 folds** para verificar a capacidade de generalização dos modelos.

Esse método reduz o risco de **overfitting**, garantindo que os modelos não estejam apenas memorizando os dados de treinamento.

---

# ⚙️ Seleção de Variáveis

Foi aplicada a técnica **RFECV (Recursive Feature Elimination with Cross Validation)** para identificar as variáveis mais relevantes para o modelo.

Algumas variáveis removidas durante esse processo foram:

* StreamingTV
* Partner
* MultipleLines
* PaymentMethod_Bank transfer (automatic)
* StreamingMovies
* PaymentMethod_Credit card (automatic)
* PaymentMethod_Mailed check
* Contract_One year

A remoção dessas variáveis ajuda a:

* Reduzir complexidade do modelo
* Melhorar generalização
* Diminuir ruído nos dados

---

# 🔧 Otimização de Hiperparâmetros

Foi aplicado **GridSearchCV** para encontrar as melhores configurações para os modelos.

### Árvore de Decisão

Melhores parâmetros encontrados:

* max_depth = 5
* min_samples_split = 2
* min_samples_leaf = 4

---

### Regressão Logística

Melhores parâmetros encontrados:

* C = 0.1
* penalty = L2
* solver = liblinear
* class_weight = balanced

---

# 🧩 Importância das Variáveis

A análise de importância das variáveis mostrou que os principais fatores associados ao churn são:

* **Contract_Month-to-month**
* **tenure**
* **Charges.Monthly**
* **InternetService_Fiber optic**
* **PaymentMethod_Electronic check**

Essas variáveis indicam que o churn está fortemente relacionado a:

* Tipo de contrato
* Tempo de permanência
* Valor do serviço
* Tipo de serviço contratado

---

# 🏆 Melhor Modelo

Mesmo após otimizações, a **Regressão Logística apresentou melhor capacidade de identificar churn**, especialmente devido ao seu **alto recall para clientes que cancelam**.

A Árvore de Decisão melhorou significativamente após a otimização de hiperparâmetros, porém ainda apresentou desempenho inferior na detecção de churn.

Por esse motivo, a **Regressão Logística foi considerada o modelo final mais adequado para o problema**.

---

# 💡 Recomendações de Negócio

Com base na análise, algumas estratégias podem ajudar a reduzir o churn:

### Incentivar contratos de longo prazo

Clientes com contratos mensais apresentam maior evasão.

Oferecer descontos ou benefícios para contratos anuais pode aumentar a retenção.

---

### Focar nos primeiros meses do cliente

Grande parte do churn ocorre no início do relacionamento.

Programas de **onboarding e acompanhamento inicial** podem reduzir cancelamentos precoces.

---

### Revisar estratégia de preços

Mensalidades mais altas estão associadas a maior churn.

Planos mais flexíveis podem melhorar retenção.

---

### Promover serviços adicionais

Serviços como **OnlineSecurity** e **TechSupport** estão associados a menor evasão.

Pacotes combinados podem aumentar fidelização.

---

# 📌 Conclusão

Este projeto demonstra como técnicas de **análise de dados e machine learning** podem transformar dados brutos em **insights estratégicos para o negócio**.

Além de identificar os principais fatores relacionados ao churn, também foi possível desenvolver um **modelo preditivo capaz de identificar clientes com risco de cancelamento**.

Com essas informações, empresas podem criar **estratégias de retenção mais inteligentes e baseadas em dados**, reduzindo perdas e melhorando a experiência dos clientes.

---

---

# ▶️ Como Executar o Projeto

Existem duas formas simples de executar este projeto.

## 1️⃣ Clonar o Repositório

No terminal, execute:

```bash
git clone <URL_DO_REPOSITORIO>
cd <NOME_DA_PASTA>
```

Depois disso, abra o arquivo **TelecomX2.ipynb**.

---

## 2️⃣ Executar no Google Colab

1. Acesse: [https://colab.research.google.com](https://colab.research.google.com)
2. Clique em **Upload Notebook**
3. Selecione o arquivo **TelecomX2.ipynb**
4. Execute as células em ordem.

Caso necessário, faça também o upload da base de dados utilizada no projeto.

---

# 🛠 Tecnologias Utilizadas

Este projeto foi desenvolvido utilizando as seguintes tecnologias:

* **Python**
* **Pandas**
* **NumPy**
* **Scikit‑learn**
* **Matplotlib**
* **Seaborn**
* **Google Colab**

Essas ferramentas foram utilizadas para processamento de dados, análise exploratória, construção dos modelos de machine learning e visualização dos resultados.

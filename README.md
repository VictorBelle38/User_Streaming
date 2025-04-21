# 🎬 User Prediction para Plataforma de Streaming

Este projeto tem como objetivo **prever o cancelamento de clientes (churn)** em uma plataforma de streaming, com base no histórico de uso, perfil do cliente e tipo de assinatura. A análise inclui desde a exploração dos dados até a modelagem com algoritmos de classificação.

---

## 📂 Dados

Os dados utilizados são uma adaptação de um conjunto disponível no Kaggle:

🔗 [E-commerce Customer Churn Dataset (Kaggle)](https://www.kaggle.com/datasets/ankitverma2010/ecommerce-customer-churn-analysis-and-prediction?select=E+Commerce+Dataset.xlsx)

📄 Arquivo usado: [`streaming_data.csv`](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/75a740fb-4146-455a-8d13-6a24ba56d2c8/streaming_data.csv)

### Principais colunas do dataset:

| Coluna                 | Descrição                                               |
|------------------------|---------------------------------------------------------|
| `client_id`            | Identificador do cliente                                |
| `age`                  | Idade                                                   |
| `gender`               | Gênero                                                  |
| `region`               | Região de origem                                        |
| `subscription_days`    | Dias com assinatura ativa                               |
| `subscription_type`    | Tipo de conta (Basic, Standard, Premium)               |
| `num_contents`         | Total de conteúdos assistidos                           |
| `avg_rating`           | Avaliação média dos conteúdos                           |
| `num_active_profiles`  | Número de perfis ativos                                 |
| `num_streaming_services` | Quantos streamings o cliente assina                   |
| `devices_connected`    | Dispositivos conectados à conta                         |
| `churned`              | Cancelou a conta? (0 = Não, 1 = Sim)                    |

---

## 🔍 Etapas do Projeto

### 1. 📊 Análise Exploratória (EDA)
- Verificação de tipos de dados
- Tratamento de valores nulos
- Estatísticas descritivas

### 2. 🛠️ Preparação dos Dados
- Substituição de valores ausentes
- Codificação de variáveis categóricas
- Normalização com `MinMaxScaler`

### 3. 🤖 Modelagem
- **Regressão Logística** como baseline
- **Random Forest Classifier** com `GridSearchCV` para ajuste de hiperparâmetros
- Avaliação com **Matriz de Confusão** e **Classification Report**

### 4. 🔮 Predição
- Predição com novos dados
- Cálculo da probabilidade de churn

---

## 🧠 Principais Bibliotecas Usadas

- `pandas`, `numpy`
- `scikit-learn`
- `seaborn`, `matplotlib`

---

## 📈 Resultados

- **Modelo base (Regressão Logística)**: desempenho razoável, servindo como benchmark
- **Modelo final (Random Forest + Tuning)**: melhor F1-score e maior capacidade de generalização
- **Insights**:
  - Clientes com menos dias de assinatura e menos dispositivos conectados tendem a cancelar
  - Tipo de plano e região também influenciam na decisão

---

## 📌 Como Executar

1. Clone este repositório:
   ```bash
   git clone https://github.com/victorbelle38/User_Streaming.git
   cd churn-streaming-model

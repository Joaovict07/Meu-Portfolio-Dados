# Previsão de vitória do League of Legends

Este projeto de **Machine Learning** tem como objetivo prever o resultado (Vitória ou Derrota) de uma partida de *League of Legends* utilizando dados estatísticos do jogo. Desenvolvido como um estudo prático de Ciência de Dados e Machine Learning.

## Objetivo do Projeto
Construir e treinar um modelo de classificação capaz de aprender os padrões que levam à vitória em Summoner's Rift. O modelo analisa o desempenho do jogador durante a partida e tenta prever o desfecho com base nas suas métricas.

## 📊 Dados Utilizados
Os dados provêm de estatísticas de partidas reais de LoL (`MatchStatsTbl.csv`) obtidos de um dataset público do [Kaggle](https://www.kaggle.com/datasets/prathamku2407u660/league-of-legends-match-stats). As principais variáveis (features) analisadas incluem:
* **KDA** (Kills, Deaths, Assists - Abates, Mortes e Assistências)
* **Total Gold** (Ouro total acumulado)
* **Damage Dealt** (Dano total causado)
* **Vision Score** (Pontuação de visão)
* **Objetivos** (Dragões e Barões abatidos)
* **Lane** (A posição do jogador na partida)

### Desafio Analítico e Tratamento de Dados
Durante a fase de exploração, identificou-se uma peculiaridade com a API em relação à posição de **Suporte**. Para garantir a integridade do modelo, foi realizado um tratamento específico, agrupando as categorias `'UTILITY'` e `'NONE'` para representar corretamente a *lane* de suporte nas análises.

## A Evolução do Modelo (Machine Learning)
O desenvolvimento passou por uma evolução contínua:

1. **Regressão Logística (Baseline):** O primeiro modelo testado. Embora simples, ajudou a estabelecer uma linha de base.
2. **Normalização de Dados (`StandardScaler`):** Identificou-se que a diferença de escala entre as variáveis (ex: Dano em dezenas de milhares vs. Kills em unidades) estava a prejudicar o modelo e a causar falsos negativos. O `StandardScaler` foi implementado para nivelar o "peso" matemático de cada variável.
3. **Random Forest (O Modelo Final):** Para capturar a complexidade e as não-linearidades do jogo de forma mais eficaz, o modelo evoluiu para um algoritmo de *Floresta Aleatória* (`Random Forest`), alcançando resultados superiores nas previsões.

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Manipulação de Dados:** Pandas
* **Machine Learning:** Scikit-learn
* **Visualização:** Seaborn, Matplotlib
* **Ambiente:** Jupyter Notebook

## 🚀 Como Executar o Projeto

1. Clone o repositório.
2. Instale as dependências listadas no `requirements.txt`:
   ```bash
   pip install -r requirements.txt
3. Abra o ficheiro modelo_previsao_lol.ipynb no Jupyter Notebook ou na sua IDE preferida.

4. Execute as células para ver o carregamento dos dados, o treino do modelo e a previsão.
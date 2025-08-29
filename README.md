# 🧠 Projeto de Análise de Dados do Censo com Redes Neurais MLP e KNN

## 📋 Descrição do Projeto

Este projeto implementa e compara dois algoritmos de Machine Learning para prever se a renda anual de um indivíduo excede US$ 50.000/ano, utilizando dados do Censo dos Estados Unidos de 1994. O projeto combina **Multi-Layer Perceptron (MLP)** e **K-Nearest Neighbors (KNN)** para análise preditiva.

## 🎯 Objetivo

Desenvolver modelos de classificação capazes de prever com precisão se um indivíduo tem renda anual superior a US$ 50.000 baseado em características demográficas, educacionais e profissionais.

## 📊 Dataset

### Fonte dos Dados
- **Origem**: UCI Machine Learning Repository
- **Fonte original**: Census Bureau Database (1994)
- **Tamanho**: 48.842 instâncias (32.561 treino, 16.281 teste)
- **Classes**: 
  - `>50K`: 23.93% (classe minoritária)
  - `<=50K`: 76.07% (classe majoritária)

### Características do Dataset
- **Tipo**: Mistura de variáveis contínuas e discretas
- **Dimensões**: 15 features
- **Características principais**:
  - Idade, classe de trabalho, educação
  - Estado civil, ocupação, raça, sexo
  - Ganhos de capital, perdas de capital
  - Horas trabalhadas por semana, país de origem

## 🏗️ Arquitetura da Solução

### 1. Pré-processamento dos Dados
- **Limpeza**: Remoção de valores nulos e espaços em branco
- **Codificação**: Transformação de variáveis categóricas usando LabelEncoder
- **Normalização**: Padronização dos dados com StandardScaler
- **Redução de dimensionalidade**: PCA mantendo 95% da variância

### 2. Divisão dos Dados
- **Treino**: 80% dos dados
- **Teste**: 20% dos dados
- **Validação cruzada**: Para otimização de hiperparâmetros

## 🤖 Modelos Implementados

### Multi-Layer Perceptron (MLP)
**Arquitetura otimizada:**
- **Camada de entrada**: 15 features
- **Camada oculta**: 30 neurônios
- **Camada de saída**: 1 neurônio (classificação binária)
- **Função de ativação**: tanh
- **Taxa de aprendizado**: 0.001
- **Solver**: Adam
- **Máximo de iterações**: 500-1000

**Vantagens:**
- Capacidade de capturar relações não-lineares complexas
- Boa generalização para padrões complexos
- Melhor performance em métricas críticas

### K-Nearest Neighbors (KNN)
**Parâmetros otimizados:**
- **Número de vizinhos (k)**: 3, 5, 7, 9, 11
- **Pesos**: uniform, distance
- **Métrica de distância**: euclidean, manhattan

**Características:**
- Algoritmo baseado em instâncias
- Simples de implementar e interpretar
- Sensível à dimensionalidade dos dados

## 📈 Resultados e Performance

### Métricas de Avaliação
- **Acurácia**: Medida geral de acertos
- **Precisão**: Proporção de predições positivas corretas
- **Recall**: Proporção de casos positivos identificados
- **F1-Score**: Média harmônica entre precisão e recall

### Performance dos Modelos

#### MLP
- **Acurácia**: Superior em validação cruzada e teste
- **Classe majoritária (<=50K)**: 
  - Recall: 93%
  - F1-Score: 91%
- **Classe minoritária (>50K)**:
  - F1-Score: 66%
  - Desafios com desbalanceamento de classes

#### KNN
- **Acurácia**: Competitiva com MLP
- **Performance**: Boa em classes majoritárias
- **Limitações**: Menor capacidade de generalização

## 🔍 Análise de Trade-offs

### MLP vs KNN
- **MLP**: Melhor em capturar padrões complexos, mas requer mais dados e pode overfitting
- **KNN**: Simples e interpretável, mas sensível à dimensionalidade e custoso computacionalmente

### Arquitetura vs Performance
- **Simplicidade**: Arquitetura simples (1 camada, 30 neurônios) oferece boa acurácia
- **Complexidade**: Mais camadas poderiam melhorar recall para classe minoritária
- **Balanceamento**: Trade-off entre simplicidade e capacidade de capturar padrões complexos

## 🛠️ Tecnologias Utilizadas

- **Python**: Linguagem principal
- **Pandas**: Manipulação e análise de dados
- **NumPy**: Computação numérica
- **Scikit-learn**: Implementação dos modelos e métricas
- **Matplotlib/Seaborn**: Visualizações
- **Jupyter Notebook**: Desenvolvimento e documentação

## 📁 Estrutura do Projeto

```
mlb/
├── README.md                 # Este arquivo
├── rede_neural.ipynb        # Notebook principal com implementação
├── data/                     # Diretório de dados
│   └── adult/               # Dataset do Censo
│       ├── adult.data       # Dados de treinamento
│       ├── adult.test       # Dados de teste
│       ├── adult.names      # Descrição das features
│       └── old.adult.names  # Documentação original
└── .git/                     # Controle de versão
```

## 🚀 Como Executar

1. **Clone o repositório:**
   ```bash
   git clone [URL_DO_REPOSITORIO]
   cd mlb
   ```

2. **Instale as dependências:**
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn jupyter
   ```

3. **Execute o notebook:**
   ```bash
   jupyter notebook rede_neural.ipynb
   ```

## 📊 Visualizações Incluídas

- **Análise exploratória dos dados**
- **Distribuição das variáveis**
- **Matriz de correlação**
- **Resultados de otimização de hiperparâmetros**
- **Comparação de performance entre modelos**
- **Análise de impacto dos parâmetros**

## 🎓 Conclusões

O **MLP** demonstrou ser o modelo superior para este problema específico, oferecendo:
- Maior acurácia geral
- Melhor capacidade de modelar relações não-lineares
- Performance superior em métricas críticas para a classe minoritária

O **KNN** apresentou performance competitiva, mas com limitações em:
- Capacidade de generalização
- Sensibilidade à dimensionalidade
- Custo computacional em predição

## 🔮 Próximos Passos

- **Balanceamento de classes**: Implementar técnicas como SMOTE ou undersampling
- **Feature engineering**: Criar novas variáveis derivadas
- **Ensemble methods**: Combinar MLP e KNN para melhor performance
- **Otimização avançada**: Usar técnicas como Bayesian optimization
- **Deploy**: Implementar modelo em produção

## 👥 Autores

Desenvolvido como parte de um projeto acadêmico de Machine Learning.

## 📄 Licença

Este projeto é de uso educacional e acadêmico.

---

*Para mais detalhes sobre a implementação, consulte o notebook `rede_neural.ipynb`*
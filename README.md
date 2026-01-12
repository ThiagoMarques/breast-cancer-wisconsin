# Sistema de Diagnóstico de Câncer de Mama - Breast Cancer Wisconsin

Sistema de Machine Learning para classificação de tumores de mama em benignos ou malignos, desenvolvido como parte do Tech Challenge da FIAP. O projeto utiliza o dataset público Breast Cancer Wisconsin (Diagnostic) e implementa um pipeline completo de análise de dados, pré-processamento, modelagem e avaliação.

## Sobre o Projeto

Este projeto foi desenvolvido para atender aos requisitos do Tech Challenge, focando na aplicação de técnicas de Machine Learning para classificação de doenças usando dados estruturados. O sistema utiliza múltiplos algoritmos de classificação para prever se um tumor de mama é benigno (não canceroso) ou maligno (canceroso) com base em características morfológicas das células.

## Dataset

O dataset utilizado é o **Breast Cancer Wisconsin (Diagnostic)**, disponível publicamente e amplamente utilizado em pesquisas sobre diagnóstico de câncer de mama.

### Características do Dataset

- **Total de amostras**: 569 casos
- **Total de features**: 30 características numéricas
- **Distribuição das classes**:
  - Benigno (B): 357 casos (62.74%)
  - Maligno (M): 212 casos (37.26%)
- **Qualidade dos dados**: Sem valores ausentes

### Descrição das Features

As 30 características representam três tipos de medidas calculadas para cada núcleo celular:

1. **Média (mean)**: Média das medidas para cada característica
2. **Erro Padrão (se)**: Erro padrão das medidas
3. **Pior Valor (worst)**: Média dos três maiores valores encontrados

As características medidas incluem:
- Raio (distâncias do centro até os pontos do perímetro)
- Textura (desvio padrão dos valores em escala de cinza)
- Perímetro
- Área
- Suavidade (variação local dos comprimentos do raio)
- Compacidade (perímetro² / área - 1.0)
- Concavidade (gravidade das porções côncavas do contorno)
- Pontos côncavos (número de porções côncavas do contorno)
- Simetria
- Dimensão fractal (aproximação da linha costeira - 1)

## Estrutura do Projeto

O projeto está organizado da seguinte forma:

```
breast-cancer-wisconsin/
├── datasets/
│   └── breast-cancer-dataset.csv    # Dataset utilizado
├── main.ipynb                        # Notebook principal com toda a análise
├── requirements.txt                  # Dependências do projeto
├── README.md                         # Este arquivo
└── LICENSE                           # Licença do projeto
```

## Requisitos do Tech Challenge

Este projeto atende aos seguintes requisitos obrigatórios do Tech Challenge:

### 1. Exploração de Dados

- Carregamento e exploração das características do dataset
- Estatísticas descritivas completas
- Visualizações e análise de distribuições
- Análise de balanceamento de classes
- Identificação de valores ausentes e inconsistências

### 2. Pré-processamento

- Limpeza de dados (remoção de colunas desnecessárias)
- Pipeline de pré-processamento estruturado
- Análise de correlação entre features
- Identificação de features mais relevantes
- Preparação para normalização/padronização

### 3. Modelagem

- Implementação de múltiplas técnicas de classificação
- Separação adequada dos dados (treino, validação, teste)
- Aplicação de técnicas de feature scaling quando necessário

### 4. Treinamento e Avaliação

- Treinamento dos modelos com conjunto de treinamento
- Métricas de avaliação: Accuracy, Recall, F1-score
- Matriz de confusão para análise detalhada
- Feature Importance para interpretação dos modelos
- Análise crítica dos resultados

### 5. Entregáveis

- Código Python estruturado e documentado
- Notebook Jupyter com análise completa
- README.md com documentação do projeto
- Dataset incluído no repositório
- Resultados documentados (gráficos, análises, métricas)

## Tecnologias Utilizadas

- **Python 3.x**: Linguagem de programação principal
- **Pandas**: Manipulação e análise de dados
- **NumPy**: Operações numéricas
- **Matplotlib**: Visualizações básicas
- **Seaborn**: Visualizações estatísticas avançadas
- **Scikit-learn**: Algoritmos de Machine Learning e ferramentas de pré-processamento
- **Jupyter Notebook**: Ambiente de desenvolvimento e análise

## Instalação e Configuração

### Pré-requisitos

- Python 3.7 ou superior
- pip (gerenciador de pacotes Python)

### Instalação das Dependências

1. Clone o repositório:
```bash
git clone <url-do-repositorio>
cd breast-cancer-wisconsin
```

2. Instale as dependências:
```bash
pip install -r requirements.txt
```

### Execução

Abra o notebook Jupyter:
```bash
jupyter notebook main.ipynb
```

Ou use JupyterLab:
```bash
jupyter lab main.ipynb
```

## Metodologia

### Fase 1: Exploração de Dados (EDA)

A análise exploratória inclui:

- Análise da estrutura do dataset (dimensões, tipos de dados)
- Estatísticas descritivas (média, mediana, desvio padrão, quartis)
- Visualização da distribuição das classes
- Análise de correlação entre features
- Identificação das features mais correlacionadas com o target
- Visualizações comparativas (boxplots, histogramas, violin plots)

### Fase 2: Pré-processamento

- Remoção de colunas não informativas (ID, colunas vazias)
- Verificação e tratamento de valores ausentes
- Análise de correlação para identificar multicolinearidade
- Seleção de features mais relevantes
- Preparação para normalização/padronização

### Fase 3: Modelagem

Implementação de múltiplos algoritmos de classificação:

- K-Nearest Neighbors (KNN)
- Árvore de Decisão (Decision Tree)
- Random Forest
- Outros algoritmos conforme necessário

### Fase 4: Avaliação

Avaliação dos modelos utilizando:

- **Accuracy**: Taxa de acerto geral do modelo
- **Recall**: Capacidade de identificar corretamente casos malignos (importante para diagnóstico médico)
- **F1-Score**: Média harmônica entre precisão e recall
- **Matriz de Confusão**: Análise detalhada dos erros de classificação
- **Feature Importance**: Identificação das características mais importantes para a predição

## Resultados Esperados

O sistema deve ser capaz de:

- Classificar tumores de mama com alta precisão
- Identificar corretamente casos malignos (alta sensibilidade/recall)
- Fornecer interpretabilidade através de feature importance
- Demonstrar robustez através de validação cruzada

## Análise de Resultados

Os resultados são analisados criticamente considerando:

- Performance comparativa entre diferentes algoritmos
- Importância das features para o diagnóstico
- Análise de erros (falsos positivos e falsos negativos)
- Impacto do desbalanceamento de classes
- Aplicabilidade prática em contexto médico

## Considerações Importantes

### Desbalanceamento de Classes

O dataset apresenta um desbalanceamento moderado (62.74% benignos vs 37.26% malignos). Esta característica é considerada durante a modelagem para evitar viés em favor da classe majoritária.

### Escalas dos Dados

As features apresentam escalas muito diferentes, indicando a necessidade de padronização ou normalização antes da aplicação de modelos sensíveis à escala.

### Multicolinearidade

Algumas features apresentam alta correlação entre si (como radius, perimeter e area, que são relacionadas geometricamente), o que pode afetar alguns modelos e justificar técnicas de redução de dimensionalidade.

## Próximos Passos

Melhorias futuras podem incluir:

- Implementação de validação cruzada para avaliação mais robusta
- Aplicação de técnicas de balanceamento de classes (SMOTE, undersampling)
- Otimização de hiperparâmetros (GridSearch, RandomSearch)
- Implementação de SHAP values para interpretabilidade avançada
- Containerização com Docker
- Desenvolvimento de API para deploy do modelo

## Referências

- Dataset: Breast Cancer Wisconsin (Diagnostic) - UCI Machine Learning Repository
- Scikit-learn Documentation: https://scikit-learn.org/
- Pandas Documentation: https://pandas.pydata.org/

## Licença

Este projeto está sob a licença especificada no arquivo LICENSE.

## Autor

Desenvolvido como parte do Tech Challenge da FIAP - Especialização em Inteligência Artificial e Machine Learning.

## Contribuições

Este é um projeto acadêmico desenvolvido para o Tech Challenge. Sugestões e melhorias são bem-vindas através de issues ou pull requests.

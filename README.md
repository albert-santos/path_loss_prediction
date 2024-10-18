

<p align="center">
    <img width= 100% src="Visualization/banner_pathloss_predict.png">

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)  ![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white) ![Power Bi](https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

# Previsão de Potência Recebida em Ambientes Indoor Utilizando Aprendizado de Máquina


## Acesso Rápido
- [Sobre o Projeto](#sobre-o-projeto)
- [Por que utilizar ML](#por-que-utilizar-ml)
- [Organização do Repositório](#organização-do-repositório)
- [Como Executar o Projeto](#como-executar-o-projeto)
- [Ferramentas e Tecnologias Utilizadas](#ferramentas-e-tecnologias-utilizadas)
- [Contribuições](#contribuições)
- [Modelos Treinados (2 GHz)](/2-4%20GHz%20Analysis/models/)
- [Modelos Treinados (5 GHz)](/5-2%20GHz%20Analysis/models/)
- [Licença](#licença)


## Sobre o Projeto

Este projeto explora o uso de modelos de aprendizado de máquina (ML) para prever a potência do sinal recebida por um usuário móvel dentro de um ambiente de comunicação sem fio (Wi-Fi) em um cenário indoor. A precisão dessas previsões é essencial para otimizar o planejamento de redes wireless, melhorando a qualidade de serviço (QoS) em termos de taxa de transmissão e latência, ajustando-se às necessidades de diferentes aplicações.

### Cenário de Estudo
Medições foram realizadas em um ambiente indoor utilizando um ponto de acesso Wi-Fi como transmissor e um dispositivo móvel como receptor. A distância entre eles variou de 1 a 30 metros, com incrementos de 1 metro, resultando em 30 amostras por frequência. As medições foram feitas separadamente nas bandas de 2.4 GHz e 5 GHz.


## Por que utilizar ML?

Ao invés de depender exclusivamente de modelos determinísticos tradicionais, que são baseados em equações ajustadas a partir de medições específicas, este projeto emprega ML para aumentar a precisão das previsões através de uma aprendizagem adaptativa baseada em dados reais.

Foram treinados três modelos de ML:
- **Random Forest**
- **Lasso Regression**
- **Decision Tree**

O desempenho dos modelos foi avaliado comparando as previsões da potência recebida com os valores reais medidos. A análise incluiu também uma comparação com os modelos determinísticos tradicionais de perda de percurso (path loss). 

Entre esses, o modelo `Random Forest` obteve o melhor desempenho. Sua habilidade em capturar a complexidade e não linearidades nos dados, combinada com sua robustez a ruídos e variações nos dados de entrada, resultou em previsões mais próximas dos valores reais medidos.

Abaixo está uma visualização comparativa entre os valores de potência recebida previstos pelo modelo Random Forest e os valores reais medidos. O gráfico à direita ilustra como o modelo acompanha os valores medidos em função da distância, enquanto os medidores à esquerda mostram a potência exata prevista versus a potência real medida em um determinado ponto.

<p align="center"> <img width= 80% src="Visualization/received_power_predict.gif"> </p>

Essa comparação visual permite identificar facilmente a precisão do modelo na tarefa de previsão de potência recebida em um ambiente indoor.

## Organização do Repositório

### 1. Diretórios de Análise
Cada diretório contém a análise das medições feitas em uma frequência específica:

- **2.4 GHz Analysis**: Análise de medições para a frequência de 2.4 GHz.
- **5 GHz Analysis**: Análise de medições para a frequência de 5 GHz.

Dentro de cada diretório de análise:
- **EDA**: Arquivos HTML com análise exploratória dos dados.
- **images**: Gráficos das medições e desempenho dos modelos.
- **models**: Modelos de aprendizado de máquina treinados (arquivos `.pkl`).
- **tables**: Métricas de avaliação de desempenho de cada modelo.

### 2. Notebooks
- **path_loss_prediction.ipynb**: Notebook com as etapas de análise exploratória, pré-processamento dos dados, divisão dos conjuntos de treino, validação e teste, além do treinamento dos modelos de aprendizado de máquina.
- **compare_models_and_path_loss_equation.ipynb**: Comparação dos modelos de aprendizado de máquina treinados com as equações determinísticas tradicionais de perda de percurso.

### 3. Visualização
- **Visualization**: Diretório contendo as imagens e datasets utilizados para gerar visualizações no Power BI, com foco na comparação do desempenho do modelo de melhor desempenho (Random Forest) e os valores reais.

### 4. Datasets
- **datasets**: Dados das medições de potência recebida para as frequências de 2.4 GHz e 5 GHz.

## Como Executar o Projeto

1. Clone este repositório:  
   ```bash
   git clone https://github.com/seuprojeto.git

2. Instale as dependências necessárias:
    ```bash
    pip install -r requirements.txt
3. Execute o notebook `path_loss_prediction.ipynb` para realizar a análise e treinar os modelos de ML.
4. Para visualizar a comparação entre os modelos e as equações de perda de percurso, utilize o notebook `compare_models_and_path_loss_equation.ipynb.`

## Ferramentas e Tecnologias Utilizadas

Este projeto faz uso de uma série de ferramentas e bibliotecas que auxiliam na análise e modelagem dos dados de potência de sinal em um ambiente wireless indoor. Abaixo estão listadas as principais tecnologias utilizadas:

- **Python**: Linguagem principal usada no desenvolvimento dos scripts e notebooks.
- **Pandas**: Utilizado para manipulação e análise dos dados, incluindo pré-processamento.
- **Y-data Profile**: Biblioteca utilizada para gerar um relatório de Análise Exploratória dos Dados
- **Scikit-learn**: Biblioteca principal para criação, treinamento e avaliação dos modelos de aprendizado de máquina, incluindo Random Forest, Lasso Regression e Decision Tree.
- **Matplotlib**: Ferramenta de visualização de dados usadas para gerar gráficos que ilustram o comportamento dos dados e o desempenho dos modelos.
- **Jupyter Notebooks**: Ambiente de desenvolvimento utilizado para a criação de notebooks interativos que contêm todo o processo de análise e modelagem.
- **Power BI**: Utilizado para a criação de dashboards e visualizações avançadas, permitindo uma comparação visual entre as previsões dos modelos e os dados reais.
- **Git**: Controle de versão utilizado para gerenciar o desenvolvimento do projeto de forma colaborativa e organizada.

## Contribuições

## Licença

Este projeto está licenciado sob a Licença MIT. Para mais detalhes consulte o arquivo  [![MIT license](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/albert-santos/path_loss_prediction/blob/main/LICENSE)









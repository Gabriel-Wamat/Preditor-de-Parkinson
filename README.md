# CAMPUS PARTY - EDITION

## Descrição do Projeto

Este projeto utiliza aprendizado profundo com modelos baseados em `DenseNet`, `ResNet` e `VGG` para classificação de imagens de desenhos de pacientes com Parkinson e indivíduos saudáveis. Os dados utilizados foram extraídos do repositório do Kaggle "[Parkinson's Drawings](https://www.kaggle.com/datasets/kmader/parkinsons-drawings)".

---

## Etapas do Projeto

### 1. Instalação de Dependências e Download de Dados

```bash
!pip install kaggle
```

Configuração do ambiente Kaggle:

```python
from google.colab import drive
drive.mount('/content/drive')
import os
os.environ['KAGGLE_CONFIG_DIR'] = '/content/drive/MyDrive/kaggle'
```

Download e extração dos dados:

```bash
!kaggle datasets download -d kmader/parkinsons-drawings
```

### 2. Preparo dos Dados

* Leitura de imagens (OpenCV)
* Balanceamento com data augmentation (rotações e flips)
* Redimensionamento com e sem padding
* Segmentação binária
* Normalização

### 3. Exploração dos Dados

* Gráficos de distribuição de classes e resoluções
* Amostras de imagens da base de treino/teste

### 4. Modelos Utilizados

#### DenseNet121

* Padded e Resized
* Melhores resultados com dados padded

#### ResNet50

* Base congelada
* Resultados razoáveis, mas inferior ao VGG e DenseNet

#### VGG16

* Melhor performance geral nos dados `resized` com accuracy de até **98%**

### 5. Avaliação

* Acurácia
* F1-score
* Matriz de confusão
* Curva AUC-ROC
* Visualização de erros de classificação

### 6. Ensemble (a ser declarado)

* Combinação de predições dos modelos para robustez

---

## Resultados

* **DenseNet (Padded):** \~91% accuracy
* **DenseNet (Resized):** \~85% accuracy
* **ResNet:** \~66% accuracy (Padded), \~60% (Resized)
* **VGG16:** \~85% (Padded), \~98% (Resized)

---

## Como Rodar o Projeto

1. Clone este repositório
2. Suba no Google Colab
3. Siga as seções do notebook:

   * `Download dependencies and data`
   * `Processing data`
   * `Train models`
   * `Evaluate models`

---

## Requisitos

* Python 3.10+
* TensorFlow
* Keras
* OpenCV
* scikit-learn
* Matplotlib
* Kaggle CLI

---

## Licença dos Dados

* [Kaggle Parkinson's Drawings](https://www.kaggle.com/datasets/kmader/parkinsons-drawings)
* Licença: CC BY-NC-ND 4.0

---





# Detecção de Parkinson a partir de Desenhos de Espirais – Deep Learning 🧠✏️

[![TensorFlow 2.15+](https://img.shields.io/badge/TensorFlow-2.15%2B-FF6F00?logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)  
[![Licença MIT](https://img.shields.io/badge/Licença-MIT-green.svg)](#licença)  
![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)

Projeto de *deep learning* que classifica indivíduos com Doença de Parkinson a partir de imagens de espirais desenhadas à mão. Comparamos três arquiteturas de CNN (DenseNet-121, ResNet-50 e VGG-16) sob dois fluxos de pré-processamento (padding × resizing) e preparamos o terreno para um ensemble de modelos.

---

## Índice

1. [Visão geral](#visão-geral)  
2. [Dataset](#dataset)  
3. [Estrutura do repositório](#estrutura-do-repositório)  
4. [Requisitos](#requisitos)  
5. [Instalação](#instalação)  
6. [Como executar](#como-executar)  
7. [Resultados](#resultados)  
8. [Próximos passos](#próximos-passos)  
9. [Contribua](#contribua)  
10. [Licença](#licença)  
11. [Agradecimentos](#agradecimentos)  

---

## Visão geral

A escrita e o desenho de espirais apresentam alterações motoras características em pacientes com Parkinson.  
Este projeto utiliza redes neurais convolucionais para automatizar a detecção dessas alterações em imagens, auxiliando pesquisas clínicas e triagem precoce.

**Principais pontos:**

- **Fluxos de pré-processamento**  
  - **Padding** (manter proporção original)  
  - **Resizing** (normalizar tamanho)  
- **Data augmentation**: rotações, flips e zoom para robustez  
- **Modelos testados**:  
  - DenseNet-121 (pesos ImageNet)  
  - ResNet-50 (pesos ImageNet)  
  - VGG-16 (pesos ImageNet)  
- **Métricas de avaliação**: acurácia, precisão, recall, F1-score e matriz de confusão  
- Exportação dos pesos treinados em arquivos `.h5`

---

## Dataset

| Fonte            | Kaggle – `kmader/parkinsons-drawings`                         |
|------------------|----------------------------------------------------------------|
| Imagens          | 1.693 PNGs de espirais (aprox. 50 × 50 mm)                     |
| Classes          | `healthy` (controle) / `parkinson`                             |
| Licença          | Creative Commons Attribution-ShareAlike 4.0                    |

O download é feito via Kaggle API direto no notebook `Projeto_DL_Parkinson.ipynb`.

---

## Estrutura do repositório

├── data/                         # Dados brutos e processados
│   ├── raw/                      # Imagens originais
│   └── processed/                # Imagens pré-processadas
├── models/                       # Pesos treinados (.h5)
├── results/                      # Gráficos, relatórios e matrizes de confusão
├── src/                          # Códigos auxiliares (augmentação, utilitários)
│   ├── preprocess.py
│   ├── train.py                  # (em breve)
│   └── evaluate.py
├── Projeto_DL_Parkinson.ipynb    # Notebook principal
├── requirements.txt              # Dependências Python
└── README.md                     # Este arquivo

---

## Requisitos

- **Python 3.9+**  
- **TensorFlow 2.15+**  
- Bibliotecas Python:  
  - `numpy`  
  - `pandas`  
  - `matplotlib`  
  - `scikit-learn`  
  - `opencv-python`  
- **Kaggle CLI** (para download automático do dataset)

Instalação rápida:

```bash
pip install -r requirements.txt


⸻

Instalação

# 1. Clone o repositório
git clone https://github.com/<seu-usuario>/parkinson-dl.git
cd parkinson-dl

# 2. Configure suas credenciais do Kaggle
#    Coloque o arquivo kaggle.json em ~/.kaggle/

# 3. (Opcional) Crie e ative um ambiente virtual
python -m venv .venv
source .venv/bin/activate

# 4. Instale dependências
pip install -r requirements.txt


⸻

Como executar

1. Notebook (recomendado)

Abra Projeto_DL_Parkinson.ipynb no Jupyter ou Google Colab e execute as células em ordem.
O download do dataset, treinamento e avaliação são totalmente automatizados.

2. Script (em desenvolvimento)

Um script train.py será disponibilizado em src/ para execução sem interface gráfica.

⸻

Resultados

Modelo / Pré-proc.	Acurácia	Precisão (P / NP)	Recall (P / NP)	F1-score (P / NP)
DenseNet-121 / Padding	0,92	0,90 / 0,93	0,93 / 0,90	0,92 / 0,92
DenseNet-121 / Resizing	0,85	0,78 / 0,96	0,97 / 0,73	0,87 / 0,83
ResNet-50 / Padding	0,67	0,81 / 0,61	0,43 / 0,90	0,57 / 0,73
ResNet-50 / Resizing	0,60	1,00 / 0,56	0,20 / 1,00	0,33 / 0,71
VGG-16 / Padding	0,85	0,86 / 0,84	0,83 / 0,87	0,85 / 0,85
VGG-16 / Resizing	0,87	0,89 / 0,84	0,83 / 0,90	0,86 / 0,87

Melhor resultado: DenseNet-121 com padding (acurácia de 92 %).

⸻

Próximos passos
	•	Treinar ensemble ponderado das três arquiteturas
	•	Testar EfficientNet (B0–B4) e Vision Transformers
	•	Implementar Grad-CAM para interpretação de predições
	•	Converter o modelo para TensorFlow Lite e avaliar em dispositivos móveis

⸻

Contribua

Contribuições são muito bem-vindas!
	1.	Faça um fork deste repositório
	2.	Crie uma branch para sua feature (git checkout -b feature/nome-da-feature)
	3.	Commit suas alterações (git commit -m "Adiciona nova feature")
	4.	Push para sua branch (git push origin feature/nome-da-feature)
	5.	Abra um pull request

Veja também issues para ideias e bugs abertos.

⸻

Licença

Este projeto está licenciado sob a MIT License.
Veja o arquivo LICENSE para mais detalhes.

⸻

Agradecimentos
	•	Kmader e colaboradores pelo dataset parkinsons-drawings no Kaggle
	•	Comunidade TensorFlow e Keras
	•	Discussões e insights da Campus Party 2025

⸻


<div align="center">  
Feito com ❤️ e muito café por [Seu Nome](https://github.com/<seu-usuario>)  
</div>
```

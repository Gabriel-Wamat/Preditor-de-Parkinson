# Detecção de Parkinson a partir de Desenhos de Espirais – Deep Learning 🧠✏️

[![TensorFlow 2.15+](https://img.shields.io/badge/TensorFlow-2.15%2B-FF6F00?logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)  
[![Python 3.9+](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/downloads/)  
[![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)]  
[![Licença MIT](https://img.shields.io/badge/Licença-MIT-green.svg)](#licença)

<p align="center">
  <img src="docs/spiral_example.png" alt="Exemplo de Espiral" width="300"/>
</p>

> Projeto de **deep learning** que detecta sinais de Parkinson a partir de desenhos de espirais feitos à mão, comparando três arquiteturas de CNN e dois fluxos de pré-processamento.

---

## 📋 Sumário

1. [Visão Geral](#visão-geral)  
2. [Dataset](#dataset)  
3. [Como Executar (Colab)](#como-executar-colab)  
4. [Resultados](#resultados)  
5. [Próximos Passos](#próximos-passos)  
6. [Contribuições](#contribuições)  
7. [Autores](#autores)  
8. [Licença](#licença)  

---

## 🔎 Visão Geral

- **Objetivo**: automatizar a triagem precoce de Parkinson a partir do padrão motor em desenhos.  
- **Modelos**: DenseNet-121, ResNet-50 e VGG-16 (pesos ImageNet).  
- **Pré-processamento**:  
  - **Padding** (manter proporção original)  
  - **Resizing** (normalizar tamanho)  
- **Data Augmentation**: rotações, flips e zoom.  
- **Métricas**: acurácia, precisão, recall, F1-score e matriz de confusão.  

---

## 🗃️ Dataset

| Propriedade      | Detalhes                                      |
|------------------|-----------------------------------------------|
| **Fonte**        | Kaggle – `kmader/parkinsons-drawings`         |
| **Imagens**      | 1.693 PNGs de espirais (≈ 50 × 50 mm)           |
| **Classes**      | `healthy` (controle) / `parkinson`            |
| **Licença**      | Creative Commons Attribution-ShareAlike 4.0   |

> O download é feito automaticamente via Kaggle API no notebook principal.

---

## 🚀 Como Executar (Colab)

1. **Abra no Colab**  
   👉 https://colab.research.google.com/github/seu-usuario/parkinson-dl/blob/main/Projeto_DL_Parkinson.ipynb  

2. **Instale dependências**  
   ```python
   !pip install -r requirements.txt

	3.	Configure credenciais Kaggle
	•	No painel lateral, faça upload de kaggle.json.
	•	Em seguida:

!mkdir -p ~/.kaggle
!mv kaggle.json ~/.kaggle/
!chmod 600 ~/.kaggle/kaggle.json


	4.	Execute todas as células
	•	Download do dataset
	•	Pré-processamento
	•	Treinamento
	•	Avaliação e geração de relatórios

⸻

📊 Resultados

Modelo / Pré-proc.	Acurácia	Precisão (P / NP)	Recall (P / NP)	F1-score (P / NP)
DenseNet-121 / Padding	0,92	0,90 / 0,93	0,93 / 0,90	0,92 / 0,92
DenseNet-121 / Resizing	0,85	0,78 / 0,96	0,97 / 0,73	0,87 / 0,83
ResNet-50 / Padding	0,67	0,81 / 0,61	0,43 / 0,90	0,57 / 0,73
ResNet-50 / Resizing	0,60	1,00 / 0,56	0,20 / 1,00	0,33 / 0,71
VGG-16 / Padding	0,85	0,86 / 0,84	0,83 / 0,87	0,85 / 0,85
VGG-16 / Resizing	0,87	0,89 / 0,84	0,83 / 0,90	0,86 / 0,87

Melhor: DenseNet-121 + Padding (92 % de acurácia).

⸻

🛠️ Próximos Passos
	•	Criar ensemble ponderado das três arquiteturas
	•	Testar EfficientNet (B0–B4) e Vision Transformers
	•	Implementar Grad-CAM para interpretação de predições
	•	Converter para TensorFlow Lite e avaliar em dispositivos móveis

⸻

👥 Autores
	•	Matias - Gabriel-Wamat
	•	Rafael Barbosa – RafaelB411

⸻

📄 Licença

Este projeto está licenciado sob a MIT License. Veja o arquivo LICENSE para detalhes.

⸻


<div align="center">
  <sub>Feito com ❤️ e muito café por <a href="https://github.com/seu-usuario">Seu Nome</a> e <a href="https://github.com/RafaelB411">RafaelB411</a>.</sub>
</div>
```

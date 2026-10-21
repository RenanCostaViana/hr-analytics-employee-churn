# 🧑‍💼 HR Analytics — Employee Churn Prediction

### Prevendo saída de funcionários com Machine Learning

Este projeto aplica **Machine Learning supervisionado** para prever a probabilidade de um funcionário deixar a empresa (churn), a partir de características como nível de satisfação, avaliação de desempenho, carga de projetos, tempo de casa, faixa salarial e departamento.

O objetivo é apoiar áreas de **Recursos Humanos** na identificação de riscos, na retenção de talentos e na escolha de ações para cada perfil de saída.

---

## 🚀 Objetivos do Projeto

- Explorar os dados de RH e entender os padrões relacionados ao churn
- Tratar duplicatas e outliers antes de qualquer análise
- Testar formalmente uma hipótese levantada na análise exploratória
- Comparar modelos de classificação sem vazamento de informação entre treino e teste
- Identificar os fatores que mais influenciam a saída de colaboradores

---

## 🔍 Etapas do Projeto

### 1. Validação e tratamento dos dados
- **3.005 linhas duplicadas (20% da base)** foram removidas. Mantidas, elas contariam os mesmos colaboradores mais de uma vez e colocariam cópias de um mesmo registro no treino e no teste do modelo.
- Um registro com **810 horas mensais**, acima do total de horas de um mês, foi removido como erro de digitação.
- Base final: **11.993 colaboradores, 16,6% saíram.**

### 2. Análise exploratória
Relações entre as variáveis e a saída, com a interpretação de cada padrão escrita no notebook.

### 3. Teste de hipótese
Mann-Whitney unilateral (as horas mensais não seguem distribuição normal) para testar se quem tem salário baixo trabalha mais horas.

### 4. Modelagem
Comparação de KNN, SVM e Random Forest por **validação cruzada estratificada de 5 dobras, só com o treino**. Cada modelo roda num pipeline com padronização e **SMOTE aplicado apenas na parte de treino de cada dobra**. O número de vizinhos do KNN também é escolhido por validação cruzada. O conjunto de teste é usado **uma única vez**, na avaliação final.

### 5. Avaliação
AUC, precisão, recall e F1 da classe "saiu", matriz de confusão, curva ROC e importância das variáveis por permutação.

---

## 🧠 Principais Insights

- **Existem três perfis de saída, com causas opostas:**
  - **Subaproveitados** (cerca de 3 anos de casa): avaliação baixa e poucas horas (147h/mês).
  - **Sobrecarregados** (cerca de 4 anos): 269h/mês e satisfação de apenas 0,14.
  - **Bons profissionais que saem por oportunidade** (5 e 6 anos): avaliação e satisfação altas.
- **A carga de projetos mostra os mesmos extremos:** mais da metade de quem tem 2 ou 6 projetos saiu, contra 1% a 15% nas cargas intermediárias.
- **Salário está associado à saída:** churn de **20,5%** entre salários baixos, 14,6% nos médios e **4,8%** nos altos. A taxa de promoção segue o mesmo padrão (0,7% contra 4,4%).
- **Quem ganha menos não trabalha mais horas:** as médias são praticamente iguais (cerca de 200h nas três faixas) e o teste não encontrou diferença (p ≈ 0,6). A saída maior nesse grupo aponta para remuneração e carreira, não para carga de trabalho.
- **O departamento explica pouco:** a taxa de saída varia só entre 12% e 19% entre áreas.

---

## 🤖 Resultados do Modelo

Validação cruzada no treino:

| Modelo | AUC | Recall (saiu) | Precisão (saiu) |
|---|---|---|---|
| KNN | 0,96 | 92% | 77% |
| SVM | 0,97 | 91% | 86% |
| **Random Forest** | **0,98** | **91%** | **98%** |

No conjunto de teste, o Random Forest identificou **91% dos colaboradores que saíram**, com **precisão de 97%** e **AUC de 0,98**. As variáveis mais importantes são satisfação, tempo de casa, número de projetos, avaliação e horas trabalhadas.

---

## 🛠️ Revisão do Projeto

Esta versão revisa a primeira publicação do repositório:

| Antes | Agora |
|---|---|
| 3.005 duplicatas mantidas: 940 dos 3.000 registros de teste eram cópias de registros do treino | Duplicatas removidas antes da análise e da divisão treino/teste |
| Número de vizinhos do KNN escolhido olhando o conjunto de teste | Hiperparâmetros escolhidos por validação cruzada no treino |
| SMOTE aplicado antes da validação cruzada (dados sintéticos vazando entre as dobras) | SMOTE dentro do pipeline, só na parte de treino de cada dobra |
| A validação cruzada apontava o Random Forest, mas o modelo final era um KNN com outros parâmetros | O modelo final é o vencedor da validação cruzada |
| Comparação só por acurácia | AUC, recall, precisão e F1 da classe "saiu" |
| Valor de 810h corrigido para 310h por suposição | Registro removido |
| Resultado do teste de hipótese não informado | Resultado informado e interpretado |

Com dados limpos, as taxas da análise exploratória mudaram, e os textos foram atualizados. A taxa de saída entre salários baixos, por exemplo, era de 29,7% com as duplicatas e é de 20,5% sem elas.

---

## 🛠️ Tecnologias Utilizadas

Python · Pandas · NumPy · Matplotlib · Seaborn · SciPy · Scikit-learn · imbalanced-learn · Jupyter Notebook

---

## ▶️ Como Executar

```
pip install -r requirements.txt
jupyter notebook hr_analytics_employee_churn.ipynb
```

---

## ⚠️ Limitações

- A base é de um único momento, sem datas. Num cenário real, o modelo deveria ser validado prevendo saídas futuras com dados do passado.
- Correlação não é causa: os padrões mostram associações, não o efeito de cada fator sobre a decisão de sair.

---

## 📬 Contato

LinkedIn: <https://linkedin.com/in/renancostaviana>
E-mail: <renan.cv@outlook.com.br>

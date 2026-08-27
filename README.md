# 🧑‍💼 HR Analytics — Employee Churn Prediction

### Prevendo saída de funcionários com Machine Learning

Este projeto aplica técnicas de **Machine Learning supervisionado** para prever a probabilidade de um funcionário deixar a empresa (churn), a partir de uma base com características como nível de satisfação, avaliação de desempenho, carga de projetos, tempo de casa, faixa salarial e departamento.

O objetivo é apoiar áreas de **Recursos Humanos** na identificação de riscos, retenção de talentos e tomada de decisão estratégica.

---

## 🚀 Objetivos do Projeto

- Explorar os dados de RH e entender os padrões relacionados ao churn
- Realizar limpeza, tratamento e engenharia de atributos
- Testar formalmente uma hipótese estatística observada na análise exploratória
- Treinar e comparar múltiplos modelos de classificação
- Lidar corretamente com o desbalanceamento de classes (a maioria dos funcionários não sai)
- Identificar os fatores que mais influenciam a saída de colaboradores

---

## 🛠️ Tecnologias Utilizadas

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- SciPy (testes estatísticos)
- Scikit-learn
- imbalanced-learn (SMOTE)
- Jupyter Notebook

---

## 🔍 Etapas do Projeto

### 1. Validação e tratamento dos dados
Verificação de valores nulos, duplicados e outliers (ex.: um valor de 810h mensais claramente incorreto, corrigido para 310h).

### 2. Análise exploratória
Investigação das relações entre as variáveis e a saída de funcionários, com interpretação escrita de cada padrão encontrado — não apenas os gráficos.

### 3. Teste de hipótese
Teste formal (Shapiro-Wilk + Mann-Whitney) sobre a relação entre faixa salarial e carga horária mensal.

### 4. Modelagem
Comparação de três algoritmos (KNN, SVM, Random Forest) via validação cruzada — feita **apenas com dados de treino**, para evitar vazamento de informação do conjunto de teste. As variáveis são padronizadas (`StandardScaler`) antes do KNN, já que é um algoritmo baseado em distância, e o desbalanceamento de classes é tratado com **SMOTE aplicado somente ao conjunto de treino**.

### 5. Avaliação
Métricas no conjunto de teste (nunca visto durante o treino): acurácia, precisão, recall, F1-score, matriz de confusão e curva ROC/AUC.

---

## 🧠 Principais Insights

- **Salário é um dos fatores mais fortes associados à saída**: a taxa de churn é de **29,7% entre salários baixos**, cai para 20,4% em salários médios e despenca para **6,6%** em salários altos. A chance de promoção segue o mesmo padrão (0,9% vs. 5,8%), sugerindo um problema de teto de carreira concentrado em quem ganha menos.
- **Departamentos com mais promoções retêm mais gente**: Management tem a maior taxa de promoção (11%) e a menor taxa de churn (14%); RH tem a menor taxa de promoção (2%) e a maior taxa de churn (29%).
- **Existem dois perfis distintos entre quem sai**: um grupo com satisfação baixa e avaliação alta (risco de burnout) e outro com satisfação e avaliação altas (provavelmente atraído por oportunidades externas) — uma nota de avaliação boa, sozinha, não indica quem vai ficar.
- **A empresa perde principalmente os funcionários mais experientes e sobrecarregados**: entre quem sai, tanto a avaliação quanto as horas trabalhadas sobem junto com o tempo de casa.

---

## ▶️ Como Executar

1. Instale as dependências:

```
pip install -r requirements.txt
```

2. Abra o notebook:

```
jupyter notebook hr_analytics_employee_churn.ipynb
```

3. Execute as células na ordem indicada.

---

## 📬 Contato

LinkedIn: <https://linkedin.com/in/renancostaviana>
E-mail: <renan.cv@outlook.com.br>

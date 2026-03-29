# 🧑‍💼 HR Analytics — Employee Churn Prediction  
### Prevendo saída de funcionários com Machine Learning

Este projeto aplica técnicas de **Machine Learning supervisionado** para prever a probabilidade de um funcionário deixar a empresa (churn).  
O objetivo é apoiar áreas de **Recursos Humanos** na identificação de riscos, retenção de talentos e tomada de decisão estratégica.

---

## 🚀 Objetivos do Projeto

- Explorar dados de RH e entender padrões relacionados ao churn  
- Realizar limpeza, tratamento e engenharia de atributos  
- Testar múltiplos modelos de classificação  
- Comparar métricas e selecionar o melhor modelo  
- Identificar fatores que mais influenciam a saída de colaboradores  
- Gerar insights acionáveis para estratégias de retenção  

---

## 🛠️ Tecnologias Utilizadas

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib  
- Seaborn  
- Jupyter Notebook  

---

## 🔍 Etapas do Projeto

### **1. Análise Exploratória (EDA)**
- Distribuição de churn  
- Relação entre salário, tempo de empresa e saída  
- Análise por departamento  
- Identificação de padrões de comportamento  
- Visualizações para facilitar interpretação  

### **2. Pré-processamento**
- Tratamento de valores ausentes  
- Codificação de variáveis categóricas  
- Normalização/Padronização  
- Feature engineering (ex.: senioridade, score de satisfação)  

### **3. Modelagem**
Modelos testados:

- Regressão Logística  
- Random Forest  
- Gradient Boosting  
- XGBoost (opcional)  
- KNN  
- SVM  

### **4. Avaliação**
- Acurácia  
- Precisão  
- Recall  
- F1-score  
- Matriz de confusão  
- Importância das variáveis  

---

## 📈 Resultados

O modelo com melhor desempenho foi:

> **Random Forest Classifier**  
> com F1-score aproximado de **XX%** e acurácia de **YY%**  
> *(substituir pelos valores reais)*

Visualizações como matriz de confusão, curva ROC e feature importance podem ser adicionadas na pasta `/images`.

---

## 🧠 Insights Relevantes

Alguns exemplos que você pode adaptar conforme sua análise:

- Funcionários com baixa satisfação apresentam probabilidade significativamente maior de churn  
- Certos departamentos possuem taxas de saída acima da média, indicando possíveis problemas de gestão  
- Salários abaixo da mediana estão fortemente associados ao risco de desligamento  
- Tempo de empresa muito curto ou muito longo pode indicar padrões distintos de churn  

Se quiser, posso escrever insights específicos com base no seu notebook.

---

## ▶️ Como Executar

1. Instale as dependências:
```bash
pip install -r requirements.txt
```
2. Abra o notebook:
```bash
jupyter notebook hr-analytics-churn.ipynb
```
3. Execute as células na ordem indicada.

##📬 Contato
LinkedIn: https://linkedin.com/in/renancostaviana  
E-mail: renan.cv@outlook.com.br

**✨ Projeto desenvolvido para demonstrar domínio em Machine Learning aplicado a Recursos Humanos.**

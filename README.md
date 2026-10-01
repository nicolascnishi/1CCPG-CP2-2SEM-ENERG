# Avaliação: APIs, Energias Renováveis e Machine Learning

Este repositório contém a resolução de duas tarefas de aprendizado de máquina utilizando dados reais extraídos de APIs públicas (ANEEL e Open-Meteo).

## 📌 Objetivos
* **Tarefa 1 (Classificação):** Prever o tipo de fonte de energia renovável (Solar, Eólica ou Hidráulica) de empreendimentos brasileiros baseando-se apenas na potência outorgada e em suas coordenadas geográficas (latitude e longitude).
* **Tarefa 2 (Regressão):** Estimar a radiação solar global horizontal (W/m²) em Petrolina (PE) com base em dados meteorológicos (temperatura, umidade, nuvens, vento e hora do dia).

## 📂 Origem dos Dados
* **Tarefa 1:** Dados extraídos da API SIGA da ANEEL, representando empreendimentos de geração no Brasil.
* **Tarefa 2:** Dados horários estimados pela API histórica Open-Meteo para a região de Petrolina (PE), de 01/04/2025 a 30/06/2025 (fuso America/Recife, das 7h às 17h).

## 🚀 Instruções de Execução
1. Clone este repositório: `git clone https://github.com/SEU_USUARIO/NOME_DO_REPO.git`
2. Instale as dependências: `pip install pandas numpy scikit-learn matplotlib seaborn`
3. Abra o Jupyter Notebook: `jupyter notebook`
4. Execute o notebook `avaliacao_ml_energias.ipynb` sequencialmente. Ele irá gerar os arquivos `aneel_classificacao_orange.csv` e `meteo_regressao_orange.csv` (através das APIs) e rodar as pipelines de Machine Learning.

## 📊 Conclusões
* **Classificação (Fonte Renovável):** Modelos baseados em árvores (como Random Forest) lidam melhor com a não-linearidade das coordenadas geográficas em comparação com regressão logística. O principal desafio é a sobreposição de localizações e o fato de que a potência isolada não discrimina perfeitamente a fonte.
* **Regressão (Radiação Solar):** A variável `hora` é o preditor mais forte devido à natureza do ciclo solar. Modelos não-lineares (como Gradient Boosting e Random Forest) capturaram perfeitamente a curva diária, resultando nos menores erros (MAE/MSE) e maiores valores de R². Vale ressaltar que estimar radiação não equivale a prever geração elétrica (que depende de fatores de hardware e eficiência dos painéis).

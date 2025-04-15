# steam-classificacao-ia
Classificação de jogos da Steam com diferentes algoritmos de ML
#Trabalho de Inteligência Artificial

#Classificação de Jogos da Steam com Algoritmos de Machine Learning

#1. Introdução

Este projeto tem como objetivo aplicar algoritmos de classificação para prever se um jogo da Steam é "Bom" ou "Ruim", com base em suas avaliações e características. A base de dados foi obtida do Kaggle:

🔗 [Steam Store Games - Kaggle](https://www.kaggle.com/datasets/nikdavis/steam-store-games)

---

#2. Base de Dados

Foram utilizadas as seguintes variáveis:

- `price`: Preço do jogo  
- `release_year`: Ano de lançamento (extraído da data de lançamento)  
- `developer`: Desenvolvedor  
- `average_playtime`: Tempo médio jogado  
- `positive_ratings`, `negative_ratings`: Usadas para calcular o "score do usuário"  

---

#3. Objetivo

Classificar os jogos em duas categorias:

- **Bom**: quando mais de 80% das avaliações dos usuários são positivas  
- **Ruim**: caso contrário

---

#4. Algoritmos Utilizados

1. Decision Tree  
2. Random Forest  
3. SVM (Support Vector Machine)  
4. Naive Bayes Gaussiano  

---

#5. Metodologia

- Pré-processamento dos dados: limpeza, conversão de datas, codificação da variável `developer`, criação da variável-alvo  
- Divisão em treino/teste (80% / 20%)  
- Avaliação com as métricas: **Acurácia**, **Precisão**, **Recall**, **F1-score**, **Matriz de Confusão**  

---

#6. Resultados

#Tabela de Comparação

| Algoritmo      | Acurácia | Precisão (Bom) | Recall (Bom) | F1-Score (Bom) |
|----------------|----------|----------------|--------------|----------------|
| Decision Tree  | 0.5907   | 0.5294         | 0.4834       | 0.5053         |
| Random Forest  | 0.6261   | 0.5796         | 0.4936       | 0.5331         |
| SVM            | 0.6040   | 0.6364         | 0.1969       | 0.3008         |
| Naive Bayes    | 0.5520   | 0.4774         | 0.3785       | 0.4223         |

#Gráfico de Acurácias

O gráfico de comparação de acurácias por algoritmo está disponível no google colab e no pdf.

---

#7. Discussão

O algoritmo com melhor desempenho geral foi o **Random Forest**, com uma acurácia de 62,61% e o melhor equilíbrio entre precisão, recall e F1-score para a classe “Bom”.

O pior desempenho foi do **Naive Bayes**, com uma acurácia de apenas 55,20%, provavelmente por suas fortes suposições sobre distribuição e independência das variáveis — o que não reflete bem os dados reais.

Embora o **SVM** tenha tido a maior precisão (63,64%) na detecção de jogos bons, seu **recall foi muito baixo** (19,69%), indicando que ele deixou de identificar muitos jogos bons.

A **Árvore de Decisão** teve desempenho intermediário, sendo útil pela sua simplicidade e interpretabilidade.

---

#8. Conclusão

Todos os modelos apresentaram desempenho razoável, com destaque para o Random Forest.

O projeto mostrou a importância do pré-processamento e da escolha do modelo. Para trabalhos futuros, seria interessante explorar mais variáveis (como gêneros e tags) e aplicar tuning de hiperparâmetros para melhorar os resultados.

---

#Execução

- O código foi desenvolvido e testado no Google Colab.  
- Para executar, basta abrir o notebook no Colab e fazer upload do arquivo `steam.csv`.

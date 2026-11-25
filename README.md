# Trabalho 2 de PLN — Classificador de veículo de imprensa (continuação do Trabalho 1)

Pergunta: dado o texto de uma matéria sobre o conflito Israel–Palestina, é possível prever o **veículo** (ou grupo de
veículos) que a publicou — mesmo com os nomes dos veículos mascarados? E quais termos compõem essa "assinatura lexical"?

**Autora:** Isabella Oliveira Marcelli

## Pipeline (segue o enunciado)
| Etapa | O que foi feito |
|---|---|
| 1 Corpus | Corpus do T1 (NewsAPI, set/2026); análise de classes; viés e limitações |
| 2 Processamento | normalização, mascaramento de nomes de veículos, tokenização, lematização e stopwords (spaCy), BoW e TF-IDF |
| 3 Modelo principal | Classificação: TF-IDF + Regressão Logística (+ agrupamento K-Means/LSA e busca TF-IDF como abordagens complementares) |
| 4 Avaliação | CV estratificada repetida, hold-out + GridSearchCV só no treino, métricas por classe (VP/FP/FN/VN), ROC-AUC/AP, matriz de confusão, análise de erros, baselines, teste de vazamento |
| Compl. framing | Tom por lado do conflito (VADER) e agência em eventos de violência (POS + dependências, com gabarito manual) |
| 5 Visualizações | 14 figuras (`resultados/figuras/`) |
| 6 Contemporâneo | Embeddings MiniLM, RAG (FLAN-T5, com × sem contexto, perguntas sem resposta) e sumarização DistilBART — só no final, comparados ao modelo tradicional |

## Como executar
**Colab (recomendado):** abra `notebooks/trabalho2_classificador_veiculos.ipynb`, rode tudo (o corpus é achado no Drive).

**Local:**
```bash
pip install -r requirements.txt
python -m spacy download en_core_web_sm
# coloque data/corpus_limpo.csv (ver data/LEIA-ME.md)
jupyter notebook notebooks/trabalho2_classificador_veiculos.ipynb
```
Sem internet/Hugging Face, a Etapa 6 é ignorada com aviso e o restante executa normalmente.

## Estrutura
```
notebooks/   trabalho2_classificador_veiculos.ipynb
data/        instruções de acesso ao corpus (LEIA-ME.md)
resultados/  figuras, metricas.json e tabelas geradas pelo notebook
docs/        relatório técnico (.docx) e slides (.pptx)
trabalho1/   notebooks do Trabalho 1 (coleta → BoW)
```

## Resultados incluídos

A pasta `resultados/` contém a execução no Colab com o corpus real do T1.

# Dados

O corpus **não** está versionado neste repositório (direitos autorais das matérias + tamanho).

## Como obter
1. Rode os notebooks do Trabalho 1 (`trabalho1/`), que coletam via NewsAPI e geram `metadados/corpus_limpo.csv`; **ou**
2. Coloque o `corpus_limpo.csv` do Trabalho 1 nesta pasta (`data/corpus_limpo.csv`); **ou**
3. No Google Colab, deixe o arquivo em qualquer pasta do seu Drive — o notebook o localiza sozinho.

## Colunas usadas
`id, grupo, veiculo, data_publicacao, url, titulo, idioma_detectado, foi_traduzido, texto_limpo`

Sem o arquivo, o notebook usa o 20 Newsgroups (sklearn) como contingência, apenas para o código rodar.

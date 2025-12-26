# Item 1 — Base de Dados (Dataset)

## 1) Fonte

- Dataset (Kaggle): **Amazon Product Reviews** — `saurav9786/amazon-product-reviews` :contentReference[oaicite:0]{index=0}
- Link: https://www.kaggle.com/datasets/saurav9786/amazon-product-reviews

> Observação: o dataset no Kaggle é derivado do repositório público de reviews da Amazon (UCSD / Julian McAuley), citado na própria documentação e materiais relacionados ao dataset. :contentReference[oaicite:1]{index=1}

---

## 2) Tamanho e Amostragem (para o case)

Para viabilizar o desenvolvimento e o upload na plataforma com menor peso de arquivo, foi gerada uma amostra do dataset original mantendo volume **acima do mínimo exigido**.

- Formato: **CSV**
- Registros (linhas): **129.174** (≥ 100.000)
- Colunas: **5**
- Período (review_date): **1998-12-04 a 2014-07-22**
- Arquivo amostrado: `amazon_reviews_150k.csv` _(nome do arquivo; volume final ~129k linhas)_

> A amostragem foi feita apenas para reduzir o tamanho do arquivo, mantendo representatividade e atendendo ao requisito de volume mínimo.

---

## 3) Granularidade do Dado

**1 linha = 1 avaliação (review) de um usuário para um produto em uma data**, associada a uma categoria.

---

## 4) Campos Principais (Dicionário rápido)

| Campo         | Tipo (esperado) | Descrição                                          |
| ------------- | --------------- | -------------------------------------------------- |
| `user_id`     | string          | Identificador do usuário que avaliou               |
| `product_id`  | string/int      | Identificador do produto avaliado                  |
| `rating`      | float (1–5)     | Nota atribuída ao produto (escala 1 a 5)           |
| `review_date` | date            | Data da avaliação                                  |
| `category`    | string          | Categoria do produto (ex.: Computers, Audio, etc.) |

Exemplo:

- `AKM1MP6P0OYPR, 0132793040, 5.0, 2013-04-13, Computers`

---

## 5) Por que essa base resolve o problema do cliente (E-commerce)

Esta base se encaixa diretamente no cenário de uma grande empresa de e-commerce que deseja uma Plataforma de Dados para **análises descritivas e prescritivas**:

### Análises Descritivas (o que aconteceu?)

- Distribuição de ratings por categoria e por produto
- Evolução temporal das avaliações (sazonalidade, tendências)
- Identificação de categorias com pior experiência do cliente (rating médio baixo)
- Detecção de produtos com alta variância de avaliações (instabilidade de qualidade)

### Análises Prescritivas (o que fazer a partir disso?)

- Base para **recomendação** e personalização (ex.: “produtos bem avaliados em categorias similares”)
- Priorização de ações (ex.: categorias/produtos que exigem melhoria, revisão de fornecedor, página de produto, logística etc.)
- Suporte a features de IA/GenAI (quando combinado com dados textuais) para:
  - análise de sentimento
  - tópicos recorrentes de reclamação/elogio
  - atributos estruturados para catálogo

Assim, o dataset permite demonstrar, ponta a ponta, o ciclo: **integrar → catalogar → garantir qualidade → modelar → analisar → gerar valor** dentro da narrativa de Plataforma de Dados.

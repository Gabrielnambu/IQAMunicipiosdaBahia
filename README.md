# 💧 Qualidade da Água em Municípios da Bahia: o Saneamento Explica a Diferença?

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.2-yellow)
![Numpy](https://img.shields.io/badge/Numpy-1.26-013243)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.8-orange)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-lightgrey)
![Status](https://img.shields.io/badge/status-concluído-brightgreen)

Análise exploratória de dados de qualidade da água coletados em 14 pontos de monitoramento, em 10 municípios do interior da Bahia, comparando localidades com e sem Sistema de Esgotamento Sanitário (SES) frente aos limites da Resolução CONAMA 357/2005.

---

## Sobre o projeto

Este repositório investiga uma pergunta simples de fazer e difícil de responder com rigor: **cidades com saneamento básico têm água de melhor qualidade do que cidades sem saneamento?**

A análise usa dados secundários publicados por Pessoa, Orrico e Lordêlo (2018) e é tratada, do início ao fim, como **exploratória** — o objetivo não é provar uma relação de causa e efeito, e sim descrever os dados com transparência, incluindo os limites do que eles permitem concluir.

## Dados

| Item | Detalhe |
|---|---|
| Unidade de análise | Ponto de monitoramento (P1–P14) |
| Período | 2008–2015 (dados já agregados por ponto) |
| Municípios | 10, divididos em `Com SES` (7 cidades / 10 pontos) e `Sem SES` (3 cidades / 4 pontos) |
| Indicadores | Coliformes termotolerantes, DBO, OD, fósforo total, IQA |
| Fonte | Pessoa, Orrico e Lordêlo (2018) — [DOI 10.1590/S1413-41522018166513](https://doi.org/10.1590/S1413-41522018166513) |
| Referência legal | Resolução CONAMA 357/2005, água doce Classe 2 |

Os arquivos de dados brutos e processados estão em [`data/`](data/) e [`outputs/`](outputs/).

## O que o notebook faz

1. Marca cada ponto como conforme ou não conforme com o CONAMA 357/2005;
2. Compara os grupos Com SES e Sem SES por meio de gráficos de barra e boxplots;
3. Relaciona o porte populacional de cada município ao IQA médio dos seus pontos;
4. Calcula o percentual de desconformidade legal por grupo e por parâmetro.

Notebook completo: [`Qualidade_Agua_Bahia_Documentacao.ipynb`](Qualidade_Agua_Bahia_Documentacao.ipynb)

## Principais achados

- Nenhum dos dois grupos está em conformidade total com a legislação; cada um se sai melhor em parâmetros diferentes;
- Os piores resultados da amostra (P9 e P10) pertencem aos dois maiores municípios do grupo Com SES;
- A correlação entre população e IQA médio por cidade é de **r = -0,74**: municípios maiores tendem a ter pior qualidade da água, independentemente do grupo.

## ⚠️ Por que este não é um estudo causal

O grupo Com SES é formado pelas cidades maiores da amostra; o grupo Sem SES, só por cidades pequenas. Como população e presença de SES variam juntas, os dados **não permitem isolar o efeito do saneamento** do efeito do porte populacional. Essa e outras limitações (dependência entre pontos de uma mesma cidade, incerteza publicada como desvio-padrão) estão detalhadas na última seção do notebook.

## Tecnologias

Python · Pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook

## Como reproduzir

```bash
pip install -r requirements.txt
jupyter notebook Qualidade_Agua_Bahia_Documentacao.ipynb
```

## Referências

- PESSOA, J.O.; ORRICO, S.R.M.; LORDÊLO, M.S. *Qualidade da água de rios em cidades do Estado da Bahia.* Engenharia Sanitária e Ambiental, v. 23, n. 4, p. 687–696, 2018.
- BRASIL. Conselho Nacional do Meio Ambiente (CONAMA). Resolução nº 357, de 17 de março de 2005.

---

Made By Gabriel Matos 

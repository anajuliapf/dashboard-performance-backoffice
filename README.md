# 🗂️ Dashboard de Performance do Backoffice

Dashboard em **Power BI** para monitorar a performance do backoffice: quantidade de documentos processados, desempenho por responsável e áreas que ainda precisam de atenção.

### 🔗 [Clique aqui para explorar o dashboard interativo no Power BI](https://app.powerbi.com/view?r=eyJrIjoiMjRlYjM3MjAtOThiZS00ODBjLWI4ZWQtMjgzNDY5NWZiOGZlIiwidCI6ImI4YWYwYWFjLTcwMjEtNDcwOS1hYjFmLWU2MzQ1ZTczNTI3OCJ9)


## 🎯 Principais indicadores

- ✔ Atividades preenchidas (Extratos, UNO, APR, Atas, Quantum, APR DAIR, DAIR Área Cliente)
- ✔ Atividades faltando (mesmas categorias)
- ✔ Tempo médio UNO
- ✔ Tempo médio DAIR
- ✔ Tempo médio Área Cliente

## ⚙️ ETL e modelagem

A informação original estava em uma planilha de datas: cada atividade de cada funcionário ocupava uma coluna, com a data de finalização (dd/mm/aaaa) em cada linha por cliente.

- **Unpivot:** todas as colunas de atividade foram transformadas em linhas.
- **Contagem:** atividade com data conta como preenchida; célula vazia é substituída por "-" e contada como faltante. Exemplo: "Extratos" tinha 422 registros preenchidos e 20 em branco.
- **DAX:** uso de `CALCULATE` para obter a diferença entre preenchidas e faltantes, com filtro por atividade. A descrição detalha quais clientes estão faltando em cada atividade e quantas atividades cada responsável tem.

### Cálculo do tempo médio (página 2)

O **extrato** do cliente é a primeira atividade e serve de referência. O tempo de cada atividade é a diferença entre a data de chegada do extrato e a data de término da atividade.

> Exemplo: extrato chega em 21/04/2024 e a atividade UNO é finalizada em 27/04/2024 → 6 dias.

Os dias são somados e é calculada a média por período (mês e ano) e por responsável.


## 💡 Insights

- **Visão geral:** atividades preenchidas, faltantes e a diferença entre elas.
- **Desempenho por categoria:** DAIR, APR DAIR, Área do Cliente e Servidor, Atas de Reunião, Quantum, APR e UNO.
- **Análise por responsável:** comparação entre colaboradores (Hugo, Pedro, Yury, Caio e Carlos) pelas colunas Preenchidos, Faltam e Diferença.
- **Tempo médio:** geral e por atividade, mostrando o desempenho individual e da equipe.
- **Por cliente:** comparação entre cidades atendidas, como Acreúna, Anhanguera e Abadia.

## ➡️ Resultados e impacto

- Métricas como "Dif. dias" e "Média" mostram quais clientes precisam de mais atenção.
- Base para investigar a alta taxa de pendências e criar ações para reduzi-la.
- Acompanhamento contínuo dos KPIs e planos de ação alinhados às metas da empresa.
- Formatação condicional que destaca visualmente atividades feitas e pendentes.

## 🧰 Ferramentas

Power BI · Power Query · DAX · Excel

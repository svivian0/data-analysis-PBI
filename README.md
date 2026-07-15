# Projeto de Análise de Dados no Power BI - SAC (Hashtag Treinamentos)

## 📌 Visão Geral
Este é o meu primeiro projeto de análise de dados utilizando o **Power BI**. O objetivo deste projeto foi aplicar os conhecimentos adquiridos no curso gratuito de Power BI da [Hashtag Treinamentos](https://youtu.be/7cUrsltJbEI?si=110qhNymlMWeN0rF), analisando uma base de dados.

![Dashboard Finalizado](./Captura%20de%20tela%202026-07-15%20144933.png)

O dashboard criado permite uma visualização clara e interativa dos principais indicadores de desempenho (KPIs), facilitando a tomada de decisão a partir de dados reais.

## 📊 Organização do Dashboard
O dashboard foi estruturado para fornecer uma análise intuitiva, indo de métricas gerais para visões mais detalhadas. A organização visual foi focada em usabilidade e clareza.

**Principais Elementos do Dashboard:**
1. **Cartões de Resumo (KPIs):** Localizados geralmente no topo, mostram os números mais importantes de forma rápida (ex: Faturamento Total, Total de Vendas, Quantidade de Chamados).
2. **Gráficos de Tendência (Linhas/Área):** Utilizados para analisar o comportamento dos dados ao longo do tempo.
3. **Gráficos de Categoria (Barras/Colunas/Rosca):** Perfeitos para comparar o desempenho entre diferentes categorias (ex: Vendas por Produto, Chamados por Motivo).
4. **Filtros e Segmentações:** Painel lateral ou superior que permite ao usuário interagir com o relatório, filtrando os dados por Ano, Mês, Região, etc.

## 🔗 Modelagem de Dados e Relacionamentos
Um dos pontos mais importantes do projeto foi garantir que as diferentes tabelas da base de dados pudessem "conversar" entre si. Para isso, utilizamos a Modelagem de Dados no Power BI, estruturando os dados de forma eficiente.

### Tabelas Utilizadas:
*   **Tabela Fato (`fOcorrencias`):** A tabela principal que registra os eventos diários de ocorrências do SAC. Contém as chaves para outras tabelas e os números que calculamos (ex: tempo de atendimento, tempo de espera).
*   **Tabelas Dimensão (`dSuporte`, `dUsuario`, `dProblema`):** Tabelas que contêm as características descritivas dos dados da tabela fato (ex: Nome do atendente, Idade do usuário, Nome do problema).

![Campos e Tabelas](./Captura%20de%20tela%202026-07-15%20145209.png)

*   **dCalendario:** Uma tabela de datas auxiliar, fundamental para garantir o funcionamento correto de filtros de tempo e funções de inteligência de tempo (Time Intelligence) no DAX.

### Como a "conversa" entre as tabelas foi criada (Relacionamentos):
Para que os filtros aplicados funcionem em todo o relatório, configuramos os **Relacionamentos** na guia de *Exibição de Modelo* do Power BI. A estrutura final do modelo ficou assim:

![Modelo de Dados](./Captura%20de%20tela%202026-07-15%20144840.png)

O processo de criação das conexões foi:

1.  **Identificação das Chaves:** Encontramos a coluna em comum entre a tabela Fato e a tabela Dimensão.
2.  **Criação do Vínculo:** Arrastamos a chave primária da tabela Dimensão (onde cada atendente aparece apenas uma vez) até a chave estrangeira correspondente na tabela Fato (onde o mesmo atendente pode registrar várias ocorrências).

![Criando Relacionamento](./Captura%20de%20tela%202026-07-15%20145039.png)

3.  **Direção do Filtro:** O fluxo do relacionamento garante que as seleções feitas nas tabelas Dimensão (ex: Escolher um Nome de Atendente) filtrem automaticamente os registros da tabela Fato para calcular os resultados corretamente.

## 🚀 Ferramentas e Tecnologias Utilizadas
*   **Power Query:** Utilizado na etapa de ETL para limpar os dados, remover colunas desnecessárias, alterar tipos de dados e preparar as tabelas antes da análise.
*   **Power BI Desktop:** Ferramenta principal para a construção do modelo e visualização.
*   **DAX (Data Analysis Expressions):** Linguagem utilizada para criar medidas calculadas

## 👨‍💻 Como Visualizar
1. Baixe o arquivo .pbix
2. Baixe a base de dados .xlsx
3. Baixe o Power BI Desktop
4. Abra o arquivo .pbix no Power BI Desktop

---
*Projeto desenvolvido durante a trilha de aprendizado da Hashtag Treinamentos.*

# Azure_Batch_end_to_end

Este projeto end-to-end foi desenvolvido para a ingestão, transformação e análise de dados utilizando serviços da plataforma Azure. O principal objetivo é extrair dados de um banco de dados SQL Server on-premise, armazená-los e processá-los em camadas distintas, garantindo governança, segurança e eficiência ao longo de todo o processo. A solução culmina na construção de um pipeline de dados robusto, automatizado e otimizado para análises avançadas.

## Arquitetura do Projeto

![image](https://github.com/user-attachments/assets/c0ef6f7b-cda0-4030-ae86-fd6b5c49a5ec)

---

## Visão Geral da Solução

O projeto é dividido em três grandes etapas, que cobrem todo o ciclo de vida dos dados:

### 1. Ingestão de Dados:
- Extração dos dados de um banco de dados SQL Server on-premise, contendo informações de clientes e vendas.
- Carregamento desses dados no **Azure Data Lake Storage (ADLS)** utilizando o **Azure Data Factory (ADF)** para orquestrar a ingestão.

### 2. Transformação de Dados:
- Processamento e limpeza dos dados no **Azure Databricks**, organizando-os em três camadas de armazenamento distintas:
  - **Camada Bronze**: Armazenamento dos dados brutos, sem nenhuma transformação.
  - **Camada Silver**: Dados pré-processados e limpos, prontos para análises mais detalhadas.
  - **Camada Gold**: Dados agregados e otimizados para consumo, preparados para relatórios e dashboards.

### 3. Carregamento e Relatórios:
- Armazenamento dos dados transformados e agregados no **Azure Synapse Analytics** para facilitar a análise e a criação de relatórios.
- Desenvolvimento de um dashboard interativo no **Power BI**, integrando-se ao Azure Synapse Analytics para visualização e análise dos dados, permitindo que os stakeholders explorem insights detalhados.

### 4. Automação:
- O pipeline foi configurado para rodar diariamente, garantindo que os dados estejam sempre atualizados para suportar decisões estratégicas e operacionais.

---

## Arquitetura Medallion (Bronze, Silver, Gold)

Este projeto implementa a arquitetura Medallion, que organiza os dados em camadas distintas para otimizar a eficiência, a governança e a qualidade dos dados:

- **Camada Bronze**: Onde os dados brutos são armazenados logo após a ingestão, sem qualquer transformação. É útil para auditoria e para reprocessamento de dados históricos.
  
- **Camada Silver**: Aqui, os dados são limpos e filtrados, corrigindo possíveis inconsistências e eliminando duplicatas. Nesta etapa, os dados já estão prontos para análises mais detalhadas.

- **Camada Gold**: A camada final onde os dados são altamente otimizados e agregados para consumo por ferramentas de BI e análises avançadas. Dados nesta camada são ideais para relatórios e insights estratégicos.

---

## Stack Tecnológico Utilizado

O projeto foi desenvolvido utilizando as seguintes ferramentas e serviços:

- **Azure Data Factory (ADF)**: Orquestração da ingestão e transformação dos dados.
- **Azure Data Lake Storage (ADLS)**: Armazenamento de dados brutos e processados.
- **Azure Databricks**: Transformação e processamento dos dados em larga escala.
- **Azure Synapse Analytics**: Armazenamento e análise de dados utilizando SQL para análise de grandes volumes de dados.
- **Power BI**: Visualização de dados e desenvolvimento de dashboards interativos.
- **Azure Key Vault**: Gestão segura de credenciais e segredos utilizados nos pipelines e na infraestrutura.
- **SQL Server (On-Premises)**: Fonte original de dados de clientes e vendas.

---

Dessa forma, o projeto abrange todo o ciclo de vida dos dados, desde a ingestão até a visualização, utilizando as melhores práticas de governança, automação e segurança na nuvem Azure.

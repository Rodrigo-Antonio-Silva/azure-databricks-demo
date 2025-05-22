# 🚗 Análise de Dados com Azure Databricks: Versionamento e SQL com Spark

Este projeto demonstra como utilizar o **Azure Databricks** para análise exploratória de dados, com foco no uso de **SQL com Spark**, versionamento interno da plataforma e organização de notebooks em um ambiente de dados.

O dataset utilizado foi o **`cars_dataset_2_csv`**, carregado como tabela no metastore padrão do Databricks.

---

## 🎯 Objetivos do Projeto

- Executar análise exploratória de dados com SQL no Databricks
- Utilizar versionamento nativo do Databricks para controle de alterações
- Praticar boas práticas de organização de notebooks em ambiente de análise de dados

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

- Microsoft Azure
- Azure Databricks
- Spark SQL
- Hive Metastore (tabela `cars_dataset_2_csv`)
- Linguagem: SQL

---

## 🧪 Etapas do Projeto

### 1. Criação do Workspace e Cluster

- Criado ambiente no Azure Databricks
- Configuração de um cluster com recursos padrão e DBR atualizado

### 2. Importação do Dataset

- Dataset: `cardataset.csv`
- Carregado na interface do Databricks como tabela chamada:


### 3. Criação e Execução de Notebooks

- Criação do notebook `Análise_SQL_Carros`
- Utilização de comandos `%sql` para consultas diretas no Spark SQL
- Organização em células separadas por contexto de análise

### 4. Versionamento Interno do Databricks

- Utilização do histórico de revisões do próprio Databricks
- Acesso por: `Notebook > Revision History`
- Permite restaurar versões anteriores e acompanhar modificações

## Prints do Projeto

![print_Tabela]()

![print_Análise descritiva]()

![print_History version]()

![print_Análise descritiva]()
---

## 📊 Consultas SQL Utilizadas

```sql
-- Consulta completa da tabela
%sql
SELECT * FROM `hive_metastore`.`default`.`cars_dataset_2_csv`;

-- Filtro por tipo de combustível e ordenação por preço
%sql
SELECT * FROM `hive_metastore`.`default`.`cars_dataset_2_csv`
WHERE fuelType = 'Petrol'
ORDER BY price DESC;

-- Agrupamento por marca e tipo de combustível
%sql
SELECT Make, fuelType, COUNT(*) as Qtd 
FROM `hive_metastore`.`default`.`cars_dataset_2_csv`
GROUP BY Make, fuelType
ORDER BY Make, Qtd;
```
```
📁 Workspace
 ├── 📄 Análise_SQL_Carros
 ├── 📁 Tabelas
 │    └── cars_dataset_2_csv
```

## 💡 Aprendizados
Familiarização com o ambiente de notebooks do Azure Databricks

Importação e registro de arquivos .csv como tabelas no metastore

Execução de comandos SQL via notebooks, sem necessidade de scripts Python


Organização e versionamento interno de notebooks no próprio Databricks
````
✅ Status do Projeto
✅ Projeto concluído com sucesso.
🚫 Sem uso de integração externa com Azure DevOps devido a limitações de conta.
````

## 🧾 Conclusão
Este hands-on demonstrou que mesmo com recursos limitados é possível realizar análises poderosas no Azure Databricks. A simplicidade do uso de SQL em notebooks acelera a exploração dos dados, tornando a plataforma acessível a analistas e engenheiros. O projeto serviu como base sólida para aprofundar o uso do Databricks em futuras iniciativas de engenharia de dados.

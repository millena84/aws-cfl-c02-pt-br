# Amazon EMR![Ícone Amazon EMR](https://icon.icepanel.io/AWS/svg/Analytics/EMR.svg)
 
## Funcionalidade  
**Solução big data** para trabalhar com processamento de dados, análise interativa e machine learning que usa estruturas de código aberto, como [Apache Spark](https://aws.amazon.com/pt/emr/features/spark/), [Apache Hive](https://aws.amazon.com/pt/emr/features/hive/) e [Presto](https://aws.amazon.com/pt/emr/features/presto/).


## Opções e Entendimento  
Permite escalar a análise de dados de grandes volumes.

### Tipos de armazenamento
-   **Hadoop Distributed File System (HDFS)**: É um sistema de arquivos distribuído e escalável para o Hadoop. O HDFS distribui os dados armazenados entre as instâncias do cluster, armazenando várias cópias dos dados em instâncias diferentes para garantir que nenhum dos dados se perca caso uma das instâncias falhe.
    
-   **Sistema de arquivos do EMR (EMRFS)**: Estende o Hadoop para adicionar a capacidade de acessar diretamente os dados armazenados no Amazon S3 como se fosse um sistema de arquivos como o HDFS.
    
-   **Sistema de arquivos local**: Disco conectado localmente. Quando você cria um cluster Hadoop, cada nó é criado a partir de uma instância do Amazon EC2 que vem com um bloco pré-configurado de armazenamento em disco pré-conectado chamado armazenamento de instâncias.


## Possíveis integrações com outros serviços  
-   EC2
-   EKS
-   OutPosts
-   Fargate*


## Caso de uso  
-   Big data


## Cobrança  
-   Por tipo de instância por hora
    -   EC2 (instância)
    -   EKS (cluster kubernetes*)
    -   Outposts (toda estrutura da AWS no datacenter on-premises)
    -   Serverless


## Fontes de consulta
- [ ] https://aws.amazon.com/pt/emr/
- [ ] https://aws.amazon.com/pt/emr/features/
- [ ] https://aws.amazon.com/pt/emr/pricing/
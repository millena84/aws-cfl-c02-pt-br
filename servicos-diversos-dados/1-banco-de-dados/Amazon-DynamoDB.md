# Amazon DynamoDB![Ícone Amazon DynamoDB](https://icon.icepanel.io/AWS/svg/Database/DynamoDB.svg)
 
## Funcionalidade  
Banco da AWS NoSQL totalmente gerenciado pela AWS de **estrutura chave-valor**, serverless com alto desempenho em qualquer escala.


## Opções e Entendimento  
-   Backup e recuperação sob demanda
-   Possível definir a vida útil de um dado (Time To Live)
-   pode processar mais de 10 trilhões de solicitações por dia e comportar picos de mais de 20 milhões de solicitações por segundo

### Funcionalidades especiais

-   **DAX – DynamoDB Accelerato**r: Uso de cache de memória – gerenciado e altamente disponível
-   **AWS Schema Conversion Tool:**  converte seu esquema existente de banco de dados de um mecanismo de banco de dados para outro.


## Possíveis integrações com outros serviços  
-   CloudWatch
-   AWS Database Migration Service
-   AWS IQ (permite que os clientes encontrem, colaborem com segurança e paguem especialistas terceirizados certificados pela AWS para trabalhos sob demanda em um projeto.)


## Caso de uso  
-   Qualquer solução que necessite de um banco de dados extremamente escalável


## Cobrança  
-   Pagamento conforme o uso (sob demanda) ou capacidade provisionada
-   Itens que entram na cobrança:
    -   Unidade de solicitação de gravação
    -   Unidade de solicitação de leitura
    -   Armazenamento de dados
    -   Backup e restauração
    -   Tabelas globais
    -   Exportação para o S3
    -   DynamoDB Accelerator
    -   DynamoDB Streams
    -   Trasnferência de dados


## Fontes de consulta
- [ ] https://aws.amazon.com/pt/dynamodb/
- [ ] https://docs.aws.amazon.com/pt_br/amazondynamodb/latest/developerguide/Introduction.html
- [ ] https://aws.amazon.com/pt/dynamodb/resources/
- [ ] https://d1.awsstatic.com/whitepapers/AWS_Comparing_the_Use_of_DynamoDB_and_HBase_for_NoSQL.pdf?dbd_how3
- [ ] https://d0.awsstatic.com/whitepapers/migration-best-practices-rdbms-to-dynamodb.pdf
- [ ] https://aws.amazon.com/pt/dms/
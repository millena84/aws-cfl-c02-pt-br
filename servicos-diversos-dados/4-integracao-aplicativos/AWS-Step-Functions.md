# Amazon Step Functions![Ícone Amazon Step Functions](https://icon.icepanel.io/AWS/svg/App-Integration/Step-Functions.svg)
 
## Funcionalidade  
Serviço de fluxo de trabalho visual que ajuda os desenvolvedores a usar os produtos da AWS para desenvolver aplicações distribuídas, automatizar processos, **orquestrar microsserviços e criar pipelines de dados e machine learning (ML)**.


## Opções e Entendimento  
-   É serverless
-   Usa a chamada  [Amazon States Language](https://docs.aws.amazon.com/step-functions/latest/dg/concepts-amazon-states-language.html), uma linguagem baseada em JSON para configurar as chamadas maquinas de estado (que são a lista de etapas orientadas a evento)
    -   Cada etapa do fluxo é chamada estado
    -   Um estado “task” é uma unidade de trabalho que pode ser executada por outro serviço da AWS.
-   Configuração de fluxo de trabalho visual e fácil de usar
-   Tratamento de erros integrado, tempos limite e fluxo de processamento paralelo para aplicativos distribuídos
-   O serviço funciona com as chamadas transições de estado. Uma transição de estado ocorre cada vez que uma etapa do fluxo de trabalho definido é executada.
-   Tem dois tipos de fluxo, que diferem basicamente nas questões duração máxima, taxa de transição, quantidade de estados de máquina, preços, tamanho do histórico de execução
    -   Standart Workflows
    -   Express Workflows (mais rápido, mais completo e mais caro também)


## Possíveis integrações com outros serviços  
-   Fargate
-   Lambda
-   Compute services (AWS Lambda, Amazon ECS, Amazon EKS, and AWS Fargate)
-   Database services (Amazon DynamoDB)Messaging services (Amazon SNS and Amazon SQS),
-   data processing Analytics services (Amazon Athena, AWS Batch, AWS Glue, Amazon EMR, and AWS Glue DataBrew)
-   Machine learning services (Amazon SageMaker)
-   APIs created by Amazon API Gateway


## Caso de uso  
-   Automatize os processos de extração, transformação e carregamento (ETL)
-   Orquestração de microsserviços


## Cobrança  
-   Por volume de transferência


## Fontes de consulta
Algumas perguntas relacionadas foram feitas para o GPT-3.5. e suas respostas usadas de guia para montar o texto juntamente com a consulta aos links abaixo:
- [ ] https://aws.amazon.com/pt/step-functions/
- [ ] https://aws.amazon.com/pt/step-functions/features/
- [ ] https://aws.amazon.com/pt/step-functions/use-cases/
- [ ] https://aws.amazon.com/pt/step-functions/getting-started/
- [ ] https://aws.amazon.com/pt/step-functions/pricing/
- [ ] https://docs.aws.amazon.com/step-functions/latest/dg/limits-overview.html#service-limits-api-action-throttling-general
- [ ] https://docs.aws.amazon.com/step-functions/latest/dg/concepts-standard-vs-express.html
- [ ] https://docs.aws.amazon.com/step-functions/latest/dg/concepts-amazon-states-language.html
- [ ] https://docs.aws.amazon.com/step-functions/latest/dg/tutorial-creating-lambda-state-machine.html
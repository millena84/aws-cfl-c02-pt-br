# AWS Batch ![Ícone AWS Batch](https://icon.icepanel.io/AWS/svg/Compute/Batch.svg)

## Funcionalidade
Execução de cargas de trabalho/tarefas em lote. 

- Não necessita de integração com software de gerenciamento de computação em lote (ele mesmo faz). 
- É escalável.
- Faz o provisionamento dinâmico, baseado nos volumes e recursos necessários para as tarefas definidas e enviadas a ele.
- Possui um painel para monitoramento das filas de trabalho.

## ~~Opções e~~ entendimento
### Componentes envolvidos:

- **JOB / Tarefa:**  shell, executável, imagem Docker, qualquer coisa que seja de execução em lote;
- **Definições de tarefa:**  Parametrizações como: Quem pode executar a tarefa, Como ela deve ser executada, Qual a capacidade necessária, Quando deve ser executada, etc;
- **Filas de trabalho:**  o “schedule” - agendamento da tarefa;
- **Ambiente:**  EC2 ou Fargate (podendo ou não ser configurado e gerenciado pelo contratante);
	- Um ambiente é a infraestrutura onde o job vai executar:
		- Capacidade min/max e tipos de instância
		- Dois tipos
			- Managed Compute Environment: Gerenciado pela AWS - provisiona e escala automaticamente instâncias EC2 sob demanda ou Spot.
			- Unmanaged Compute Environment: Gerenciado pelo contratante (inclusive na questão suporte instâncias EC2)

> **IMPORTANTE:** Ele deve ser usado apenas para trabalhos nos quais não se precise de interação humana (Neste outro caso, usar o  _Amazon Simple Workflow Service_)

### Exemplo de Configuração
1.  **Criando um Compute Environment**:
    -   No console do AWS Batch, você cria um novo compute environment e seleciona se deseja que seja gerenciado ou não.
    -   Defina os parâmetros, como tipo de instância, capacidade mínima e máxima, e preferência por instâncias Spot ou On-Demand.
2.  **Criando uma Job Queue**:
    -   Crie uma fila de jobs onde os trabalhos em lote aguardam para serem executados.
    -   A fila é associada ao compute environment, e o AWS Batch encaminha os jobs para os recursos disponíveis.
3.  **Enviando Jobs**:
    -   Defina job definitions, que incluem as especificações dos parâmetros necessários para executar os jobs.
    -   Envie os jobs para a job queue, e o AWS Batch cuidará do provisionamento dos recursos e da execução dos jobs.

## Possíveis integrações com outros serviços
- EC2: execuções provisionadas
- Fargate: execuções de contêineres
- Lambda: pode gatilhar ou ser gatilhado por um trabalho
- S3: armazenamento de dados de entrada e saída de tarefas
- Cloudwatch: monitoramento e logs)
- SQS: gerenciar fila de mensagens que controlam o fluxo de jobs
- SNS: publicar o status dos jobs

## Caso de uso 
- Processamento de grandes volumes de dados
- Treinamento de modelos de ML
- Simulações científicas


## Cobrança
Não existe cobrança adicional pelo gerenciamento do AWS Batch. A cobrança ocorre nos serviços envolvidos:

-   EC2
-   Fargate
-   Lambda (se houver)
-   Etc…

## Fontes de consulta
Algumas perguntas relacionadas foram feitas para o GPT-3.5. e suas respostas usadas de guia para montar o texto juntamente com a consulta aos links abaixo: 
 - [ ]  [https://docs.aws.amazon.com/pt_br/batch/latest/userguide/what-is-batch.html](https://docs.aws.amazon.com/pt_br/batch/latest/userguide/what-is-batch.html)
 - [ ]  [https://aws.amazon.com/pt/batch/faqs/](https://aws.amazon.com/pt/batch/faqs/)
 - [ ]  [https://aws.amazon.com/pt/batch/](https://aws.amazon.com/pt/batch/)
 - [ ]  [https://docs.aws.amazon.com/pt_br/whitepapers/latest/architecting-hipaa-security-and-compliance-on-aws/aws-batch.html](https://docs.aws.amazon.com/pt_br/whitepapers/latest/architecting-hipaa-security-and-compliance-on-aws/aws-batch.html)
 - [ ]  [https://docs.aws.amazon.com/pt_br/batch/latest/userguide/batch_user.pdf](https://docs.aws.amazon.com/pt_br/batch/latest/userguide/batch_user.pdf)

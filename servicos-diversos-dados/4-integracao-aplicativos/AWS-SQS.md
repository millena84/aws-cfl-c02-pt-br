# Amazon SQS (Simple Queue Service)![Ícone AWS SQS](https://icon.icepanel.io/AWS/svg/App-Integration/Simple-Queue-Service.svg)
 
## Funcionalidade  
**Serviço de filas** de mensagens gerenciado que permite o desacoplamento e a escalabilidade de microsserviços, sistemas distribuídos e aplicações sem servidor.
Permite que você envie, armazene e receba mensagens entre componentes de software em qualquer volume, sem perder mensagens ou precisar que outros serviços estejam disponíveis.

## Opções e Entendimento  
### Tipos de fila

-   **Fila padrão**
    -   **Taxa de transferência ilimitada**: as filas padrão comportam um número quase ilimitado de transações por segundo (TPS) por ação de API.
    -   **Entrega pelo menos uma vez**: uma mensagem é entregue pelo menos uma vez, mas, às vezes, mais de uma cópia da mensagem é entregue.
    -   **Melhor ordenação possível**: às vezes, as mensagens podem ser entregues em uma ordem diferente da qual elas foram enviadas.
-   **Fila FIFO**
    -   **Alta taxa de transferência**: por padrão, as filas do tipo FIFO comportam até 300 mensagens por segundo (300 operações de envio, recebimento ou exclusão por segundo). Ao agrupar em lote 10 mensagens por operação (no máximo), as filas FIFO podem dar suporte a até 3.000 mensagens por segundo. Para solicitar um aumento de limite, [envie uma solicitação de suporte](https://console.aws.amazon.com/support/v1?#/case/create).
    -   **Processamento exatamente uma vez**: uma mensagem é entregue uma vez e permanece disponível até que um consumidor a processe e exclua. Duplicatas não são inseridas na fila.
    -   **Entrega FIFO**: a ordem em que as mensagens são enviadas e recebidas é preservada com rigor (ou seja a primeira a entrar será a primeira a sair).


## Possíveis integrações com outros serviços  
-   SNS
-   Redshift
-   DynamoDB
-   EC2
-   ECS


## Caso de uso  
-   Desacoplamento de comunicação entre microserviços

> Como escolho entre o SNS e SQS?

O *AWS SQS* é um serviço de **fila**, então o tipo de comunicação é diferente. Isso significa que seu funcionamento (e seus casos de uso consequentemente) é também diferente do *SNS*, pois no caso da **fila**, quem define quem serão os consumidores é o desenvolvedor, enquanto que no modelo **pub/sub**, qualquer interessado pode se inscrever no tópico.


## Cobrança  
-   Quantidade de solicitações por mês
-   Transferência de dados


## Fontes de consulta
Algumas perguntas relacionadas foram feitas para o GPT-3.5. e suas respostas usadas de guia para montar o texto juntamente com a consulta aos links abaixo:
- [ ] https://aws.amazon.com/pt/sqs/
- [ ] https://aws.amazon.com/pt/sqs/getting-started/
- [ ] https://aws.amazon.com/pt/sqs/faqs/
- [ ] https://aws.amazon.com/pt/sqs/details/
- [ ] https://aws.amazon.com/pt/sqs/pricing/

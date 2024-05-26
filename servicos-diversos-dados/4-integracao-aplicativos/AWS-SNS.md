
# Amazon SNS (Simple Notification Service)![Ícone AWS SNS](https://icon.icepanel.io/AWS/svg/App-Integration/Simple-Notification-Service.svg)
 
## Funcionalidade  
Serviço de **pub/sub** de mensagens (SMS, push e e-mail) totalmente gerenciado pela AWS.
Ele permite que você envie notificações para diversos destinatários usando, se necessário, diferentes protocolos de entrega:
1.  **HTTP/HTTPS:** Voltado para comunicação entre aplicações como, notificações para APIs, integrações com webhooks e envio de dados para servidores web.
2.  **Email/Email-JSON:** Voltado para eventos relacionados a uma aplicação como, alertas para administradores, notificações para usuários finais e comunicações internas.
3.  **SMS (Short Message Service):** Voltado para comunicações urgentes relacionadas a uma aplicação como, notificações urgentes, alertas de segurança e atualizações em tempo real para usuários móveis.
4.  **Push Notifications (Aplicativos Móveis):** Através de serviços de push como Amazon Device Messaging (ADM), Apple Push Notification Service (APNs), Google Firebase Cloud Messaging (FCM), e Microsoft Push Notification Service (MPNS). Voltado para comunicações relacionadas à aplicação e voltadas para o usuário final. Pode ser usado para notificações para aplicativos móveis, atualizações de estado de aplicativos, mensagens para engajamento de usuários.
5.  **AWS Lambda:** Voltado para comunicação entre aplicações. Invoca funções Lambda em resposta a mensagens publicadas no tópico SNS. Lambda é um serviço de computação sem servidor que permite executar código em resposta a eventos. Pode ser usado para processamento de dados em tempo real, execução de lógicas de negócios, automação de tarefas.
6.  **Amazon SQS (Simple Queue Service):** Voltado para comunicação entre aplicações. Envia mensagens para filas SQS, permitindo o desacoplamento de componentes de software. Pode ser usado para orquestração de fluxos de trabalho, processamento assíncrono de mensagens, buffering de mensagens para processamento em lote.

### Benefícios
-   **Modernizar e desacoplar suas aplicações**: permite modernizar suas aplicações e desacoplá-las em componentes menores e independentes que são mais fáceis de desenvolver, implantar e manter.
-   **Enviar mensagens diretamente para milhões de usuários**: permite que você envie mensagens ou notificações diretamente para usuários com mensagens de texto SMS para mais de 200 países, push em plataformas Apple e Android e outras plataformas ou e-mail (SMTP).
-   **Entregar mensagens com confiabilidade**: usar o artifício da comunicação assíncrona para garantir que suas mensagens serão entregue em algum momento
-   **Dimensionar automaticamente sua carga de trabalho**: aproveita a Nuvem AWS comprovada para se escalar dinamicamente de acordo com seu aplicativo. O Amazon SNS é um serviço totalmente gerenciado, que cuida da carga pesada relacionada ao planejamento de capacidade, provisionamento, monitoramento e correções.
-   **Garantir a precisão com ordenamento de mensagens e eliminação de duplicação**:  os tópicos FIFO do Amazon SNS funcionam com as filas FIFO do Amazon SQS para garantir que as mensagens sejam entregues de maneira estritamente ordenadas e sejam processadas somente uma vez (eliminação de duplicação).
-   **Simplificar sua arquitetura com a filtragem de mensagens**: ajuda você a simplificar sua arquitetura de envio de mensagens de publicação/assinatura ao descarregar a lógica de filtragem de mensagens de seus sistemas assinantes e transmitir a lógica de mensagens de seus sistemas de publicação.


## Opções e Entendimento  
### Recordar é viver: pub/sub
Modelo de comunicação pub/sub é voltado para comunicação assíncrona entre sistemas.

![Imagem exemplo: pub/sub](https://d1.awsstatic.com/product-marketing/Messaging/sns_img_topic.e024462ec88e79ed63d690a2eed6e050e33fb36f.png)

#### Componentes essenciais:
1.  **Publicadores (Publishers):** São, literalmente, os produtores das informações, as fontes das mensagens. Eles produzem e enviam mensagens a um tópico específico sem se preocupar com quem irá recebê-las.
2.  **Tópicos (Topics):** São os "assuntos" de interesse. Eles são a ponte entre publicadores e assinantes. Um tópico é um canal de comunicação onde as mensagens são publicadas pelos publicadores. OBS:. podem ter múltiplos assinantes.
3.  **Assinantes (Subscribers):** São os interessados na informação do tópico, os destinatários das mensagens. Eles se inscrevem em um tópico para receber todas as mensagens publicadas nele.

### Tipos de pub/sub do SNS:
-   **pub/sub de A2A (aplicação para aplicação):** fornece tópicos para sistemas de mensagens de alta taxa de transferência baseados em push e de muitos para muitos entre sistemas distribuídos, microsserviços e aplicativos sem servidor orientados por eventos
-   **pub/sub de A2P (aplicação para pessoa):** permite enviar mensagens para usuários em grande escala por  **SMS, push de dispositivos móveis e e-mail**.

### Tipos de tópicos
-   **Standard Topics**: 
    -   Podem ser usados em muitos cenários, desde que seu aplicativo possa processar mensagens que chegam mais de uma vez e fora de ordem, por exemplo: distribuição de mensagens para codificação de mídia.
    -   Suportam um número quase ilimitado de mensagens por segundo.
    -   Ocasionalmente, as mensagens podem ser entregues em uma ordem diferente da que foram publicadas.
-   **FIFO Topics**: 
    -   Aprimorar mensagens entre aplicativos quando a ordem das operações e eventos é crítica ou quando duplicatas não podem ser toleradas, por exemplo: distribuição de mensagens para registro de transações bancárias.
    -   Suportam até 300 mensagens por segundo ou 10 MB por segundo por tópico FIFO (o que ocorrer primeiro).
    -   A ordem em que as mensagens são publicadas e entregues é estritamente preservada (ou seja, primeiro a entrar, primeiro a sair).

### Como funciona ![Não importante para essa certificação](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgKT8_cCbE2oCdZZ7LS3yEtqwGWZwAU54uL2E8n3b6aSLljHcRBgb3OruIdKZ3aHriZeNTtIxQnfHKgoawGJdZI1yquZrnjlaSeRG7rTxs6MtE2xb5G7KfG66QE28ai2ZOG4EvirUJ7Zx_ktVeoXxawMJeWgq8dvU5aZLzeANEsiMKNKg/s1600/ALERTA-NAO-IMPO-PARA-CFLC02.png  =70x80)

-   Os editores se comunicam de maneira assíncrona com os assinantes produzindo e enviando mensagens para um tópico, que é um canal de comunicação e um ponto de acesso lógico.
-   **Pub/Sub**
    -   A aplicação publica mensagens
    -   Envia para o SNS
    -   O SNS separa a mensagem por tópico
        -   Se o endpoint está indisponível, as mensagens são entregues para uma fila “dead-letter” para análise ou reprocessamento
    -   As mensagens são filtradas e distribuídas para os assinantes
    -   Que podem ser
        -   AWS Lambda
        -   Amazon SQS
        -   Aplicação HTTP
        -   E-mail
-   **SMS**
    -   Amazon SNS publica mensagens de texto num tópico
    -   O tópico SNS distribui para os destinatários
-   **Push**
    -   Amazon SNS cria uma aplicação para uma plataforma (Android, IOS ou Microsoft)
    -   Adiciona os endpoints
    -   Publica as mensagens no tópico
    -   O tópico SNS distribui para os destinatários

## Possíveis integrações com outros serviços  
1. **AWS Lambda:**: Permite a execução de funções serverless em resposta a mensagens publicadas em um tópico SNS. 
2.  **Amazon SQS:** Permite que mensagens sejam enviadas para filas SQS, facilitando o desacoplamento de sistemas e o processamento assíncrono de mensagens.
3. **AWS Step Functions:** Permite orquestrar fluxos de trabalho serverless ao acionar Step Functions com mensagens do SNS.
4. **Amazon Simple Email Service (SES):**  Embora o SES e o SNS sejam ambos serviços de e-mail, eles podem ser usados em conjunto. Por exemplo, o SNS pode enviar notificações para endereços de e-mail configurados no SES.
5. **AWS IAM:** Gerenciamento das permissões de tópicos.


## Caso de uso  
1.  **Notificações de Alertas e Monitoramento:** 
    -   Enviar alertas em tempo real sobre falhas de sistema, alta utilização de recursos, ou outros eventos críticos para administradores ou equipes de operações.
    -   Fazer o Monitoramento de Infraestrutura através de uma integração com o Amazon CloudWatch para enviar notificações sobre métricas e alarmes.
2.  **Notificações para Usuários:**
	-  Atualizações de status de suas transações, pedidos, ou outras atividades importantes
3.  **Automação e Orquestração:**
	-   Automatizar fluxos de trabalho integrando com o AWS Step Functions: para orquestrar fluxos de trabalho complexos, onde a publicação de mensagens SNS pode desencadear etapas subsequentes.
    -   Notificação de equipes de desenvolvimento sobre o status das builds, deploys, ou testes automatizados em pipelines de CI/CD.
4.  **Serviços de Suporte e Atendimento ao Cliente:**
	-   Informar clientes sobre atualizações de tickets de suporte, respostas a consultas, ou outros eventos relevantes através de e-mail ou SMS.
5.  **Marketing e Engajamento de Usuários:**
	-  Enviar notificações de marketing, promoções ou newsletters para uma lista de clientes via e-mail ou SMS.
    -  Notificar membros de programas de fidelidade sobre pontos acumulados, recompensas, ou ofertas especiais.

> Como escolho entre o SNS e SQS?

O *AWS SQS* é um serviço de **fila**, então o tipo de comunicação é diferente. Isso significa que seu funcionamento (e seus casos de uso consequentemente) é também diferente do *SNS*, pois no caso da **fila**, quem define quem serão os consumidores é o desenvolvedor, enquanto que no modelo **pub/sub**, qualquer interessado pode se inscrever no tópico.


## Cobrança  
-   Por tipo de tópico
-   Por solicitações de API
-   Por entrega de notificações


## Fontes de consulta
Algumas perguntas relacionadas foram feitas para o GPT-3.5. e suas respostas usadas de guia para montar o texto juntamente com a consulta aos links abaixo:
- [ ] https://aws.amazon.com/pt/sns/
- [ ] https://aws.amazon.com/pt/sns/features/
- [ ] https://aws.amazon.com/pt/sns/getting-started/
- [ ] https://aws.amazon.com/pt/sns/resources/
- [ ] https://aws.amazon.com/pt/sns/pricing/

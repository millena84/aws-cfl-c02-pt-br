# Amazon SES (Simple Email Service)![Ícone AWS SES](https://icon.icepanel.io/AWS/svg/Business-Applications/Simple-Email-Service.svg)
 
## Funcionalidade  
**Serviço de e-mail** que permite que você alcance os clientes com confiança, sem um sistema de SMTP (Simple Mail Transfer Protocol) on-premises.


## Opções e Entendimento  
-   É possível configurar rapidamente a compatibilidade do Amazon SES com vários casos de uso de e-mails, como comunicações transacionais, de marketing ou de e-mails em massa.


## Possíveis integrações com outros serviços  
-   EC2
-   S3
-   Redshift
-   Lambda


## Caso de uso  
-   E-mail marketing
-   Comunicações em massa

> Como escolho entre o SNS e SES?

O *AWS SES* é um serviço de apenas de **e-mail** com objetivo diferente do *AWS SQS*. 
-   *SQS*: ideal para mensagens curtas e notificações mais direcionadas
-   *SES*: ideal para e-mails **transacionais** e em massa. Transacionais no sentido de estarem relacionados a uma transação. Pode também ser usado como newsletter, campanhas de marketing e atualizações de produtos/ofertas para o usuário **final**


## Cobrança  
-   Por quantidade de e-mails
    -   Enviados
    -   Enviados EC2
    -   Recebidos
-   Por volume de GBs anexados


## Fontes de consulta
Algumas perguntas relacionadas foram feitas para o GPT-3.5. e suas respostas usadas de guia para montar o texto juntamente com a consulta aos links abaixo:
- [ ] https://aws.amazon.com/pt/ses/
- [ ] https://aws.amazon.com/pt/ses/details/
- [ ] https://aws.amazon.com/pt/ses/developer-resources/
- [ ] https://aws.amazon.com/pt/ses/getting-started/
- [ ] https://aws.amazon.com/pt/ses/pricing/
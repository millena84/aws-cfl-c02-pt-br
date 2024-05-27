### _Paralelo entre: AWS Amplify x AWS Elastic Bealstalk_

> Por que fazer um paralelo entre os dois serviços

Porque eles têm fins semelhantes (mas o Bealstalk é mais completo), porém um é voltado para front E back-end, e o outro, para front-end
 
-   **Amplify**: auxilia no desenvolvimento de aplicações web e móveis (front-end), simplificando o deploy, o gerenciamento e a integração com o back-end.
-   **Elastic Beanstalk**: auxilia no desenvolvimento de aplicações completas (front e back-end) e gerencia servidores de aplicação, bancos de dados, rede e tráfego.

> o AWS Amplify é equivalente a um AWS Elastic Beanstalk simplificado, porém voltado somente para front-end.

#### Uso Ideal
-   **Amplify**: projetos especializados em front-end.
-   **Elastic Beanstalk**: aplicações completas e complexas.

#### Encaixe em uma esteira de desenvolvimento

> Em que ponto de uma esteira de desenvolvimento poderiam ser encaixados ambos os serviços?

**Amplify:**
-   Desenvolvimento inicial
-   Integração contínua: no testes automatizados
-   Entrega contínua: no build e deploy do front automatizado
-   Pós-implantação (gerenciamento em produção): no monitoramento e escalabilidade

**Elastic Beanstalk:**
Pode aparecer em quase toda esteira de desenvolvimento através da integração com as ferramentas especializadas
-   Configuração inicial: Facilita a configuração inicial de infra
-   Desenvolvimento: Suporta linguagens de programação mais comuns
-   Controle de versão: Pode ser configurado para pegar o código automaticamente de repositórios como Github ou CodeCommit
-   Integração contínua: Pode ser integrado com Jenkins ou ColdeBuild para testes automatizados a cada mudança de código
-   Entrega contínua: Automatiza o build e o deploy da aplicação, fazendo o gerenciamento dos servidores, bancos de dados, balanceamento de carga e redes

## Fontes
***Esse conteúdo foi criado através das respostas de várias perguntas para a Luri (a IA generativa da Alura) e para o chat-GPT (GPT-3.5). Todas elas foram checadas na documentação da AWS, interpretadas e refinadas antes de vir para este doc.***

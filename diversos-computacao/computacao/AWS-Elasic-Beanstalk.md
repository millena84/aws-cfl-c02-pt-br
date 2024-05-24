# AWS Elastic Beanstalk ![Ícone AWS Beanstalk Family](https://icon.icepanel.io/AWS/svg/Compute/Elastic-Beanstalk.svg)
 
## Funcionalidade  

Serviço totalmente gerenciado que permite implantar e gerenciar rapidamente aplicações na nuvem AWS sem se preocupar com a infraestrutura que as executa.  
  
Os desenvolvedores carregam seus aplicativos e o serviço administra os detalhes da implantação, provisionamento da capacidade, balanceamento de carga, do Auto Scaling e do monitoramento da integridade do aplicativo.   

Ele oferece uma maneira diferente e simplificada de executar e gerenciar aplicativos na nuvem em comparação com a configuração manual e o gerenciamento direto dos recursos de infraestrutura.

Ele tem sua própria linha de comando (a EB CLI).
  
## Opções e Entendimento  

Reduz a complexidade de gerenciamento sem restringir as escolhas nem o controle  
O código pode ser implantado pelo console da AWS, linha de comando do Elastic Beanstalk, Visual Studio e Eclipse.  
Tem algumas políticas de implantação para garantir a integridade: 
- **todas de uma vez (All at once)**: Faz o upload e atualiza todas as instâncias simultaneamente. É a política mais rápida, mas pode causar interrupções no serviço.  
- **agregadas (rolling)**: Faz o upload e atualiza um subconjunto de instâncias por vez. Reduz a interrupção do serviço, mas leva mais tempo.  
- **agregadas com um lote adicional (rolling with additional batch)**: Faz o upload e atualiza um subconjunto de instâncias por vez, mas lança instâncias adicionais para manter a capacidade. Evita a interrupção do serviço, mas aumenta os custos.  
- **imutável (immutable)**: Faz o upload e atualiza todas as instâncias em um novo grupo de autoescalação. Garante a confiabilidade do serviço, mas duplica os recursos.  
- **azul/verde**: Transfere gradualmente o tráfego de usuários de uma versão anterior da aplicação ou do microsserviço para uma nova versão praticamente idêntica, também executada em ambiente de produção. A versão antiga pode ser chamada de “ambiente azul”, enquanto a versão nova é chamada de “ambiente verde”. Após o tráfego em produção ser totalmente transferido do ambiente azul para o verde, o azul pode ser mantido para fins de reversão (rollback) ou retirado do ambiente de produção  
  
Ele pode ser usado através:  
  
- da console da AWS  
- da CLI da AWS  
- da SDK da AWS  
- do Eclipse  
  
E além da implantação, pode ser usado para:  
- **Gerenciamento de aplicações**: usando conceitos como ambientes, versões, configurações, políticas de implantação e grupos de autoescalação.  
- **Segurança de aplicações**: usando conceitos como grupos de segurança, perfis de instância do IAM, certificados SSL/TLS e VPCs.  

### Observações relevantes:
- O Elastic Beanstalk usa o auto-scaling na escalabilidade das aplicações, porém não é necessário configurar no Auto-scaling. Você pode especificar as características de dimensionamento desejadas, como a capacidade mínima e máxima de instâncias, e o Elastic Beanstalk gerenciará o dimensionamento automático com base nesses parâmetros.  O monitoramento da carga da sua aplicação é feito pelo serviço e ele mesmo ajusta o número de instâncias conforme necessário, tudo de forma automática e transparente.


## Possíveis integrações com outros serviços  
  
- Amazon S3: Pode ser usado para armazenar arquivos estáticos, backups de dados, e logs de aplicações.  
- Amazon CloudWatch: se integra com o CloudWatch para monitoramento e log  
- AWS IAM: para gerenciar permissões e controle de acesso  
- AWS SNS: pode ser configurado para enviar notificações sobre eventos do Elastic Beanstalk, como implantações, atualizações e falhas
- AWS CodePipeline e AWS CodeBuild: pode ser usado como um destino de implantação em uma pipeline de CI/CD.
	1. Configuração do Repositório de código-fonte. Pode ser um repositório no AWS CodeCommit, GitHub ou Bitbucket.
	2. AWS CodePipeline é configurado para orquestrar o fluxo de trabalho de CI/CD  
	3. AWS CodeBuild compila e testa o código  
	4. A implantação ocorre no AWS Beanstalk
      
## Caso de uso  

- Desenvolvimento e Teste Rápido: pode ser usado para criar ambientes de desenvolvimento e teste rapidamente. Isso permite que equipes de desenvolvimento implementem e testem novas funcionalidades ou correções de bugs em um ambiente que replica o ambiente de produção sem a complexidade de configurar a infraestrutura manualmente.
- Implementação de Microserviços:  pode ser usado para implantar microserviços individuais. Cada microserviço pode ser gerenciado como um aplicativo separado, com seu próprio ciclo de vida de desenvolvimento, escalabilidade e monitoramento. Isso facilita a implementação de arquiteturas de microsserviços distribuídas.
- Prototipagem e Provas de Conceito (PoCs): para quem precisa validar rapidamente uma ideia, Elastic Beanstalk permite a criação rápida de protótipos e provas de conceito. A facilidade de deploy e gerenciamento automático da infraestrutura permite que o foco esteja na funcionalidade e validação da ideia.  

> Mas e como seria a execução dessa aplicação usada no Beanstalk em um serviço não gerenciado pela AWS?

#### Configuração Manual:
1.  **Provisionamento de Recursos**: Você precisa criar **manualmente** as instâncias EC2, configurar balanceadores de carga, definir regras de Auto Scaling e configurar grupos de segurança.
2.  **Deploy da Aplicação**: Enviar manualmente o código para as instâncias, configurar servidores web e servidores de aplicação.
3.  **Gerenciamento e Manutenção**: Monitorar continuamente os recursos, ajustar manualmente a capacidade com base na demanda e gerenciar patches e atualizações.
4.  **Escalabilidade**: Configurar e ajustar manualmente as políticas de Auto Scaling para responder a aumentos e diminuições na carga de trabalho.
5.  **Monitoramento**: Integrar e configurar manualmente ferramentas de monitoramento e logging, como o Amazon CloudWatch.

#### AWS Elastic Beanstalk:
1.  **Provisionamento Automático de Recursos**: Você simplesmente carrega seu código e o Elastic Beanstalk cuida do provisionamento de todos os recursos necessários (instâncias e outros serviços).
2.  **Deploy Simplificado**: O Elastic Beanstalk facilita o deploy do código da aplicação, gerenciando automaticamente a implantação, balanceamento de carga e escalabilidade.
3.  **Gerenciamento Automatizado**: O Elastic Beanstalk gerencia automaticamente a infraestrutura, aplicando patches, realizando atualizações e monitorando a saúde dos recursos.
4.  **Escalabilidade Automática**: O Elastic Beanstalk ajusta automaticamente a capacidade com base na demanda da aplicação, garantindo que ela permaneça responsiva e disponível.
5.  **Monitoramento Integrado**: Integração com o Amazon CloudWatch para monitorar a aplicação e os recursos subjacentes, fornecendo métricas e logs detalhados.

## Cobrança  
Não há custo adicional para o AWS Elastic Beanstalk. Você paga pelos recursos da AWS (como instâncias do EC2 ou buckets do S3) que criar para armazenar e executar seu aplicativo.  
  
## Fontes de consulta
Algumas perguntas relacionadas foram feitas para o GPT-3.5. e suas respostas usadas de guia para montar o texto juntamente com a consulta aos links abaixo:
- [ ] https://aws.amazon.com/pt/elasticbeanstalk/
- [ ] https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3.html
- [ ] https://aws.amazon.com/pt/elasticbeanstalk/pricing/

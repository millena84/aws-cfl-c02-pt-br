Nesse post, vamos falar um pouco mais sobre ECS e EKS usando analogia para ficar mais didático.
  
## Vamos falar sobre estacionamentos e carros?

Vamos associar os termos técnicos com termos relacionados a estacionamentos e carros:

-   **Amazon ECS** = uma pessoa que gerencia um andar de um estacionamento
-   **Contêiner** = cada carro estacionado
-   **Amazon EKS** = gerenciador de vários andares de um estacionamento
-   **Kubernetes** = uma prática de gerenciar vários andares de estacionamento

Existe uma pessoa responsável pelo gerenciamento das vagas dos estacionamento (Amazon ECS). Essa pessoa facilita o processo de estacionar e organizar os carros (contêineres) garantindo que cada um tenha seu lugar designado. Ele também checa as credenciais dos motoristas (habilitação) para saber se eles estão dirigindo o carro correto (tipo da habilitação) e define para quais setores do andar eles deveriam ser designados (vans em um, carros em outro, motos em outro, etc), estaciona os carros, corrige uma baliza torta e etc.
> Mas e para administrar um estacionamento de 10 andares?

É aqui que entra o gerenciador de vários andares de estacionamento (Amazon EKS). Usando a prática de gerenciar o estacionamento inteiro (Kubernetes). Ele orquestra o trabalho de cada andar de estacionamento de uma vez só, eliminando a necessidade de ter uma pessoa administrando por andar. Ele reposiciona os veículos nas melhores vagas, corrige os que estão com baliza errada, otimiza o espaço por setor, tudo isso de uma vez.

## Agora vamos voltar a falar de tecnologia?

O Amazon ECS é um serviço gerenciado pela AWS que permite administrar e orquestrar contêineres baseados em docker.
> Mas que raios é Docker?

Docker é uma plataforma que facilita a criação, distribuição e execução de contêineres. Ele seu próprio mecanismo de orquestração nativo da AWS para gerenciar contêineres. 

**Pensando no termo "serviço gerenciado"**: toda vez que ele aparecer, saiba que o contratante não tem que se preocupar com infraestrutura. Isso significa que na AWS, o contratante pode usar tanto uma instância EC2 com docker como o ECS. Depende de quanto controle em cima da infraestrutura ele deseja ter.

Já o Amazon EKS é um serviço gerenciado pela AWS que facilita a execução do Kubernetes na AWS sem precisar instalar e operar o próprio Kubernetes. 
> Mas que raios é Kubernetes?

É um sistema (aberto e criado pelo google) para automatizar a implantação, o dimensionamento e a gestão de aplicações em contêineres. Se usa quando se tem muitos contêineres para administrar. 

Você deve considerar a transição do uso apenas de Docker para usar Kubernetes é quando suas aplicações em contêineres começam a crescer em complexidade e escala (> centenas de microserviços).

Sendo assim, a diferença entre eles é a complexidade:

- O ECS usa o orquestrador da AWS; EKS usa Kubernetes.
- O ECS é mais simples e fácil de usar; EKS oferece mais flexibilidade e controle.
- O ECS é altamente integrado com a AWS; EKS oferece portabilidade para outros ambientes Kubernetes.
- O ECS é ideal para quem quer simplicidade e integração direta com AWS; EKS é ideal para quem precisa de funcionalidades avançadas e tem experiência com Kubernetes.

## Fontes
***Esse conteúdo foi criado através das respostas de várias perguntas para a Luri (a IA generativa da Alura) e para o chat-GPT (GPT-3.5). Todas elas foram interpretadas e refinadas antes de vir para este post.***

# Amazon Lightsail ![Ícone Amazon Lightsail](https://icon.icepanel.io/AWS/svg/Compute/Lightsail.svg)

## Funcionalidade
Serviço da AWS projetado para ser uma maneira simples e acessível de começar a usar a nuvem. Ele é ideal para desenvolvedores, pequenas empresas, estudantes e outros usuários que precisam de uma solução de hospedagem fácil de configurar, com preços previsíveis e um conjunto de recursos básicos.
Ele traz algumas opções de serviços simples e abstrai parte da configuração, tornando-se intuitivo e fácil de usar.
Os preços são previsíveis (sendo mensais e fixos) incluindo instâncias de máquinas virtuais, armazenamento, transferência de dados e endereços IP. 
Além disso, é possível:
- Fazer monitoramento do que é configurado no Lightsail
- Fazer registro de domínio
- Usar o lightsail nos pontos de presença para distribuição de conteúdo (CDN)


## Opções ~~e entendimento~~

### Servidores 
-   Instâncias pré-configuradas com várias opções de sistema operacional (Linux/Unix e Windows) e aplicativos como WordPress, LAMP stack, e outros.

### Contêineres
- Contêiner é um recurso altamente escalável. Você pode implantar, executar e gerenciar contêineres. 
	- Um contêiner é uma unidade padrão de software que empacota o código e suas dependências para que o aplicativo seja executado de forma rápida e confiável de um ambiente de computação para outro.
	- Consulte também: [ECS, Docker, EKS e Kubernetes "em um tweet" e com analogia](https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/extras/ecs-docker-eks-k8s-em-1-tweet.md)

### Armazenamento de objetos
São dois tipos. Você pode criar um Bucket ou um Disk:

-   Bucket
    -   Funciona tal qual um  _Bucket do S3_, porém a concessão de acesso é simplificada
-   Disk
    -   _Armazenamento em bloco_. Discos que são anexados nas instâncias do Lightsail

### Snapshots e backups
Backup das instâncias e discos lightsail
 
### Banco de dados
Criação de banco de dados MySQL ou PostgreSQL. É possível:

-   Fazer backup de seu banco de dados para um snapshot.
-   Criar um novo banco de dados maior a partir de um snapshot.
-   Solucionar problemas comuns com logs e métricas baseados em navegador.
-   Recuperar dados usando operações de backup e restauração a partir de um momento específico.

Além disso, é possível desenvolver uma aplicação em uma instância do Lightsail e conectá-la ao um banco de dados.

### Recursos de rede
Ele tem integrado:
- Um _load balancer_ no qual pode-se criar um balanceador de carga para distribuir o tráfego.
- _Endereços IP estáticos_ para manter o mesmo endereço IP sempre que reinicializar sua instância.

## Possíveis integrações com outros serviços
- Amazon Route 53, na criação do DNS
- Amazon S3, para armazenar grandes quantidades de dados que precisam ser acessados por seus aplicativos Lightsail.
- Amazon RDS, caso o contratante precise de funcionalidades avançadas e suporte a diferentes tipos de bancos de dados como MySQL, PostgreSQL, MariaDB, Oracle e SQL Server.
- Amazon CloudFront, pode ser usado para distribuir conteúdo do seu site Lightsail globalmente com baixa latência e alta velocidade.
- AWS IAM, para gerenciar o acesso aos seus recursos Lightsail e definir permissões detalhadas.

## Caso de uso
- **Sites e Blogs**:  
    -   Hospedagem de sites simples e blogs usando CMS populares como WordPress.
- **Aplicativos Web**: 
    -   Desenvolvimento e implantação de aplicativos web básicos e APIs.
- **Ambientes de Desenvolvimento/Teste**: 
    -   Criação de ambientes de desenvolvimento e teste que podem ser facilmente replicados e gerenciados.
- **Projetos Educacionais**:   
    -   Ideal para estudantes e educadores que desejam aprender e ensinar sobre hospedagem web e desenvolvimento de aplicativos na nuvem.


## Cobrança
Na cobrança, está Incluído em todos os planos do Lightsail

-   Endereço IP estático
-   Console de gerenciamento intuitivo
-   Gerenciamento de DNS
-   Acesso ao terminal SSH com um clique (Linux/Unix)
-   Acesso ao RDP com um clique (Windows)
-   API avançada
-   Armazenamento SSD altamente disponível
-   Monitoramento de servidores

Caso o uso dos recursos seja apartado, a escolha de valor (em dólar) x capacidade da máquina mensal:
-   Depende da funcionalidade usada
    -   Tem preço único
        -   Load balancer
        -   snapshot
    -   Servidores
        -   Cobrança mensal por capacidade de máquina
    -   Contêineres
        -   Cobrança mensal por tamanho do contêiner
    -   Armazenamento
        -   Cobrança por total de armazenamento e transferência
    -   Banco de dados
        -   Cobrança por capacidade computacional direcionada para o banco
    -   CDN
        -   Total de transferência de dados
    -   Armazenamento em blocos
        -   Cobrança por total de armazenamento
    -   Pesquisa
        -   Tamanho da máquina

## Fontes de consulta
Algumas perguntas relacionadas foram feitas para o GPT-3.5. e suas respostas usadas de guia para montar o texto juntamente com a consulta aos links abaixo:
-   [https://aws.amazon.com/pt/free/compute/lightsail/](https://aws.amazon.com/pt/free/compute/lightsail/) 
-   [https://lightsail.aws.amazon.com/ls/docs/en_us/articles/amazon-lightsail-choosing-a-database](https://lightsail.aws.amazon.com/ls/docs/en_us/articles/amazon-lightsail-choosing-a-database)
-   [https://lightsail.aws.amazon.com/ls/docs/pt_br/articles/buckets-in-amazon-lightsail](https://lightsail.aws.amazon.com/ls/docs/pt_br/articles/buckets-in-amazon-lightsail)
-   [https://lightsail.aws.amazon.com/ls/docs/pt_br/articles/amazon-lightsail-understanding-bucket-permissions](https://lightsail.aws.amazon.com/ls/docs/pt_br/articles/amazon-lightsail-understanding-bucket-permissions)
-   [https://lightsail.aws.amazon.com/ls/docs/pt_br/articles/elastic-block-storage-and-ssd-disks-in-amazon-lightsail](https://lightsail.aws.amazon.com/ls/docs/pt_br/articles/elastic-block-storage-and-ssd-disks-in-amazon-lightsail)
-   [https://lightsail.aws.amazon.com/ls/docs/pt_br/articles/amazon-lightsail-databases](https://lightsail.aws.amazon.com/ls/docs/pt_br/articles/amazon-lightsail-databases)

-   

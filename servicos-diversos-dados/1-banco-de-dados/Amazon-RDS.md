# Amazon RDS![Ícone Amazon RDS](https://icon.icepanel.io/AWS/svg/Database/RDS.svg)
 
## Funcionalidade  
 1. É um  **serviço gerenciado**  que facilita a configuração, operação e dimensionamento de um  **banco de dados relacional**  na nuvem
 2. Alta performance com SSD / provisioned IOPS SSD
 3. Alta disponibilidade

O RDS auxilia, não somente na migração de banco de dados, como também na execução. Por ser um serviço gerenciado pela AWS, ele abstrai diversas tarefas, tais como: 
 - Provisionamento da infraestrutura, instalação, configuração, atualização e aplicação de patches
 - Gerenciamento de backups
 - Monitoramento (para failover) e alarmes
 - Escalabilidade

  
## Opções e Entendimento  
### Funcionalidades especiais
#### Read-replicas
   -   Alta disponibilidade de leitura
   -   É uma snapshot do BD que é atualizada de forma síncrona
   -   Requisições de leitura podem ser direcionadas para as Replicas
       -   Estatisticamente, existem mais leituras do que gravações em um BD
   -   Podem ser adicionadas várias réplicas
   -   Em caso de manutenção da instância principal, as requisições de leitura são servidas pelas replicas

#### Multi-AZ deployments
   -   Alta disponibilidade “geral”
   -   o Amazon RDS automaticamente providencia e mantém uma  **réplica “em espera” simultânea em uma zona de disponibilidade diferente**.
   -   As atualizações de instância de banco de dados são replicadas simultaneamente por meio de zonas de disponibilidade para a espera, a fim de manter ambos em sincronia e proteger as últimas atualizações de banco de dados contra falhas de instância de banco de dados.
   -   RDS atualiza o DNS para apontar para uma segunda instância em 60-120 segundos
   -   Acontece nos seguintes casos:
       -   Manutenção
       -   Falha no host
       -   Falha na AZ
       -   Reboot da instância
       -   Mudança da configuração da instância (exemplo: tamanho)

#### Importante: sobre as funcionalidades especiais:
As read-replicas sem associação com o Multi-AZ deployment não tem failover automático e não é possível configurar essa funcionalidade.

> O que significa na prática?

Que, caso a instância principal falhe por qualquer motivo, é necessária uma ação manual para promover uma read-replica a instância principal. Sem associação com o Multi-AZ Deployment, não tem suporte para configurar o failover automático.
Usando o Multi-AZ deployment, o failover é automático por padrão: O RDS monitora a instância principal e, em caso de falha, promove automaticamente uma réplica a instância principal.

### Tipos de instância
- Uso geral: cargas de trabalho variadas
- Otimizadas por memória: cargas de trabalho que exigem grande quantidade de memória, precisam de cache, análise em memória ou aplicativos big data
	- OBS:. considerando que é um banco de dados RELACIONAL, a indicação mais adequada seria para volumes moderados. É importante considerar também a natureza dos dados.

### Escalabilidade
- vertical: o RDS aumenta o tamanho da instância
- horizontal: o RDS dimensiona mais réplicas para leitura
Deve ser configurada e, no caso da horizontal, não usa o auto-scaling, o próprio RDS se encarrega.

### Bancos suportados
-   Aurora*
-   PostgreSQL
-   MySQL
-   MariaDB
-   Oracle
-   SQL Server



## Possíveis integrações com outros serviços  
- **AWS Lambda**: para responder a eventos no Amazon RDS, como alterações nos dados do banco de dados
	- Isso permite a execução de lógica personalizada em resposta a eventos no banco de dados >> Pilar Excelência operacional do WAF
- **Amazon S3**: para fazer backup e restaurar bancos de dados do Amazon RDS ou para armazenar arquivos de log do banco de dados
- **Amazon Redshift**: para transferir dados entre os dois serviços, permitindo análises mais avançadas dos dados do banco de dados.
-  **Amazon CloudWatch**: para poder publicar métricas de desempenho, permitindo monitorar o desempenho do banco de dados e configurar alarmes com base nessas métricas.
> Mas qual a diferença do monitoramento interno do RDS com o uso do CloudWatch associado?
1. RDS: métricas básicas como CPU, memória, uso de armazenamento e IOPS da instância de banco de dados
2. Cloudwatch: métricas adicionais como desempenho, latência de throughput (leitura e gravação), contagem de conexões e etc
Isso fora os dashboards que podem ser criados.
- **AWS Key Management Service (KMS)**: É possível usar o KMS para criptografar dados em repouso no Amazon RDS, garantindo a segurança dos dados sensíveis.
> Mas qual a diferença da criptografia interna do RDS com o uso do KMS associado?
1. RDS: usa chaves de criptografia gerenciadas pelo próprio serviço para criptografar dados em repouso no banco de dados e não é necessária intervenção do usuário, porém tem as seguintes limitações como não permitir controle direto de chaves e não permitir que você gerencie seu ciclo de vida
2. KMS: permite um controle total sobre as chaves de criptografia usadas para proteger seus dados, logo, é possível criar, gerenciar e rotacionar suas próprias chaves de criptografia, bem como gerenciar seu ciclo de vida. 


## Caso de uso  
- Qualquer aplicação que use banco de dados relacional
> Ah, mas e o Amazon Aurora? Quando eu poderia usar?

Bem, sim, o Aurora é uma variante do MySQL e do PostgreSQL otimizada para a nuvem da AWS. Porém para considerar seu uso, é necessário ponderar:
 - Custo: O RDS pode ser mais econômico
 - Compatibilidade com o banco de dados "original": se sua aplicação foi projetada especificamente para o "original" ou se sua familiaridade for maior com ele, pode ser mais custoso e difícil migrar para o Aurora
 - Recursos específico do banco de dados "original": se sua aplicação usa recursos específicos, pode não ser adequado migrar para o Aurora
 - Tamanho das cargas de trabalho: se elas tendem a ser menores, pode não ser adequado migrar para o Aurora
 - Flexibilidade de configuração: se você deseja ter mais controle em cima da configuração do banco de dados, o RDS 


## Cobrança  
-   Tem o nível gratuito
-   Fora o nível gratuito, a definição de preço depende do modelo que se está migrando:
    -   Aurora
        -   Taxa de armazenamento
        -   Taxa de IO
        -   Taxa de backup
        -   Exportação de snapshot
        -   Transferência de dados
    -   MySQL, PostgreSQL, MariaDB, Oracle*, SQL Server*
        -   Mono AZ
        -   Multi AZ
        -   Instâncias padrão x otimizadas por memória
        -   Instâncias sob demanda x instâncias reservadas
        -   Armazenamento de uso geral x armazenamento com IOPS x armazenamento magnético
        -   Backup
        -   Exportação de snapshot
        -   Transferência de dados
        -   *também varia o preço de acordo com a licença/versão tratada na AWS


## Fontes de consulta
Algumas perguntas relacionadas foram feitas para o GPT-3.5. e suas respostas usadas de guia para montar o texto juntamente com a consulta aos links abaixo:

- [ ] https://aws.amazon.com/pt/rds/
- [ ] https://aws.amazon.com/pt/rds/resources/
- [ ] https://docs.aws.amazon.com/pt_br/AmazonRDS/latest/UserGuide/Welcome.html
- [ ] https://aws.amazon.com/pt/rds/features/security/
- [ ] https://aws.amazon.com/pt/rds/mysql/
- [ ] https://aws.amazon.com/pt/rds/instance-types/

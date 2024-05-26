# Amazon Aurora![Ícone Amazon Aurora](https://icon.icepanel.io/AWS/svg/Database/Aurora.svg)
 
## Funcionalidade  
**Banco de dados relacional**  totalmente gerenciado pela AWS (através do AWS RDS). Ele faz parte da família de serviços do Amazon RDS
> O que isso significa?

Significa que seu gerenciamento ocorre pela console do Amazon RDS, ou pelo AWS CLI ou pela API do RDS. Ou seja: não dá para usar o Aurora sem usar o RDS.

-   automatiza tarefas administrativas demoradas como provisionamento de hardware, configuração do banco de dados, aplicação de patches e backups.

  
## Opções e Entendimento  
-   Compatível com MySQL e PostgreSQL, sendo:
    -   5 x mais rápido que o MySQL
    -   3 x mais rápido que o PostgreSQL
-   1/10 do custo comparado com concorrentes
-  Otimizado para desempenho e alta disponibilidade
-   Alta disponibilidade
    -   Também tem  **read-replicas**  (até 15 de leitura)
    -   Backup contínuo no S3
    -   Sistema de armazenamento distribuído – escala até 128 TB por instância
    -   **Replicação entre 3 AZs**

### Global Database
Um único banco de dados Aurora por abranger várias regiões da AWS
-   Ele replica seus dados sem impacto no desempenho do banco de dados
-   Permite leituras locais rápidas com baixa latência em cada região 
    -    Regiões secundárias podem ser usadas para cargas de trabalho de leitura intensa sem impactar o desempenho da região primária
-   Fornece recuperação de desastres de interrupções em toda a região
-   Pode ser usado no modelo instância ou serveless
-   Provisionamento automático

### Gerenciamento do Aurora através do RDS
1.  **Provisionamento de Instâncias**: criação e gerenciamento das instâncias de banco de dados Aurora através do console do Amazon RDS. Durante a criação, você escolhe o tipo de banco de dados (Aurora MySQL ou Aurora PostgreSQL) e configura opções como tipo de instância, tamanho de armazenamento, e configurações de rede.
	- O processo de provisionamento é simplificado e automatizado, permitindo que você defina configurações iniciais e deixe o RDS cuidar da configuração do banco de dados.
2.  **Backup e Recuperação**:  oferece backups automáticos contínuos que são gerenciados pelo RDS. Você pode configurar a retenção de backups e realizar recuperações em ponto no tempo através do console do RDS.
3.  **Escalabilidade e Replicas**: pode ser gerenciado através da  adição de replicas de leitura. O Aurora suporta até 15 replicas de leitura com latência extremamente baixa.
    -   A escalabilidade de armazenamento é automática, com o Aurora ajustando a capacidade de armazenamento conforme necessário, até um máximo de 128 TB.
4.  **Segurança**: Integração com o AWS IAM (Identity and Access Management) permite gerenciar permissões e acesso ao banco de dados Aurora.
5.  **Monitoramento e Alerta**: O Amazon CloudWatch é utilizado para monitorar métricas de desempenho do Aurora, permitindo configurar alarmes e visualizações personalizadas.
    -   Logs de auditoria e performance podem ser habilitados e gerenciados através do RDS.
6.  **Patching e Manutenção**: gerenciamento da aplicação de patches e atualizações ao banco de dados Aurora, garantindo que o software esteja atualizado e seguro.
    -   Janela de manutenção pode ser configurada para controlar quando as atualizações são aplicadas.

> NÃO É POSSÍVEL USAR O AMAZON AURORA SEM USAR O AMAZON RDS

> Importante:  existem tipos de configuração em que o controle granular no Amazon RDS é maior do que no Amazon Aurora e vice-versa, porém, não é o foco dessa certificação

### Bancos suportados
-   PostgreSQL
-   MySQL
Suportados na questão compatibilidade. Uma vez migrado para o Aurora, o banco passa a ser Aurora (e não mais MySQL ou PostgreSQL) 


## Possíveis integrações com outros serviços  
- **Amazon RDS**: integração por padrão, para uso da console do RDS para configurar o Aurora
- **AWS Lambda**: para responder a eventos no Amazon RDS, como alterações nos dados do banco de dados
	- Isso permite a execução de lógica personalizada em resposta a eventos no banco de dados >> Pilar Excelência operacional do WAF


## Caso de uso  
Aplicações que exigem alto desempenho e disponibilidade, escalabilidade e durabilidade
Ou ainda: 
-   Aplicações de SaaS (Software como Serviço) de massiva utilização: Com recursos de isolamento e segurança, suporte para escalabilidade horizontal com replicas de leitura, alta disponibilidade e recuperação automática, o Aurora pode sser uma excelente opção.
-   Aplicações distribuídas globalmente: jogos digitais, e-commerce global usando o Aurora Global Database
-   Tecnologia  **serverless**

> Como escolho entre Aurora e Amazon RDS?

Bem, sim, o Aurora é uma variante do MySQL e do PostgreSQL otimizada para a nuvem da AWS. Porém para considerar seu uso, é necessário ponderar:
 - Custo: O RDS pode ser mais econômico
 - Compatibilidade com o banco de dados "original": se sua aplicação foi projetada especificamente para o "original" ou se sua familiaridade for maior com ele, pode ser mais custoso e difícil migrar para o Aurora
 - Recursos específico do banco de dados "original": se sua aplicação usa recursos específicos, pode não ser adequado migrar para o Aurora
 - Tamanho das cargas de trabalho: se elas tendem a ser menores, pode não ser adequado migrar para o Aurora
 - Flexibilidade de configuração: se você deseja ter mais controle em cima da configuração do banco de dados, o RDS 
 - Desempenho: O Aurora é projetado para ser bem mais performático que os bancos originais

Além disso: 
 - Escalabilidade de armazenamento automática
 - Suporta até 15 read-replicas


## Cobrança  
-   Sob demanda ou instância reservada
    -   Taxa de armazenamento / Taxa de IO
    -   Taxa de backup
    -   Restauração
    -   Exportação de snapshot
    -   Transferência de dados



## Fontes de consulta
Algumas perguntas relacionadas foram feitas para o GPT-3.5. e suas respostas usadas de guia para montar o texto juntamente com a consulta aos links abaixo:
- [ ] https://aws.amazon.com/pt/rds/
- [ ] https://aws.amazon.com/pt/rds/resources/
- [ ] https://docs.aws.amazon.com/pt_br/AmazonRDS/latest/UserGuide/Welcome.html
- [ ] https://aws.amazon.com/pt/rds/features/security/
- [ ] https://aws.amazon.com/pt/rds/mysql/
- [ ] https://aws.amazon.com/pt/rds/instance-types/

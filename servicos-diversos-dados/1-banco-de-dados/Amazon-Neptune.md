# Amazon Neptune![Ícone Amazon Neptune](https://icon.icepanel.io/AWS/svg/Database/Neptune.svg)
 
## Funcionalidade  
É um serviço de **banco de dados gráfico (grafo)** rápido, confiável e totalmente gerenciado que facilita a criação e a execução de aplicativos.


## Opções e Entendimento  
Criado para armazenar relacionamentos e navegar entre eles:

-   Estrutura
    -   Nós: entidades de dados
    -   Bordas: relacionamentos
É serverless, tem alto throughput e baixa latência nas suas consultas com grafo.

### Funcionalidades especiais

-   **Read-réplicas**   
    Para leituras de baixa latência
    
-   **Multi A-Z**
    Failover para uma das até 15 réplicas do Neptune criadas em uma das três zonas de disponibilidade. Em caso de falha, se nenhuma réplica do Neptune foi provisionada, ele tentará criar automaticamente uma nova instância de banco de dados.
    
-   **Backup automático, restauração ‘point-in-time’**
    Isso permite que você restaure o banco de dados para qualquer segundo durante o período de retenção, até os últimos cinco minutos.
    
-   **Global**
    Ele replica os dados de grafos com pouco impacto na performance do banco de dados, permite leituras locais rápidas com baixa latência em cada região.


## Possíveis integrações com outros serviços  
-   IAM (controle de acesso)
-   KMS (criptografia de chaves)
-   CloudWatch (monitoramento e logs de auditoria)
-   S3


## Caso de uso  
-   Criação de redes sociais
-   Detectar padrões de fraude
-   Previsões de machine learning
-   Personalização do cliente 360


## Cobrança  
-   Sob-demanda
-   Por hora x Por tamanho de instância
-   Por volume de armazenamento
-   Por E/S
-   Por volume de backup armazenado
-   Por transferência de dados
-   Por hora serverless


## Fontes de consulta

- [ ] https://aws.amazon.com/pt/neptune/
- [ ] https://aws.amazon.com/pt/neptune/getting-started/
- [ ] https://aws.amazon.com/pt/neptune/pricing/
- [ ] https://aws.amazon.com/pt/neptune/features/
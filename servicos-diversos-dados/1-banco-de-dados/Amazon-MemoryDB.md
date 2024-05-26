# Amazon MemoryDB for Redis ![Ícone Amazon MemoryDB for Redis](https://icon.icepanel.io/AWS/svg/Database/MemoryDB-for-Redis.svg)
 
> *não consta no treinamento de 2023*

## Funcionalidade  
Serviço de banco de dados em memória, durável e compatível com Redis para **performance ultrarápida** e **gerenciado pela AWS**.

### Recordar é viver: NoSQL chave-valor
#### Informações sobre NoSQL
-   Criado em 2000 para explicar requisitos básicos para um sistema distribuído
-   Teorema CAP:
    -   Consistência = Todos os servidores terão os dados replicados iguais
    -   Disponibilidade = O sistema sempre estará disponível, mesmo que com o dado defasado
    -   Tolerância de partição = O sistema está sempre operante, mesmo que um dos servidores esteja fora do ar
-   Para o paradigma, somente duas opções são sempre possíveis (CA ou AP ou CP)
#### Informações sobre banco de dados chave-valor
-   Na AWS: MemoryDB for Redis
-   No "mercado": Redis, Memcached
-   Dados usados com frequência ficam em memória
-   Suporta estruturas de dados complexas por terem schema flexível


## Opções e Entendimento
-   **Durabilidade multi-AZ:** armazena dados em várias AZs (dentro de uma região da AWS) para proporcionar tolerância a falhas e maior disponibilidade, permitindo assim uma recuperação e reinicialização rápidas do banco de dados
-   **Read-replicas:** mantém uma cópia dos dados do nó primário. Isso permite distribuir a carga de leitura e melhorar a performance
-   **Pesquisa vetorial:** permite realizar buscas eficientes em grandes volumes e dados usando vetores (representações matemáticas de dados). Relacionado a ML e IA generativa


## Possíveis integrações com outros serviços  
-	**Amazon S3 (Simple Storage Service)**: para armazenar grandes volumes de dados brutos (imagens, texto, vídeos) que serão processados e transformados em vetores ou ainda para backup e recuperação.
-	**Amazon SageMaker**: para treinar modelos de machine learning que geram embeddings vetoriais (códigos que transformam informações complexas em conjuntos de números) a partir de dados brutos.
-	**AWS Lambda**: usando funções Lambda para processar eventos em tempo real e atualizar os vetores no MemoryDB.
-	**Amazon Kinesis**: para coleta, processamento e analise dados em tempo real antes de armazená-los como vetores no MemoryDB.


## Cobrança  
-   Nós sob demanda
-   Nós reservados (semelhante às instâncias reservadas do EC2, mas sem flexibilidade da conversão)
-   Dados gravados
-   Armazenamento de snapshots


## Fontes de consulta 
Algumas perguntas relacionadas foram feitas para o GPT-3.5. e suas respostas usadas de guia para montar o texto juntamente com a consulta aos links abaixo:
- [ ] https://aws.amazon.com/pt/memorydb
- [ ] https://aws.amazon.com/pt/memorydb/features/
- [ ] https://aws.amazon.com/pt/connect/getting-started/
- [ ] https://aws.amazon.com/pt/connect/pricing/
- [ ] https://aws.amazon.com/pt/memorydb/resources/
- [ ] https://docs.aws.amazon.com/memorydb/
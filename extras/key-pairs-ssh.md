## Um pouco sobre Keys pairs

As key pairs de acesso SSH são pares de chaves criptográficas usadas no acesso de instâncias EC2 de forma segura. 
Elas têm em uma chave pública e uma chave privada.

1. **Chave Pública**:
   - **Definição**: É a chave pública é armazenada na instância EC2.
   - **Função**: Quando você tenta acessar a instância, a AWS usa a chave pública para verificar a correspondência com a chave privada.

2. **Chave Privada**:
   - **Definição**: É a chave privada é mantida pelo usuário e deve ser guardada em segurança.
   - **Função**: Utilizada para se autenticar ao acessar a instância EC2 via SSH.

### Criando e Usando Key Pairs

1. **Criação de um Key Pair na AWS Management Console**:
   - Acesse o **AWS Management Console**.
   - Vá para o serviço **EC2**.
   - No menu à esquerda, clique em **Key Pairs** (ou **Pares de Chaves**).
   - Clique em **Create Key Pair**.
   - Dê um nome ao seu key pair e clique em **Create**.
   - A chave privada (.pem) será baixada automaticamente para o seu computador. Guarde-a em um local seguro.

2. **Conectando-se a uma Instância EC2 usando SSH**:
   - Abra um terminal no seu computador.
   - Navegue até o diretório onde a chave privada (.pem) está armazenada.
   - Use o comando SSH para conectar à instância EC2. O comando geralmente se parece com isso:

     ```bash
     ssh -i /caminho/para/sua-chave.pem ec2-user@seu-endereco-ip
     ```

     Exemplo:

     ```bash
     ssh -i ~/.ssh/minha-chave.pem ec2-user@198.51.100.1
     ```

3. **Configuração de Permissões da Chave Privada**:
   - Antes de conectar, é importante definir as permissões corretas para a chave privada. Isso pode ser feito usando o comando `chmod`:

     ```bash
     chmod 400 /caminho/para/sua-chave.pem
     ```

### Porque usar 

1. **Acesso Seguro à Instância EC2**:
   - Key pairs são usados para permitir o acesso seguro e criptografado a instâncias EC2, garantindo que apenas usuários autorizados possam se conectar.

2. **Automatização e Deploys**:
   - Em ambientes de CI/CD (Integração Contínua/Entrega Contínua), key pairs são usados para acessar instâncias EC2 e realizar deploys automatizados de aplicações.

3. **Administração de Servidores**:
   - Administradores de sistemas usam key pairs para acessar e gerenciar servidores, realizar manutenção e aplicar atualizações de segurança.

### Boas Práticas

- **Proteção da Chave Privada**: A chave privada deve ser mantida em segurança e nunca compartilhada. Se a chave privada for comprometida, qualquer pessoa poderá acessar suas instâncias EC2.
- **Gerenciamento de Acesso**: Crie key pairs diferentes para diferentes usuários ou propósitos. Evite usar a mesma key pair para múltiplos usuários ou ambientes.
- **Rotação de Chaves**: Periodicamente, rote suas chaves para melhorar a segurança. Crie novas key pairs e atualize suas instâncias para usar as novas chaves.

As key pairs de acesso SSH são uma parte fundamental da segurança na AWS, garantindo que apenas usuários autorizados possam acessar suas instâncias EC2.

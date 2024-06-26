# Índice - Conteúdo - AWS Cloud Practitioner - CFL-C02

Em construção

## Guia de certificação:
[Guia do exame AWS Certified Cloud Practitioner (CFL-C02)](https://d1.awsstatic.com/pt_BR/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Exam-Guide.pdf)


## Serviços - versão extendida:
### Diversos - computação:
  <details>
      <summary><b>Computação</b></summary>
        <ol>
          <li><a href="https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/servicos-diversos-computacao/1-computacao/AWS-Batch.md">Amazon Batch</a></li>
          <li><a href="https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/servicos-diversos-computacao/1-computacao/Amazon-EC2.md">Amazon EC2*</a></li>
          <li><a href="https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/servicos-diversos-computacao/1-computacao/AWS-Elasic-Beanstalk.md">AWS Elastic Beanstalk</a></li>
          <li><a href="https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/servicos-diversos-computacao/1-computacao/Amazon-Lightsail.md">Amazon Lightsail</a></li>
          <li><a href="https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/servicos-diversos-computacao/1-computacao/AWS-Local-Zones.md">Zonas Locais da AWS*</a></li>
          <li>AWs Outposts</li>
          <li>AWs Wavelenght</li>
        </ol>
  </details>
  <details>
      <summary><b>Sem servidor</b></summary>
        <ol>
          <li><a href="https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/servicos-diversos-computacao/3-sem-servidor/AWS-lambda.md">AWS Lambda*</a></li>
          <li>AWs Fargate</li>
        </ol>
  </details>
  <details>
      <summary><b>Contêineres</b></summary>
        <ol>
          <li>AWS ECS</li>
          <li>AWS EKS</li>
          <li>AWS ECR</li>
        </ol>
  </details>
    <details>
      <summary><b>Computação de usuário final</b></summary>
        <ol>
          <li>Amazon AppStream 2.0</li>
          <li>Amazon Workspaces</li>
          <li>Amazon Workspaces Web</li>
        </ol>
  </details>
  <details>
      <summary><b>Web e dispositivos móveis</b></summary>
        <ol>
          <li>AWs Device Farm</li>
          <li>AWs Amplify</li>
          <li>AWS App Sync</li>
        </ol>
  </details>
  <details>
      <summary><b>Internet das coisas</b></summary>
        <ol>
          <li>IoT Core</li>
          <li>IoT greengrass</li>
        </ol>
  </details>
  
--- 


# Visão do conteúdo - Mapa mental:
Contém somente os nomes dos serviços

<details>
<summary>Diversos computação:</summary>
  
```mermaid
graph LR
01[Diversos computação] --> 001(Computação) --> 0001(AWS Batch)
001 --> 0002(Amazon EC2)
001 --> 0003(AWS Elastic Beanstalk)
001 --> 0004(Amazon Lightsail)
001 --> 0005(Zonas Locais da AWS)
001 --> 0006(AWS Outposts)
001 --> 0007(AWS Wavelenght)

01 --> 002(Contêineres)
002 --> 0008(Amazon ECS)
002 --> 0009(Amazon EKS)
002 --> 0010(Amazon ECR)

01 --> 003(Usuário final)
003 --> 0011(Amazon AppStream 2.0)
003 --> 0012(Amazon WorkSpaces)
003 --> 0013(Amazon WorkSpaces Web*)

01 --> 004(Web e dispositivos móveis)
004 --> 0014(AWS Amplify)
004 --> 0015(AWS AppSync)
004 --> 0016(AWS Device Farm)

01 --> 005(Internet das coisas)
005 --> 0017(AWS IoT Core)
005 --> 0018(AWS IoT Greengrass)

01 --> 006(Sem servidor)
006 --> 0019(AWS Lambda)
006 --> 0020(AWS Fargate)

```
</details>

---


# Conteúdo extra
- [Mapa mental - CFL-C02](https://www.mindmeister.com/app/map/3008228986?t=NOu7B2okNO)

## Informações do entorno
- [Um pouco sobre Keys pairs](https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/extras-artigos/key-pairs-ssh.md)

## Insights e etc
### Computação
- [Comparação EC2 x Lightsail](https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/extras-artigos/comparacao-ec2-lightsail-em-um-tweet.md)
- [ECS, Docker, EKS e Kubernetes "em um tweet" e com analogia](https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/extras-artigos/ecs-docker-eks-k8s-em-1-tweet.md)


--- 

# Não cai na CFL-C02, porém, convém conhecer para as próximas:
  <details>
      <summary><b>Banco de dados</b></summary>
        <ol>
          <li><a href="https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/servicos-diversos-dados/1-banco-de-dados/Amazon-ElastiCache(nao-cai).md">Amazon ElastiCache</a></li>
        </ol>
  </details>
  <details>
      <summary><b>Analytics</b></summary>
        <ol>
          <li><a href="https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/servicos-diversos-dados/3-analytics/Amazon-CloudSearch(nao-cai).md">Amazon CloudSearch</a></li>
        </ol>
  </details>
  <details>
  <details>
      <summary><b>Integração de aplicativos</b></summary>
        <ol>
          <li><a href="https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/servicos-diversos-dados/4-integracao-aplicativos/Amazon-MQ(nao-cai).md">Amazon MQ</a></li>
        </ol>
  </details>
  <details>
      <summary><b>Transferência de dados</b></summary>
        <ol>
          <li><a href="https://github.com/millena84/aws-cfl-c02-pt-br/blob/main/servicos-diversos-armazenamento-e-transferencia/2-migracao-e-transferencia/AWS-DataSync(nao-cai).md">AWS DataSync</a></li>
        </ol>
  </details>

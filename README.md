## 📖 Descrição
Este projeto foi desenvolvido como parte do **Desafio da DIO** com o objetivo de consolidar conhecimentos sobre **automação de tarefas utilizando AWS Lambda e Amazon S3**.  
A proposta é criar uma função Lambda capaz de reagir a eventos do S3 (como upload de arquivos) para executar uma ação automatizada, simulando um cenário prático de integração entre serviços da AWS.

---

## 🎯 Objetivos de Aprendizagem
Ao concluir este desafio, você será capaz de:
- Aplicar conceitos de automação em um ambiente prático na AWS;
- Documentar processos técnicos de forma clara e estruturada;
- Utilizar o GitHub como ferramenta de portfólio técnico e de versionamento.

---

## 🧰 Tecnologias e Serviços Utilizados
- **AWS Lambda** – Execução de código sem servidor  
- **Amazon S3** – Armazenamento de objetos e geração de eventos  
- **AWS IAM** – Controle de permissões e políticas de acesso  
- **AWS CloudFormation (opcional)** – Automação da infraestrutura  
- **Python 3.x** – Linguagem usada na função Lambda  
- **Git e GitHub** – Versionamento e documentação do projeto  

---

## ⚙️ Etapas do Projeto

### 1. Criação do Bucket S3
- Acesse o console da AWS e crie um **bucket S3**.
- Configure permissões básicas e habilite **notificações de eventos**.
- Defina o evento **ObjectCreated (All)** para acionar sua função Lambda.

### 2. Desenvolvimento da Função Lambda
A função Lambda será acionada sempre que um novo objeto for criado no bucket.

**Exemplo simples em Python:**
```python
import boto3
import json

def lambda_handler(event, context):
    print("Evento recebido:")
    print(json.dumps(event, indent=2))
    
    bucket = event['Records'][0]['s3']['bucket']['name']
    objeto = event['Records'][0]['s3']['object']['key']
    
    print(f"Arquivo {objeto} criado no bucket {bucket}")
    return {
        'statusCode': 200,
        'body': json.dumps('Processamento concluído com sucesso!')
    }
lambda-s3-automation/
│
├── README.md
├── /src
│   └── lambda_function.py
│
├── /images
│   ├── lambda-config.png
│   ├── s3-trigger.png
│
└── /notes
    └── insights.md

   ", event)
       return {"status": "success"}

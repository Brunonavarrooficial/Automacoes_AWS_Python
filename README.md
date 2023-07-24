# Automação AWS Python

- Criação de scripts para automatizar tarefas no cloud da Amazom Web Services.
- Linguagem Python
- Foram feitos 5 Scripts no Total
    - 1º - Criação Automatizada de Instância EC2 com Função Lambada AWS [Veja o Repositório](/script_1/)
    - 2º - S3 Resize Versão Thumbnail [Veja o Repositório](/script_2/)
    - 3º - EC2 - Snapshot [Veja o Repositório](/script_3/)
    - 4º - EC2 - Start/Stop [Veja o repositório](/script_4/)
    - 5º - DynamoDB - Backup - Lambda AWS [Veja o repositório](/script_5/)

![aws_automate_lambda](/script_2/assets/img/automate_aws.png)

#

### Projeto 1: Criação Automatizada de Instância EC2 com Função Lambada AWS

- Automação para gerar uma nova Instância EC2 com apenas um clique. 
- A instância gerada no teste é do tipo EC2 t2.micro.

#

### Projeto 2: S3 Resize Versão Thumbnail

- Automação para padronizar automaticamente o tamanho de dimensão específico para uma imagem enviada para um bucket S3 de origem. 
- A função lambda com recursos de IAM e trigger padronizada redimensiona a imagem para o tamanho de 128x128 (Thumbnail) e a envia para um bucket S3 de destino. 
- CloudWatch monitora todo o processo.

#

### Projeto 3: EC2 - Snapshot

- Automação para criar uma nova Instância EC2 a partir de um backup caso a instância atual esteja com problemas.
- A configuração da instância é feita adicionando uma nova tag "backup":"true".

#

### Projeto 4: EC2 - Start/Stop

- Automação para iniciar e parar instâncias EC2 para economizar recursos.
- As instâncias são paradas às 20h de segunda a sexta-feira e iniciadas às 6h de segunda a sexta-feira.

#

### Projeto 5: DynamoDB - Backup - Lambda AWS

Automação para criar backup das tabelas do banco de dados DynamoDB.


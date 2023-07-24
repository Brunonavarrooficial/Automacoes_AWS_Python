## EC2 - Snapshot

- Automação para criar uma nova Instância EC2 apartir de um backup caso a atual estiver com problemas.

- Configurando a Instância com uma nova tag "backup":"true" para somente as que tiverem essa tag fazer backup.

#

- Criação de Istância EC2
    - EC2 t2.micro
    - Manage Tags
        - Add tag = ("key":"value") exemplo: "backup":"true"

- CloudWatch
    - Programar para rodar a  função a cada horário desejado
    - Neste caso esta configurado para a cada 24 horas
        - Rules
            - Event Source - Schedule - Fixed rate of * days,hours,minutes....
            - Add target e configure rule details

- Função Lambda
    - Create a new role with basic Lambda permissions
    - IAM - acesso a instâncias EC2 e aos Snapshots - edit policy [aqui está o script](Script3+-+IAM+Role.txt)
    - Runtime python 3.7
    - Timeout para 1 minuto.
    - Configurations - Configure a lambda_function [aqui está o script](script3.py)
        - Bibliotécas datetime e boto3

- Aconpanhe os logs no CloudWatch e depois confira em Snapshots os backups criados.
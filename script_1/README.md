## Criação Automatizada de Instância EC2 com Função Lambada AWS

- Automação para gerar uma nova Instância EC2 com apenas um click
- Linguagem Python
- Intância gerada no teste
    - EC2 t2.micro

#

- Função Lambda
    - Create a new role with basic Lambda permissions
    - Runtime python 3.11
    - Configurations
        - Configure a lambda_function [aqui está o script](script1.py)
            - Bibliotécas os e boto3
                - `*boto3*` (SDK AWS) e `*os*` para ler as variaveis de ambiente na lambda_function.

- CloudWatch
    - IAM - Acesso a Instâncias EC2 - edit policy [aqui está o script](Script1+-+IAM+Role.txt)
        - Criando logs de Group, Stream, Events e EC2 Run Instances. Tera duas permissões a CloudWatch e EC2.

- Configure as variaveis de ambiente com os id "***(ami-...), (t2...),(key pairs-'name...'),(subnet-...)***" corretos de cada funcionalidade.

- Crie um evento de teste e rode o script para criar uma nova maquina.
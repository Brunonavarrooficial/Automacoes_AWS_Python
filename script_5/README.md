## DynamoDB - Backup - Lambda AWS

- Criação de Backup das tabelas do banco de dados DynamoDB
- Linguagem Python


#

- ### AWS Management Console
    - DynamoDB
        - Tables
            - Create Table - *Table name - Primary key*
            - Ttems
                - Create item *Items name*

    - função lambda
        - runtime python 3.7
        - create a new role with basic lambda permissions
        - permissions
            - roles
            - edit policy JSON - [aqui está o script](Script5+-+IAM+Rule.txt)
        - configuration
            - lambda_function - [aqui está o script](script5.py)
                - verifica as tabelas
                - cria o backup da tabela

    - cloudWatch
        - role
            - time-base - 8pm (segunda-sexta)
        - events
            - rules
                - create rule
                    - event source - schedule - fixed rate of 24 hours
                - targets
                    - função lambda (backup - dynamodb-"*table-name*")
                    - configure input
                        - constant(JSON text) - "*variable-name*" - {"key":"value"}

- aconpanhe os acontecimentos em CloudWatch e Log groups


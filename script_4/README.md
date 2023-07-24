## EC2 - Start/Stop

- Automação para iniciar e parar instâncias EC2
- Economia de uso de recursos
- Linguagem Python

#

### Parar Instâncias:
- CloudWatch
    - Role
        - time-base - 8pm (segunda-sexta)
    - Events
        - Rules
            - Create Rule
                - Event Source - Schedule - Cron Expression
                - 0 20 ? * MON-FRI * (seg-sex - 8pm)
            - Targets
                - Função Lambda (parar instâncias)
- Função Lambda
    - Runtime python 3.7
    - Create a new role with basic lambda permissions
    - Permissions
        - Roles
            - Edit Policy JSON - [aqui está o script](Script4+-+IAM+Role.txt)
    - Configuration
        - lambda_function - [aqui está o script](script4.py)
            - Listar todas regiões
            - Buscar todas regiões
            - Filtrar instâncias ligadas
            - Parar as instâncias
        - Clique em deploy

- Visualizar relatório nos Log Groups e CloudWatch

#

### Iniciar as Instâncias:

- Função Lambda
    - Runtime python 3.7
    - Create a new role with basic lambda permissions
    - Permissions
        - Roles
            - Edit Policy JSON - [aqui está o script](Script4+-+IAM+Role.txt)
    - Configuration
        - lambda_function - [aqui está o script](script4_start.py)
            - Listar todas regiões
            - Buscar todas regiões
            - Filtrar instâncias desligadas
            - Iniciar as instâncias
        - Clique em deploy
- CloudWatch
    - Role
        - time-base - 6am (segunda-sexta)
    - Events
        - Rules
            - Create Rule
                - Event Source - Schedule - Cron Expression
                - 0 6 ? * MON-FRI * - (seg-sex - 6am)
            - Targets
                - Função Lambda (iniciar instâncias)


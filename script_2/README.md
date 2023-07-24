## S3 Resize Versão Thumbnail

- trabalhando script para padronizar de forma automática um tamanho de dimensão especifico para uma imagem

- Onde o usuário manda uma imagem que é recebida pelo ***S3 bucket de origem*** e a função lambda com recursos de IAM e trigger patronizada com tamanho de 128x128 (Thumbnail) e envia para o ***S3 bucket de destino*** com CloudWatch monitorando.

#

- Criação de 2 buckets um de origem e o de destino
- criação de função lambda com novo script
    - Runtime Python 3.11
    - Create a new role with basic Lambda permissions IAM - edit policy [aqui esta o arquivo](Script2+-+IAM+Role.txt)
        - Get,Put, Logs e "Resource": "Buckets(origem-destino)"
    - Add Trigger S3 para Bucket-origem
    - configuration script [aqui está o arquivo](lambda_function.py)
        - blibliotécas: os, tempfile, boto3, e ***PIL import Image***
            - bibliotéca PIL não tem na Lambda AWS precisa fazer o download, caso precisar [aqui esta a pasta](./assets/docs/Archive/PIL/)
- Criação das váriaveis de ambiente dos buckets.
- Clique em deploy, faça o upload da imagem no bucket de origem
- Faça um refresh na bucket-destino e o arquivo irá convertido para lá.
- Caso quiser, confira todo o processo ocorrido em cloudWatch.
# RDS-DMS

Projeto de migração de dados de um banco de dados relacional para um bucket (representando a primeira camada de um data lake). O projeto é formado por um script python cuja função é carregar dados em um banco de dados Postgres, presente no Amazon RDS(Relational Database Service), uma tarefa de migração/replicação de dados do Amazon DMS(Database Migration Service) e um bucket no Amazon S3(Simple Storage Service).

O esquema do projeto pode ser visto na imagem a seguir:

<img  src = "https://github.com/LuccaFurtado/images/blob/main/rds-dms.png">

Primeiro foram criados o bucket no S3 e o banco de dados no RDS, como pode ser visto na próxima imagem:

<img src="https://user-images.githubusercontent.com/31989524/178646562-5e8cc0c6-1a3d-4a67-8ed4-dfbe190ddf81.png">

Na sequência, foi utilizado o [Script para inserção de dados](https://github.com/andresionek91/dms-insert-update/blob/master/insert.py), disponibilizado pelo [André Sionek](https://github.com/andresionek91)

Os últimos passos aconteceram no DMS na seguinte ordem: criação do Source Endpoint (banco de dados), do Target Endpoint (Bucket do S3), da Instância de replicação, além da tarefa de migração de banco de dados. A última pode ser vista na imagem a seguir: 

<img src = "https://github.com/LuccaFurtado/images/blob/main/aws-rds-dms.jpg">

Depois da execução da tarefa de migração, podemos visualizar os dados, no formato Parquet, presentes no bucket:


<img src="https://user-images.githubusercontent.com/31989524/178647955-18960aec-b39c-4595-8434-a8159d0c63e1.png">

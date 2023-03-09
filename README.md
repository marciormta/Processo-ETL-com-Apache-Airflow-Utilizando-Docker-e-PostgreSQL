# Processo-ETL-com-Apache-Airflow-Utilizando-Docker-e-PostgreSQL
Problema: Dada Uma base de dados CSV, erá necessário armazenar no PostgreSQL, Foi utilizado Cointainer e Apache Airflow para realizar a inclusão.
# Passos:
1 passo: Entender regra de negócio, modelar Criação de tabelas, e definir relacionamentos(Primary key/Foreign key).

2 passo: Criar um container no Docker com a instância do POSTGRESQL.(docker pull postgres), cria a imagem (docker run --name dbdsa -p 5433:5432 -e POSTGRES_USER=dsalabdw -e POSTGRES_PASSWORD=dsalabdw123 -e POSTGRES_DB=dwdb -d postgres)

3 passo: Conectar no PgAdmin(cria um servidor, depois cria um banco de dados com as informações do docker).

4 passo: no Pgadmin criar as tabelas do 1 passo. 

5 passo: criar a dag no apache airflow, a ideia é que temos dados em excel/csv e queremos incluí-los dentro do banco de dados, os nomes dos arquivos tem que ser iguais aos nomes das colunas no banco de dados

6 passo: no etl_dw.py, criamos uma dag com apache airflow para ler os dados da DIM_CLIENTE e armazenar no banco de dados, depois foi criado uma nova conexão no apache airflow para conectar com o docker, detalhe que na configuração do apache airflow o localhost deve-se preencher o ip do docker com os comandos (bash e ifconfig).

7 passo: feita a conexão no apache airflow, devemos colocar a dag para funcionar.

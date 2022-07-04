## First steps with Apache Airflow
Este repositório contém os códigos utilizados durante curso de Data Pipelines com Apache Airflow.
## 💻 Principais Tecnologias, Softwares e Bibliotecas
- Docker
- Python
- Apache AirFlow (Data Pipeline)
- Postgres
## ⚙ Instalação e configuração de ambiente
### Docker
  - Seguir a [documentação](https://docs.docker.com/engine/install/) oficial
### Apache AirFlow
  - Abra o terminal em sua pasta raiz para subir seu container com Airflow, dessa forma não perdemos os arquivos de DAGs gerados caso seja necessário algumas reinstalação ou configuração adiciona do container.
  - Rode o Seguinte comando em seu terminal:
    ```PowerShell
    docker run -d -p 8080:8080 -v "$PWD/airflow/dags:/opt/airflow/dags/" \
    --entrypoint=/bin/bash \
    --name airflow apache/airflow:2.1.1-python3.8 \
    -c '(\
    airflow db init && \
    airflow users create --username <nome de usuário> --password <sua senha> --firstname <Seu nome> --lastname <Seu Nome> --role Admin --email <Seu e-mail>); \
    airflow webserver & \
    airflow scheduler\
    '
    ```

  - Verificando o container em execução.
    ```powershell
    docker container ls
    ```
    
- Verificando os logs do container
  ```powershell
    docker container logs airflow
  ```
- Se nenhum erro aparecer, acesse a interface web do Apache Airflow pelo endereço:
  **https://localhost:8080**

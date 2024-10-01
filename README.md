# Projeto Infra EKS Terraform

Este projeto utiliza Terraform para gerenciar o serviço de EKS na AWS. Este projeto é responsável por implementar a infra do EKS e criar o cluster na AWS.

## Estrutura do Projeto

- `main.tf`: Arquivo contendo a definição dos recursos do EKS.
- `terraform.tf`: Arquivo principal contendo a definição dos recursos do Terraform.
- `variables.tf`: Arquivo responsável por armazenar as variáveis.
- `outputs.tf`: Arquivo que contém os outputs para montagem do EKS.
- `.github/workflows/`: Contém os workflows do GitHub Actions para CI/CD.

## Workflows do GitHub Actions

### `kubernets.yml`

Este workflow é acionado sempre que algum push é realizado na main.

## Variáveis de Ambiente no GitHub Actions

As seguintes vari�veis de ambiente podem ser configuradas no GitHub Actions:

Para acesso á AWS:
- `AWS_ACCESS_KEY_ID`: Key do IAM user que será utilizado.
- `AWS_SECRET_ACCESS_KEY`: Secret do IAM user que será utilizado.
- `AWS_DEFAULT_REGION`: Região da AWS em que os serviços serão implantados.

Terraform
- `TF_API_TOKEN`: Token de usuário do Terraform Cloud.

## Como Usar

1. Clone o repositório:
    ```sh
    git clone https://github.com/seu-usuario/seu-repositorio.git
    cd seu-repositorio
    ```

2. Configure as variáveis de ambiente necessárias:
    ```sh
    export AWS_ACCESS_KEY_ID=your_access_key_id
    export AWS_SECRET_ACCESS_KEY=your_secret_access_key
    export AWS_DEFAULT_REGION=your_default_region
    export TF_API_TOKEN=your_db_username
    ```

3. Inicialize o Terraform:
    ```sh
    terraform init
    ```

4. Selecione o workspace apropriado:
    ```sh
    terraform workspace select dev || terraform workspace new Kubernets_terraform_2
    ```

5. Aplique as mudanças:
    ```sh
    terraform apply -auto-approve
    ```

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.
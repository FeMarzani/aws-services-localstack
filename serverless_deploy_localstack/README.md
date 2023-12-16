# Demonstração de deploy no localstack utilizando Serverless Framework

### Principais Tecnologias Utilizadas:
<div align="center">
  <img align="center" alt="Git" height="28" width="42" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original.svg">
  <img align="center" alt="AWS" height="28" width="42" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/Amazon_Web_Services_Logo.svg/1024px-Amazon_Web_Services_Logo.svg.png" />
  <img align="center" alt="localstack" height="28" width="42" src="https://avatars.githubusercontent.com/u/28732122?s=200&v=4"/>
  <img align="center" alt="Serverless-framework" height="28" width="42" src="https://user-images.githubusercontent.com/2752551/30405068-a7733b34-989e-11e7-8f66-7badaf1373ed.png">
</div>

### Descrição:
- O localstack é uma poderosa ferramenta que permite simular serviços da AWS, sendo que a estrutura de código para sua utilização é praticamente igual aos utilizados para IaaC na AWS.

- É possível realizar deploys de infraestrutura em diversas formas, como por exemplo utilizando o Terraform ou o próprio Serverless Framework.

- O Serverless é formatado em um arquivo normalmente chamado de ```serverless.yml```. Com sua utilização, é possível realizar a criação de vários serviços da AWS, como:
    - Buckets do S3;
    - Filas SQS;
    - Definição de API Gateway;
    - Etc...

Nesta pasta específica deste repositório em questão, vamos ter um modelo de exemplo para realizar deploy via serverless framework utilizando o localstack, com suas respectivas informações para visualização do funcionamento.

### Como Utilizar:
- Sua utilização vai depender da etapa em que você se encontra. Para utilizar e realizar o deploy é necessário já ter o localstack com o docker e, além disso, o próprio serverless framework com o plugin do ```serverless-localstack```. Essas informações de como instalar o localstack vai ser possível encontrar na raiz do repositório ou direto na documentação do localstack..

- Você pode instalar o serverless utilizando o NPM:
    ```bash
    npm install -g serverless
    ```
- Você pode também instalar o plugin do serverless-localstack utilizando:
    ```bash
    serverless plugin install -n serverless-localstack
    ```
- Por fim, para realizar o deploy, esteja com o localstack em execução no docker:
    ```bash
    localstack start -d
    ```
    E depois execute:
    ```
    serverless deploy
    ```

### Visualização:
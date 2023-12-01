# Desenvolvimento de uma API Flask que suporta longas durações de processamento

### Tecnologias que serão utilizadas:
<div align="center">
  <img align="center" alt="Python" height="30" src="https://upload.wikimedia.org/wikipedia/commons/c/c3/Python-logo-notext.svg" />
  <img align="center" alt="Git" height="28" width="42" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original.svg">
  <img align="center" alt="AWS" height="28" width="42" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/Amazon_Web_Services_Logo.svg/1024px-Amazon_Web_Services_Logo.svg.png" />
  <img align="center" alt="localstack" height="28" width="42" src="https://avatars.githubusercontent.com/u/28732122?s=200&v=4"/>
  <img align="center" alt="Marzani-Flask" height="28" width="42" src="https://raw.githubusercontent.com/devicons/devicon/v2.15.1/icons/flask/flask-original-wordmark.svg">
  <img align="center" alt="Gunicorn" height="28" width="42" src="https://gunicorn.org/images/logo.jpg" />
  <img align="center" alt="Serverless-framework" height="28" width="42" src="https://user-images.githubusercontent.com/2752551/30405068-a7733b34-989e-11e7-8f66-7badaf1373ed.png">
</div>

### Descrição:
- API Flask com duas rotas não bloqueantes, sendo uma delas a `/health`, retornando o código http correto e a rota `/` para realizar o pooling de mensagens na fila de entrada.

- Será enviado um dicionário para a fila SQS, que por sua vez através de um listener para monitoramento, irá permitir a desserialização da mensagem e, respectivos processos, que no final salvará-se um arquivo em um bucket.

- Será utilizado:
    - 2 Buckets do S3:
        - Um para salvar arquivos de Scifi
        - Um para salvar arquivos de romance.

    - 1 Filas SQS do tipo FIFO:
        - InputQueue (Receberá as mensagens)

A mensagem irá conter:

```json
    {
     "id": "12345",
     "title": "LoremIpsum",
     "author": "John Doe",
     "year": "1960",
     "genre": "romance",
     "summary": "Lorem ipsum dolor sit amet, 
                 consectetur adipiscing elit,
                 sed do eiusmod tempor incididunt
                 ut labore et dolore magna aliqua."
    }
```

Sendo que:
- `title`: nome doo arquivo a ser salvo no bucket.
- `genre`: define qual bucket o arquivo será salvo.

- Será utilizado o Serverless Framework, com o plugin para o localstack, afim de subir a infraestrutura como código (criação das filas SQS e dos Buckets).
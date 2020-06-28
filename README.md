<img alt="GoStack" src="https://storage.googleapis.com/golden-wind/bootcamp-gostack/header-desafios.png" />

<h3 align="center">
  Desafio: Conceitos do React Native
</h3>


<p align="center">

  <img alt="GitHub language count" src="https://img.shields.io/github/languages/count/pauloabq/gostack-desafio-fundamentos-nodejs">

  <a href="https://rocketseat.com.br">
    <img alt="Made by Rocketseat" src="https://img.shields.io/badge/gostack%20bootcamp-Rocketseat-%237259c1">
  </a>

  <img alt="License" src="https://img.shields.io/github/license/pauloabq/gostack-desafio-fundamentos-nodejs">


</p>

<p align="center">
  <a href="#rocket-sobre-o-desafio">Sobre o desafio</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#rotas-da-aplicação">Rotas</a>
  &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-especificação-dos-testes">Especificação dos Testes</a>
  &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#instalação">Instalação</a>
  &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#testar">Testar</a>
  &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#memo-licença">Licença</a>

</p>

## :rocket: Sobre o desafio

Nesse desafio, você deve criar uma aplicação para continuar treinando o que você aprendeu até agora no **Node.js** junto ao **TypeScript**, utilizando o conceito de **models**, **repositories** e **services**!

Essa será uma aplicação para armazenar transações financeiras de entrada e saída, que deve permitir o cadastro e a listagem dessas transações.


### Rotas da aplicação


- **`POST /transactions`**: A rota deve receber `title`, `value` e `type` dentro do corpo da requisição, sendo `type` o tipo da transação, que deve ser `income` para entradas (depósitos) e `outcome` para saídas (retiradas). Ao cadastrar uma nova transação, ela deve ser armazenada dentro de um objeto com o seguinte formato :

```json
{
  "id": "uuid",
  "title": "Salário",
  "value": 3000,
  "type": "income"
}
```

- **`GET /transactions`**: Essa rota deve retornar uma listagem com todas as transações que você cadastrou até agora, junto com o valor de soma de entradas, retiradas e total de crédito. Essa rota deve retornar um objeto com o formato a seguir:

```json
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Salário",
      "value": 4000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Freela",
      "value": 2000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Pagamento da fatura",
      "value": 4000,
      "type": "outcome"
    },
    {
      "id": "uuid",
      "title": "Cadeira Gamer",
      "value": 1200,
      "type": "outcome"
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

**Dica**: Dentro de balance, o income é a soma de todos os valores das transações com `type` income. O outcome é a soma de todos os valores das transações com `type` outcome, e o total é o valor de `income - outcome`.

**Dica 2**: Para fazer a soma dos valores, você pode usar a função [reduce](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) para agrupar as transações pela propriedade `type`, assim você irá conseguir somar todos os valores com facilidade e obter o retorno do `balance`.

### Especificação dos testes

Em cada teste, tem uma breve descrição no que sua aplicação deve cumprir para que o teste passe.

Para esse desafio temos os seguintes testes:

- **`should be able to create a new transaction`**: Para que esse teste passe, sua aplicação deve permitir que uma transação seja criada, e retorne um json com a transação criada.

- **`should be able to list the transactions`**: Para que esse teste passe, sua aplicação deve permitir que seja retornado um objeto contendo todas as transações junto ao balanço de income, outcome e total das transações que foram criadas até o momento.

- **`should not be able to create outcome transaction without a valid balance`**: Para que esse teste passe, sua aplicação não deve permitir que uma transação do tipo `outcome` extrapole o valor total que o usuário tem em caixa, retornando uma resposta com código HTTP 400 e uma mensagem de erro no seguinte formato: `{ error: string }`


Em cada teste, tem uma breve descrição no que sua aplicação deve cumprir para que o teste passe.


### Instalação

#### 1. Obter os arquivos

```bash
$ git clone https://github.com/pauloabq/gostack-desafio-fundamentos-nodejs

```
#### 2. Instalar as dependências

Executar o comando no diretório do projeto clonado para instalar as dependências

```bash
$ yarn
```
ou

```bash
$ npm install
```
#### 3. Iniciar servidor back-end NodeJS

```
$ yarn dev:server
```
ou
```
$ npm run dev:server
```



### Testar

```bash
$ yarn test
```

### :memo: Licença

Esse projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

Criado por <strong>Paulo Albuquerque</strong>

[![Twitter][twitter-shield]][twitter-url] [![LinkedIn][linkedin-shield]][linkedin-url] [![GitHub][github-profile-shield]][github-profile-url]


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[license-shield]: https://img.shields.io/github/license/pauloabq/gostack-desafio-fundamentos-nodejs
[license-url]: https://github.com/pauloabq/gostack-desafio-fundamentos-nodejs/LICENSE

[twitter-shield]: https://img.shields.io/badge/-twitter-black.svg?style=flat-square&logo=twitter&colorB=555
[twitter-url]: http://twitter.com/pauloabq

[github-profile-shield]: https://img.shields.io/badge/-Github-black?style=flat-square&logo=github&colorB=555
[github-profile-url]: http://github.com/pauloabq

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/pauloabq


[github-lang-shield]: https://img.shields.io/github/languages/count/pauloabq/gostack-desafio-fundamentos-nodejs
[github-lang-url]: http://github.com/pauloabq

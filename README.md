# Desafio-03 Corrigindo o Código

<img src="https://camo.githubusercontent.com/f8ff62d08386208c02ec61d2a533821f3a805cc6359a50a0b83573a3e4c9963c/68747470733a2f2f7777772e6e6f74696f6e2e736f2f696d6167652f687474707325334125324625324673332d75732d776573742d322e616d617a6f6e6177732e636f6d2532467365637572652e6e6f74696f6e2d7374617469632e636f6d25324661643031656537392d373632612d343737352d626262362d333534663266343238373961253246636f7665722d6e6f64652e6a732e706e673f7461626c653d626c6f636b2669643d35396363623233352d616563642d343361362d613036622d6630396132346537656465382677696474683d33383430267573657249643d62623639633032362d346533382d343565652d623166612d3466346339623035393431312663616368653d7632" />
          
Nesse desafio, temos uma aplicação Node.js que está em processo de desenvolvimento mas que já possui os testes necessários para fazer toda a validação dos requisitos (você não deve mexer nos testes).

# 💻 Sobre o desafio

Nesse desafio, temos uma aplicação Node.js que está em processo de desenvolvimento mas que já possui os testes necessários para fazer toda a validação dos requisitos (você não deve mexer nos testes).
Após algumas alterações no código da aplicação, parte dos testes deixaram de passar e agora só você pode resolver esse problema. Bora lá? 🚀

Essa aplicação realiza o CRUD (**C**reate, **R**ead, **U**pdate, **D**elete) de repositórios de projetos. Além disso, é possível dar likes em repositórios cadastrados, aumentando a quantidade de likes em 1 a cada vez que a rota é chamada.

A estrutura de um repositório ao ser criado é a seguinte:

```jsx
{
  id: uuid(),
  title,
  url,
  techs,
  likes: 0
}
```

Descrição de cada propriedade:

- **id** deve ser um uuid válido;
- **title** é o título do repositório (por exemplo "unform");
- **url** é a URL que aponta para o repositório (por exemplo "[https://github.com/unform/unform](https://github.com/unform/unform)");
- **techs** é um array onde cada elemento deve ser uma string com o nome de uma tecnologia relacionada ao repositório (por exemplo: ["react", "react-native", "form"]);
- **likes** é a quantidade de likes que o repositório recebeu (e que vai ser incrementada de 1 em 1 a cada chamada na rota de likes).

Note que a quantidade de likes deve sempre ser zero no momento de criação.

## Template da aplicação

Para te ajudar nesse desafio, criamos para você esse modelo que você deve utilizar como um template do GitHub.

O template está disponível na seguinte URL:

https://github.com/rocketseat-education/ignite-template-corrigindo-o-codigo

**Dica**: Caso não saiba utilizar repositórios do GitHub como template, temos um guia em **[nosso FAQ](https://www.notion.so/FAQ-Desafios-ddd8fcdf2339436a816a0d9e45767664).**

Agora navegue até a pasta criada, abra no Visual Studio Code e por último abra o arquivo `index.js`. Lembre-se de executar o comando `yarn` no seu terminal para instalar todas as dependências e você terá o seguinte código:

<img src="https://camo.githubusercontent.com/b1ae85e95b82182e34db4a48d9c65d0a4c56bad1e33047c7a0dae90cd49c1874/68747470733a2f2f7777772e6e6f74696f6e2e736f2f696d6167652f687474707325334125324625324673332d75732d776573742d322e616d617a6f6e6177732e636f6d2532467365637572652e6e6f74696f6e2d7374617469632e636f6d25324639663830333265392d643435392d346336662d613630662d643863393066643962633561253246556e7469746c65642e706e673f7461626c653d626c6f636b2669643d32346661666332642d663364392d346634352d613564352d3635333161383763323065372677696474683d31383230267573657249643d62623639633032362d346533382d343565652d623166612d3466346339623035393431312663616368653d7632" />

## Rotas da aplicação

Com o template já clonado e o arquivo `index.js` aberto, você deve completar onde não possui código com o código para atingir os objetivos de cada teste.

### GET `/repositories`

A rota deve retornar uma lista contendo todos os repositórios cadastrados.

### POST `/repositories`

A rota deve receber `title`, `url` e `techs` pelo corpo da requisição e retornar um objeto com as informações do repositório criado e um status `201`.

### PUT `/repositories/:id`

A rota deve receber `title`, `url` e `techs` pelo corpo da requisição e o `id` do repositório que deve ser atualizado pelo parâmetro da rota. Deve alterar apenas as informações recebidas pelo corpo da requisição e retornar esse repositório atualizado.

### DELETE `/repositories/:id`

A rota deve receber, pelo parâmetro da rota, o `id` do repositório que deve ser excluído e retornar um status `204` após a exclusão.

### POST `/repositories/:id/like`

A rota deve receber, pelo parâmetro da rota, o `id` do repositório que deve receber o like e retornar o repositório com a quantidade de likes atualizada.

## Específicação dos testes

Em cada teste, tem uma breve descrição no que sua aplicação deve cumprir para que o teste passe.

Note que partes da aplicação já estão prontas e você precisará alterar apenas o que está errado (ou implementar algo que esteja faltando). 

Se você achou algum trecho de código confuso ou pensou em uma melhor solução, sinta-se livre para também refatorar.

Caso você tenha dúvidas quanto ao que são os testes, e como interpretá-los, dê uma olhada em **[nosso FAQ](https://www.notion.so/FAQ-Desafios-ddd8fcdf2339436a816a0d9e45767664)**

Para esse desafio, temos os seguintes testes:

### Testes de repositórios

- **Should be able to create a new repository**

Para que esse teste passe, você deve permitir que um novo repositório seja cadastrado pela rota **POST** `/repositories`. Caso precise confirmar o formato do objeto, você pode olhar [aqui.](https://www.notion.so/Desafio-03-Corrigindo-o-c-digo-c15c8a2e212846039a367cc7b763c6dd) 

Também é necessário que você retorne a resposta com o código `201`.

- **Should be able to list the projects**

Para que esse teste passe, é necessário que você conclua o teste anterior. Se tudo ocorreu bem, os repositórios cadastrados deverão aparecerem na listagem da rota **GET** `/repositories` e esse teste irá passar.

- **Should be able to update repository**

Para que esse teste passe, você deve permitir que um repositório seja atualizado a partir de seu `id` pela rota **PUT** `/repositories/:id` usando as [informações recebidas pelo corpo da requisição](https://www.notion.so/Desafio-03-Corrigindo-o-c-digo-c15c8a2e212846039a367cc7b763c6dd). Lembre-se de manter as informações que não foram passadas pelo corpo, por exemplo:
Se o usuário quiser trocar apenas o `title`, mantenha `url` e `techs` que já estavam no repositório.

- **Should not be able to update a non existing repository**

Para que esse teste passe, você deve verificar se o repositório existe antes de atualizar as informações na rota **PUT** `/repositories/:id`. Caso não exista, retorne um status `404` (que é o status para **Not Found**) com uma mensagem de erro no formato `{ error: "Mensagem do erro" }`.

- **Should not be able to update repository likes manually**

Para que esse teste passe, você deve impedir que a quantidade de likes de um repositório seja alterada manualmente através da rota **PUT** `/repositories/:id`.
Por exemplo:

ERRADO:
```jsx
// Repositório recém criado:
{
	id: "c160a99b-9d3b-4669-8a35-8dce1e8196ec",
	title: "Umbriel",
	techs: ["React", "ReactNative", "TypeScript", "ContextApi"],
	url: "https://github.com/Rocketseat/umbriel",
	likes: 0
}

// Requisição para alterar informações: 
// Rota: "/repositories/c160a99b-9d3b-4669-8a35-8dce1e8196ec"
// Método: PUT
// Corpo: { title: "Novo título", likes: 10 }

// Retorno:

{
	id: "c160a99b-9d3b-4669-8a35-8dce1e8196ec",
	title: "Novo título",
	techs: ["React", "ReactNative", "TypeScript", "ContextApi"],
	url: "https://github.com/Rocketseat/umbriel",
	likes: 10
}
```

```jsx
CERTO:

// Repositório recém criado:
{
	id: "c160a99b-9d3b-4669-8a35-8dce1e8196ec",
	title: "Umbriel",
	techs: ["React", "ReactNative", "TypeScript", "ContextApi"],
	url: "https://github.com/Rocketseat/umbriel",
	likes: 0
}

// Requisição para alterar informações: 
// Rota: "/repositories/c160a99b-9d3b-4669-8a35-8dce1e8196ec"
// Método: PUT
// Corpo: { title: "Novo título", likes: 10 }

// Retorno:

{
	id: "c160a99b-9d3b-4669-8a35-8dce1e8196ec",
	title: "Novo título",
	techs: ["React", "ReactNative", "TypeScript", "ContextApi"],
	url: "https://github.com/Rocketseat/umbriel",
	likes: 0 // A quantidade de likes não mudou
}

```

- **Should be able to delete the repository**

Para que esse teste passe, você deve permitir que um repositório seja excluído através do `id` passado pela rota **DELETE** `/repositories/:id`.

- **Should not be able to delete a non existing repository**

Para que esse teste passe, você deve validar se o repositório existe antes de excluí-lo. Caso o repositório não exista, retorne um status `404` com uma mensagem de erro no formato 

```jsx
`{ error: "Mensagem do erro" }`.

```

### Testes de likes

- **Should be able to give a like to the repository**

Para que esse teste passe, deve ser possível incrementar a quantidade de likes em `1` a cada chamada na rota **POST** `/repositories/:id/like`. Use o `id` passado por parâmetro na rota para realizar essa ação.

- **Should not be able to give a like to a non existing repository**

Para que esse teste passe, você deve validar que um repositório existe antes de incrementar a quantidade de likes. Caso não exista, retorne um status `404` com uma mensagem de erro no formato 

```jsx
`{ error: "Mensagem do erro" }`.

```

Todos os demais testes são os mesmos testes encontrados no desafio 01 com algumas (ou nenhuma) mudanças.

Após todo código pronto e acertado de acordo com o teste vamos obter o seguinte resultado abaixo:

<img src="https://github.com/LucasRGarcias/Desafio-03-Corrigindo-codigo/blob/main/src/imgs/Codigo%20testado.png" />

Feito com 💜 por Rocketseat e praticado no curso Ignite trila NodeJS👋


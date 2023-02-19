# Poke Rest API

![Descrição da imagem](https://raw.githubusercontent.com/MarcioBADias/poke-rest-api/main/public/assets/img/png_20230219_005604_0000.png)


## Desafio

Construir uma aplicação para listagem e busca de pokemons utilizando a PokeAPI v2. A aplicação consiste em uma tela com um campo de busca centralizado que, ao ser acionado com o nome do pokémon, submete a pesquisa para a PokeAPI e retorna as informações do pokémon buscado e de suas evoluções (Evolution Chains). Para cada um dos pokémons listados, queremos ver seu nome e sua imagem.

Ao clicarmos em um pokémon listado, queremos listar suas principais características (hp, attack, defense, special attack, special defense e speed), utilizando princípios básicos de UI/UX.

## Componentes

A aplicação é dividida em três componentes:

- **Lista de Cards**: responsável por listar os cards dos pokémons, vindo da API.
- **Filtro**: componente que configura o input para fazer um filtro na lista de cards.
- **Destaque**: responsável por destacar o card clicado.

## Desafios

Este foi o meu primeiro projeto usando Vue-JS visando consumo de API. Minha maior dificuldade foi me acostumar com a sintaxe do Framework, mas graças à minha prática no JavaScript consegui superar essa barreira e entregar a página. Fiquei muito satisfeito em ver o desenvolvimento no responsivo e as chamadas funcionando no script.

## Deploy

Este projeto está disponível em produção em https://poke-rest-api.netlify.app/

## Como Executar

Para executar a aplicação, siga os seguintes passos:

1. Clone o repositório `git clone https://github.com/seu-usuario/poke-rest-api.git`
2. Entre no diretório do projeto `cd poke-rest-api`
3. Instale as dependências `npm install`
4. Execute a aplicação `npm run serve`
5. Acesse a aplicação em `http://localhost:8080/`

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

## Contato

Caso tenha dúvidas, sugestões ou queira entrar em contato, envie um e-mail para `seu-email@provedor.com`. Você também pode me encontrar no LinkedIn em [linkedin.com/in/marciobadias](https://www.linkedin.com/in/marciobadias/).

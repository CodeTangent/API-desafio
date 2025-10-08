# Sistema de Hospedagem em C#

## Visão Geral
O sistema permite registrar hóspedes, gerenciar suítes e calcular reservas automaticamente, incluindo validação de capacidade e aplicação de descontos progressivos para estadias longas. Desenvolvido como parte da Trilha .NET da DIO.

## Funcionalidades Principais
- Cadastro de hóspedes (classe Pessoa)  
- Cadastro de suítes (classe Suite, com tipo e capacidade)  
- Reserva de quartos (classe Reserva, integrando hóspedes e suíte)  
- Cálculo automático do valor da diária  
- Desconto de 10% para reservas com duração igual ou superior a 10 dias  
- Validação de capacidade: impede reservas com número de hóspedes superior à capacidade da suíte  
- Métodos para obter quantidade de hóspedes e valor total da reserva  

## Conceitos Aplicados
- Programação Orientada a Objetos (POO)  
- Encapsulamento e abstração de classes  
- Validação de dados e tratamento de exceções  
- Boas práticas de nomeação e estrutura de código  


---

# Sistema de Banco de Dados de Filmes

## Visão Geral
O sistema permite realizar consultas SQL em um banco de dados de filmes, atores e gêneros, extraindo informações relevantes para análises. Desenvolvido como parte da Trilha .NET da DIO, o projeto foca na prática de consultas, relacionamentos e manipulação de dados.

## Funcionalidades Principais
- Estruturação de banco de dados com tabelas para Filmes, Atores e Gêneros  
- Relacionamentos muitos-para-muitos entre filmes-atores e filmes-gêneros  
- Execução de 12 consultas SQL diferentes para retorno de dados específicos:  
  - Listagem de filmes por nome, ano e duração  
  - Filtros por ano e duração  
  - Contagem de filmes por ano  
  - Listagem de atores por gênero  
  - Relação de filmes com gêneros  
  - Associação de filmes com atores e papéis  

## Conceitos Aplicados
- Modelagem de banco de dados relacional  
- Consultas SQL com filtros, ordenações e agrupamentos  
- Relacionamentos muitos-para-muitos  
- Validação e integridade de dados  

## Preparando o Banco
- Executar o script **Script Filmes.sql** no SQL Server (localizado na pasta `Scripts`)  
- O script cria o banco **Filmes** com todas as tabelas e dados necessários para as consultas  


---

# Sistema de Testes Unitários em C#

## Visão Geral
Este projeto aplica testes unitários em um sistema C# para garantir a qualidade e confiabilidade do código. Desenvolvido como parte da Trilha .NET da DIO, o projeto foca na implementação de testes usando xUnit, cobrindo cenários positivos e negativos.

## Funcionalidades Principais
- Implementação de testes unitários para validações de listas e strings  
- Cobertura de cenários positivos e negativos  
- Identificação e prevenção de regressões no sistema  
- Execução de testes automatizados com **xUnit**  

## Classes e Métodos do Projeto Console

**Classe ValidacoesLista** – realiza validações em listas de inteiros:

| Método                       | Objetivo                                                                                                                |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| RemoverNumerosNegativos      | Retorna uma nova lista contendo apenas números positivos                                                               |
| ListaContemDeterminadoNumero | Verifica se um determinado número está presente na lista                                                               |
| MultiplicarNumerosLista      | Retorna uma nova lista com os elementos multiplicados por um número específico                                        |
| RetornarMaiorNumeroLista     | Retorna o maior número da lista                                                                                         |
| RetornarMenorNumeroLista     | Retorna o menor número da lista                                                                                         |

**Classe ValidacoesString** – realiza validações em strings:

| Método                       | Objetivo                                                                                                                |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| RetornarQuantidadeCaracteres | Retorna a quantidade de caracteres em um texto                                                                         |
| ContemCaractere              | Retorna verdadeiro ou falso se um trecho específico está presente no texto                                             |
| TextoTerminaCom              | Retorna verdadeiro ou falso se o texto termina com um trecho específico                                               |

## Classes e Métodos do Projeto de Teste

**ValidacoesListaTests** – testa a classe `ValidacoesLista`:

| Método de teste                               | Resultado esperado                                                                                          |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| DeveRemoverNumerosNegativosDeUmaLista         | Retorna apenas os números positivos da lista                                                              |
| DeveConterONumero9NaLista                     | Retorna verdadeiro se o número 9 estiver presente                                                         |
| NaoDeveConterONumero10NaLista                 | Retorna falso se o número 10 não estiver presente                                                         |
| DeveMultiplicarOsElementosDaListaPor2         | Retorna a lista com todos os elementos multiplicados por 2                                                |
| DeveRetornar9ComoMaiorNumeroDaLista           | Retorna o maior número da lista (9 neste caso)                                                            |
| DeveRetornarOitoNegativoComoMenorNumeroDaList | Retorna o menor número da lista (-8 neste caso)                                                           |

**ValidacoesStringTests** – testa a classe `ValidacoesString`:

| Método de teste                                  | Resultado esperado                                                                                       |
|-------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| DeveRetornar6QuantidadeCaracteresDaPalavraMatrix | Retorna 6 ao passar o texto "Matrix"                                                                    |
| DeveContemAPalavraQualquerNoTexto                | Retorna verdadeiro se a palavra "qualquer" estiver presente                                             |
| NaoDeveConterAPalavraTesteNoTexto               | Retorna falso se a palavra "teste" não estiver presente                                                 |
| TextoDeveTerminarComAPalavraProcurado           | Retorna verdadeiro se o texto termina com a palavra "procurado"                                         |

## Estrutura do Projeto
O projeto está organizado em dois projetos principais:  

- Projeto Console – contém as classes e métodos de validação  
- Projeto de Teste (xUnit) – contém os testes unitários a serem implementados  

![Estrutura do Projeto](Imagens/projeto.png)

## Solução
Os testes estão parcialmente implementados. Para concluir o projeto, implemente os métodos comentados com "TODO", garantindo que todos os testes descritos acima funcionem corretamente.


---

# Sistema de Gerenciamento de Tarefas com API e Entity Framework

## Visão Geral
Este projeto permite gerenciar uma lista de tarefas utilizando uma Web API em C# com Entity Framework. Desenvolvido como parte da Trilha .NET da DIO, o sistema implementa operações CRUD para organizar e controlar tarefas de forma eficiente.

## Funcionalidades Principais
- Cadastro de tarefas (Create)  
- Obtenção de tarefas individuais ou todas as tarefas (Read)  
- Atualização de tarefas existentes (Update)  
- Exclusão de tarefas (Delete)  
- Filtros de tarefas por título, data ou status  
- Integração com banco de dados via Entity Framework  
- Documentação de endpoints via Swagger  

## Classe Principal: Tarefa
O sistema utiliza a classe `Tarefa` como modelo principal para representar uma tarefa:

json
{
  "id": 0,
  "titulo": "string",
  "descricao": "string",
  "data": "2022-06-08T01:31:07.056Z",
  "status": "Pendente"
}

Endpoints da API
Verbo	Endpoint	Parâmetro	Body
GET	/Tarefa/{id}	id	N/A
PUT	/Tarefa/{id}	id	Schema Tarefa
DELETE	/Tarefa/{id}	id	N/A
GET	/Tarefa/ObterTodos	N/A	N/A
GET	/Tarefa/ObterPorTitulo	titulo	N/A
GET	/Tarefa/ObterPorData	data	N/A
GET	/Tarefa/ObterPorStatus	status	N/A
POST	/Tarefa	N/A	Schema Tarefa
Conceitos Aplicados

Web API com ASP.NET Core

Entity Framework para persistência de dados

Operações CRUD

Filtros e consultas por parâmetros

Documentação de API com Swagger

Preparando o Projeto

Crie a migration e atualize o banco de dados usando Entity Framework

Execute a aplicação e teste os endpoints utilizando Swagger ou outra ferramenta de sua preferência

Detalhe:

O código está parcialmente implementado. Para concluir o projeto, implemente os métodos comentados com "TODO" garantindo que todas as operações CRUD e filtros funcionem corretamente.


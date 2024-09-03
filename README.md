# Sistema de Gerenciamento de Biblioteca

Este projeto consiste na criação de um sistema de gerenciamento para uma biblioteca, permitindo organizar e acompanhar os livros disponíveis, os autores, e os empréstimos realizados. O objetivo é desenvolver um banco de dados funcional que facilite a administração dos recursos da biblioteca e a interação com os usuários.

## Descrição do Projeto

O sistema de gerenciamento de biblioteca foi desenvolvido utilizando comandos SQL para criar e manipular dados. Ele permite:

- Inserir informações de autores, livros e empréstimos.
- Consultar dados, como listar livros com seus autores, e verificar empréstimos pendentes.
- Atualizar dados, como modificar a data de devolução de um empréstimo.
- Deletar registros, como remover livros e empréstimos associados.

## Estrutura do Banco de Dados

O banco de dados `Biblioteca` contém as seguintes tabelas:

- **Autores**: Armazena informações sobre os autores, como ID, nome e nacionalidade.
- **Livros**: Armazena informações sobre os livros, incluindo ID, título, ID do autor, ano de publicação e gênero.
- **Empréstimos**: Armazena informações sobre os empréstimos realizados, como ID do empréstimo, ID do livro, data de empréstimo, data de devolução e nome do usuário.

## Pré-requisitos

Antes de executar este projeto, certifique-se de ter:

- MySQL instalado em sua máquina.
- Acesso a um cliente MySQL, como MySQL Workbench ou terminal MySQL.

## Instruções de Configuração

Siga os passos abaixo para configurar o banco de dados:

1. **Clonar o repositório**:

    ```bash
    git clone <URL_DO_REPOSITORIO>
    cd <NOME_DO_DIRETORIO>
    ```

2. **Abrir o script SQL**:

   Abra o arquivo `biblioteca.sql` em seu cliente MySQL preferido.

3. **Executar o script SQL**:

   Execute o script para criar o banco de dados, tabelas e inserir os dados iniciais.

## Funcionalidades Implementadas

- **Criação do Banco de Dados**: Criação do banco de dados `Biblioteca` e suas tabelas: `Autores`, `Livros` e `Empréstimos`.
- **Inserção de Dados**: Inserção de registros de autores, livros e empréstimos.
- **Consultas de Dados**:
  - Listar todos os livros junto com o nome do autor e o ano de publicação.
  - Mostrar todos os empréstimos que ainda não foram devolvidos.
- **Atualização de Dados**: Atualizar a data de devolução de um empréstimo específico.
- **Exclusão de Dados**: Remover um livro e todos os registros relacionados a ele na tabela de empréstimos.

## Exemplos de Uso

1. **Listar todos os livros com os nomes de seus autores:**

    ```sql
    SELECT Livros.Titulo, Autores.Nome AS Autor, Livros.AnoPublicacao
    FROM Livros
    JOIN Autores ON Livros.AutorID = Autores.AutorID;
    ```

2. **Listar os empréstimos que ainda estão em aberto:**

    ```sql
    SELECT Emprestimos.EmprestimoID, Livros.Titulo, Emprestimos.DataEmprestimo, Emprestimos.NomeUsuario
    FROM Emprestimos
    JOIN Livros ON Emprestimos.LivroID = Livros.LivroID
    WHERE Emprestimos.DataDevolucao IS NULL;
    ```

## Contato

Para mais informações, entre em contato pelo e-mail: [seuemail@exemplo.com].

## Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

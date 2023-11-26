# Sistema de Gerenciamento de Matrículas em Cursos

Este é um conjunto de scripts SQL e procedimentos armazenados para um sistema simples de gerenciamento de matrículas em cursos, utilizando um banco de dados relacional.

## Estrutura do Banco de Dados

O banco de dados consiste em quatro tabelas principais:

### Tabela `Areas`

Armazena informações sobre as áreas de estudo disponíveis.
- `ID_Area`: Identificador único da área.
- `Nome_Area`: Nome da área de estudo.

### Tabela `Cursos`

Registra os cursos disponíveis, associados a uma área específica.
- `ID_Curso`: Identificador único do curso.
- `Nome_Curso`: Nome do curso.
- `ID_Area`: Chave estrangeira referenciando a tabela `Areas`.

### Tabela `Alunos`

Mantém informações sobre os alunos.
- `ID_Aluno`: Identificador único do aluno.
- `Nome`: Nome do aluno.
- `Sobrenome`: Sobrenome do aluno.
- `Email`: Endereço de e-mail do aluno.

### Tabela `Matriculas`

Registra as matrículas dos alunos nos cursos.
- `ID_Matricula`: Identificador único da matrícula.
- `ID_Aluno`: Chave estrangeira referenciando a tabela `Alunos`.
- `ID_Curso`: Chave estrangeira referenciando a tabela `Cursos`.
- `Data_Matricula`: Data de matrícula (preenchida automaticamente com a data atual).

## Inserção de Dados de Exemplo

Foram inseridos dados de exemplo nas tabelas `Areas`, `Cursos`, `Alunos` e `Matriculas` para ilustrar o funcionamento do sistema.

## Stored Procedures e Funções

### Procedure `InserirCurso`

Permite a inserção de um novo curso no banco de dados.
- Parâmetros: `p_Nome_Curso` (Nome do curso a ser inserido) e `p_ID_Area` (ID da área associada ao curso).

### Function `BuscarIDCurso`

Busca o ID de um curso com base no nome do curso e nome da área.
- Parâmetros: `p_Nome_Curso` (Nome do curso a ser buscado) e `p_Nome_Area` (Nome da área do curso).
- Retorna: ID do curso correspondente ou NULL se não encontrado.

### Procedure `MatricularAluno`

Realiza a matrícula de um aluno em um curso específico.
- Parâmetros: `p_ID_Aluno` (ID do aluno), `p_Nome_Curso` (Nome do curso) e `p_Nome_Area` (Nome da área do curso).

## Como Utilizar

Os procedimentos e funções podem ser chamados para inserir cursos, buscar IDs de cursos e matricular alunos em cursos existentes. Certifique-se de inserir os dados corretamente e seguir as restrições definidas nas tabelas para evitar erros.

---

Este sistema é um exemplo simplificado e pode ser expandido com mais funcionalidades e validações de acordo com as necessidades do usuário.
![image](https://github.com/SamuelJorgetto/Function-Universidade/assets/144075081/86b7f85d-c9a8-4ebc-8708-b73c5ac15768)


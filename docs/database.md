# Documentação do Banco de Dados :floppy_disk:

## [Prisma ORM :crystal_ball:](prisma.md)

## Modelos :page_facing_up:

### Biblioteca

- Tabela: `Biblioteca`
- Descrição: Representa uma biblioteca.
- Campos:
  - `id`: Identificador único da biblioteca (tipo: Inteiro).
  - `nome`: Nome da biblioteca (tipo: String).
  - `status`: Status da biblioteca, com valores "ATIVO" ou "INATIVO" (tipo: Enum `StatusDefault`).
  - `createdAt`: Data de criação do registro (tipo: DateTime).
  - `updatedAt`: Data de atualização do registro (tipo: DateTime).
  - `contatoId`: Identificador único do contato associado à biblioteca (tipo: Inteiro).
  - `enderecoId`: Identificador único do endereço associado à biblioteca (tipo: Inteiro).
- Relações:
  - `Contato`: Relação com o modelo `Contato`, associada ao campo `contatoId`.
  - `Endereco`: Relação com o modelo `Endereco`, associada ao campo `enderecoId`.
  - `configBiblioteca`: Relação com o modelo `configBiblioteca`, associada ao campo `configBibliotecaId`.
  - `Autor`: Relação com o modelo `Autor`, representando os autores associados à biblioteca.
  - `Lingua`: Relação com o modelo `Lingua`, representando as línguas associadas à biblioteca.
  - `Categoria`: Relação com o modelo `Categoria`, representando as categorias associadas à biblioteca.
  - `Estoque`: Relação com o modelo `Estoque`, representando os estoques associados à biblioteca.
  - `Emprestimo`: Relação com o modelo `Emprestimo`, representando os empréstimos associados à biblioteca.
  - `Notificacao`: Relação com o modelo `Notificacao`, representando as notificações associadas à biblioteca.
  - `Multas`: Relação com o modelo `Multas`, representando as multas associadas à biblioteca.
  - `livros`: Relação com o modelo `Livro`, representando os livros associados à biblioteca.
  - `usuarios`: Relação com o modelo `Usuario`, representando os usuários associados à biblioteca.

### configBiblioteca

- Tabela: `configBiblioteca`
- Descrição: Representa a configuração de uma biblioteca.
- Campos:
  - `id`: Identificador único da configuração da biblioteca (tipo: Inteiro).
  - `createdAt`: Data de criação do registro (tipo: DateTime).
  - `updatedAt`: Data de atualização do registro (tipo: DateTime).
  - `valorMulta`: Valor da multa associada à biblioteca (tipo: Inteiro).
  - `bibliotecaId`: Identificador único da biblioteca associada à configuração (tipo: Inteiro).
- Relações:
  - `Biblioteca`: Relação com o modelo `Biblioteca`, associada ao campo `bibliotecaId`.

### Livro

- Tabela: `Livro`
- Descrição: Representa um livro.
- Campos:
  - `id`: Identificador único do livro (tipo: Inteiro).
  - `createdAt`: Data de criação do registro (tipo: DateTime).
  - `updatedAt`: Data de

atualização do registro (tipo: DateTime).

- `idInterno`: Identificador interno do livro (tipo: Inteiro).
- `titulo`: Título do livro (tipo: String).
- `isbn`: ISBN do livro (tipo: String).
- `ano_pub`: Ano de publicação do livro (tipo: Inteiro).
- `tombo`: Tombo do livro (tipo: String).
- `posicao`: Posição do livro na biblioteca (tipo: String).
- `cdd`: Classificação Decimal de Dewey (CDD) do livro (tipo: String).
- `status`: Status do livro, com valores "ATIVO" ou "INATIVO" (tipo: Enum `StatusDefault`).
- `edicao`: Edição do livro (tipo: String).
- `estoqueId`: Identificador único do estoque associado ao livro (tipo: Inteiro).
- `bibliotecaId`: Identificador único da biblioteca associada ao livro (tipo: Inteiro).
- `categoriaId`: Identificador único da categoria associada ao livro (tipo: Inteiro, opcional).
- `linguaId`: Identificador único da língua associada ao livro (tipo: Inteiro, opcional).
- `autorId`: Identificador único do autor associado ao livro (tipo: Inteiro, opcional).
- Relações:
  - `biblioteca`: Relação com o modelo `Biblioteca`, associada ao campo `bibliotecaId`.
  - `Estoque`: Relação com o modelo `Estoque`, associada ao campo `estoqueId`.
  - `Categoria`: Relação com o modelo `Categoria`, associada ao campo `categoriaId`.
  - `Lingua`: Relação com o modelo `Lingua`, associada ao campo `linguaId`.
  - `Autor`: Relação com o modelo `Autor`, associada ao campo `autorId`.
  - `Multas`: Relação com o modelo `Multas`, representando as multas associadas ao livro.
  - `Emprestimo`: Relação com o modelo `Emprestimo`, representando os empréstimos associados ao livro.
  - `Reservas`: Relação com o modelo `Reservas`, representando as reservas associadas ao livro.

### Autor

- Tabela: `Autor`
- Descrição: Representa um autor.
- Campos:
  - `id`: Identificador único do autor (tipo: Inteiro).
  - `createdAt`: Data de criação do registro (tipo: DateTime).
  - `updatedAt`: Data de atualização do registro (tipo: DateTime).
  - `nome`: Nome do autor (tipo: String).
  - `bibliotecaId`: Identificador único da biblioteca associada ao autor (tipo: Inteiro).
- Relações:
  - `biblioteca`: Relação com o modelo `Biblioteca`, associada ao campo `bibliotecaId`.
  - `Livro`: Relação com o modelo `Livro`, representando os livros associados ao autor.

### Lingua

- Tabela: `Lingua`
- Descrição: Representa uma língua.
- Campos:
  - `id`: Identificador único da língua (tipo: Inteiro).
  - `createdAt`: Data de criação do registro (tipo: DateTime).
  - `updatedAt`: Data de atualização do registro (tipo: DateTime).
  - `nome`: Nome da língua (tipo: String).
  -

`bibliotecaId`: Identificador único da biblioteca associada à língua (tipo: Inteiro).

- Relações:
  - `biblioteca`: Relação com o modelo `Biblioteca`, associada ao campo `bibliotecaId`.
  - `Livro`: Relação com o modelo `Livro`, representando os livros associados à língua.

### Categoria

- Tabela: `Categoria`
- Descrição: Representa uma categoria.
- Campos:
  - `id`: Identificador único da categoria (tipo: Inteiro).
  - `createdAt`: Data de criação do registro (tipo: DateTime).
  - `updatedAt`: Data de atualização do registro (tipo: DateTime).
  - `nome`: Nome da categoria (tipo: String).
  - `bibliotecaId`: Identificador único da biblioteca associada à categoria (tipo: Inteiro).
- Relações:
  - `biblioteca`: Relação com o modelo `Biblioteca`, associada ao campo `bibliotecaId`.
  - `Livro`: Relação com o modelo `Livro`, representando os livros associados à categoria.

### Estoque

- Tabela: `Estoque`
- Descrição: Representa o estoque de livros em uma biblioteca.
- Campos:
  - `id`: Identificador único do estoque (tipo: Inteiro).
  - `createdAt`: Data de criação do registro (tipo: DateTime).
  - `updatedAt`: Data de atualização do registro (tipo: DateTime).
  - `quantidadeTotal`: Quantidade total de livros no estoque (tipo: Inteiro).
  - `quantidadeDisponivel`: Quantidade de livros disponíveis no estoque (tipo: Inteiro).
  - `quantidadeEmprestada`: Quantidade de livros emprestados do estoque (tipo: Inteiro).
  - `bibliotecaId`: Identificador único da biblioteca associada ao estoque (tipo: Inteiro).
- Relações:
  - `biblioteca`: Relação com o modelo `Biblioteca`, associada ao campo `bibliotecaId`.
  - `Livro`: Relação com o modelo `Livro`, representando o livro associado ao estoque (opcional).

### Emprestimo

- Tabela: `Emprestimo`
- Descrição: Representa um empréstimo de livro feito por um usuário em uma biblioteca.
- Campos:
  - `id`: Identificador único do empréstimo (tipo: Inteiro).
  - `createdAt`: Data de criação do registro (tipo: DateTime).
  - `updatedAt`: Data de atualização do registro (tipo: DateTime).
  - `data_dev`: Data de devolução do livro (tipo: DateTime).
  - `status`: Status do empréstimo, com valores "DEVOLVIDO", "NAO_DEVOLVIDO" ou "ATRASADO" (tipo: Enum `EmprestimoStatus`).
  - `usuarioId`: Identificador único do usuário que realizou o empréstimo (tipo: Inteiro).
  - `LivroId`: Identificador único do livro emprestado (tipo: Inteiro).
  - `bibliotecarioId`: Identificador único do bibliotecário responsável pelo empréstimo (tipo: Inteiro).
  - `bibliotecaId`: Identificador único da biblioteca associada ao empréstimo (tipo: Inteiro).
- Relações:
  - `Usuario`: Rel

ação com o modelo `Usuario`, associada ao campo `usuarioId`.

- `Livro`: Relação com o modelo `Livro`, associada ao campo `LivroId`.
- `bibliotecario`: Relação com o modelo `Usuario`, representando o bibliotecário responsável pelo empréstimo.
- `biblioteca`: Relação com o modelo `Biblioteca`, associada ao campo `bibliotecaId`.

### Notificacao

- Tabela: `Notificacao`
- Descrição: Representa uma notificação enviada aos usuários de uma biblioteca.
- Campos:
  - `id`: Identificador único da notificação (tipo: Inteiro).
  - `createdAt`: Data de criação do registro (tipo: DateTime).
  - `updatedAt`: Data de atualização do registro (tipo: DateTime).
  - `mensagem`: Mensagem da notificação (tipo: String).
  - `data_envio`: Data de envio da notificação (tipo: DateTime).
  - `bibliotecaId`: Identificador único da biblioteca associada à notificação (tipo: Inteiro).
- Relações:
  - `biblioteca`: Relação com o modelo `Biblioteca`, associada ao campo `bibliotecaId`.

### Multas

- Tabela: `Multas`
- Descrição: Representa as multas aplicadas aos usuários de uma biblioteca.
- Campos:
  - `id`: Identificador único da multa (tipo: Inteiro).
  - `createdAt`: Data de criação do registro (tipo: DateTime).
  - `updatedAt`: Data de atualização do registro (tipo: DateTime).
  - `valor`: Valor da multa (tipo: Float).
  - `status`: Status da multa, com valores "PENDENTE" ou "PAGO" (tipo: Enum `MultaStatus`).
  - `usuarioId`: Identificador único do usuário associado à multa (tipo: Inteiro).
  - `bibliotecaId`: Identificador único da biblioteca associada à multa (tipo: Inteiro).
- Relações:
  - `Usuario`: Relação com o modelo `Usuario`, associada ao campo `usuarioId`.
  - `biblioteca`: Relação com o modelo `Biblioteca`, associada ao campo `bibliotecaId`.

### Usuario

- Tabela: `Usuario`
- Descrição: Representa um usuário registrado em uma biblioteca.
- Campos:
  - `id`: Identificador único do usuário (tipo: Inteiro).
  - `createdAt`: Data de criação do registro (tipo: DateTime).
  - `updatedAt`: Data de atualização do registro (tipo: DateTime).
  - `nome`: Nome do usuário (tipo: String).
  - `email`: E-mail do usuário (tipo: String).
  - `senha`: Senha do usuário (tipo: String).
  - `tipo`: Tipo de usuário, com valores "ALUNO", "PROFESSOR" ou "COMUNIDADE" (tipo: Enum `UsuarioTipo`).
  - `status`: Status do usuário, com valores "ATIVO" ou "INATIVO" (tipo: Enum `StatusDefault`).
  - `bibliotecaId`: Identificador único da biblioteca associada ao usuário (tipo: Inteiro).
- Relações:
  - `biblioteca`: Relação com o modelo `Biblioteca`, associada ao campo `bibliotecaId`.
  - `Emprestimo`: Relação com o modelo `Emprestimo`, representando os empr

éstimos realizados pelo usuário.

- `Multas`: Relação com o modelo `Multas`, representando as multas aplicadas ao usuário.
- `Notificacao`: Relação com o modelo `Notificacao`, representando as notificações enviadas ao usuário.

Esses são os modelos e suas relações básicas para um sistema de biblioteca. Lembre-se de que essa é apenas uma sugestão e você pode personalizar e adicionar mais campos e relações de acordo com as necessidades do seu projeto.

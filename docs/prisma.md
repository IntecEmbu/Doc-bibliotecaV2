# Documentação: Adição de Novas Tabelas e Migrações com Prisma

Esta documentação fornece um guia passo a passo sobre como adicionar novas tabelas ao banco de dados e executar migrações usando o Prisma. Siga as instruções abaixo para garantir uma adição segura e controlada de novas tabelas ao seu esquema de banco de dados.

## Pré-requisitos

Antes de prosseguir com a adição de novas tabelas, certifique-se de que você tenha os seguintes pré-requisitos configurados e instalados em seu ambiente de desenvolvimento:

- Node.js (versão 12 ou superior)
- NPM (gerenciador de pacotes do Node.js)
- Banco de dados configurado e conectado ao Prisma

## Passo 1: Definir o Esquema da Nova Tabela

1. Abra o arquivo `schema.prisma` em seu projeto Prisma. Este arquivo contém a definição do esquema do banco de dados.
2. Adicione uma nova definição de modelo para a tabela desejada, seguindo a sintaxe do Prisma. Por exemplo:

   ```ts
   model NovaTabela {
     id    Int    @id @default(autoincrement())
     nome  String
     campo String
     ...
   }
   ```

   Substitua `NovaTabela` pelo nome desejado para a nova tabela e defina os campos necessários de acordo com os requisitos do seu aplicativo.

3. Salve o arquivo `schema.prisma`.

## Passo 2: Gerar a Nova Migração

1. Abra o terminal ou prompt de comando.
2. Navegue até o diretório raiz do seu projeto Prisma.
3. Execute o seguinte comando para gerar a nova migração:

   ```bash
   npx prisma migrate dev --name nome_da_migracao
   ```

   Substitua `nome_da_migracao` por um nome descritivo para a migração. Certifique-se de usar um nome significativo que descreva as alterações sendo feitas na tabela.

4. Aguarde até que a migração seja gerada com sucesso. Isso criará um novo arquivo de migração na pasta `prisma/migrations`.

## Passo 3: Aplicar a Nova Migração

1. Com a migração gerada, você está pronto para aplicá-la ao banco de dados.
2. Execute o seguinte comando para executar a migração:

   ```bash
   npx prisma migrate dev
   ```

   Esse comando irá aplicar a migração pendente ao banco de dados. O Prisma irá comparar o estado atual do esquema com as migrações pendentes e realizar as alterações necessárias.

3. Aguarde até que a migração seja concluída com sucesso. Você verá uma confirmação no terminal indicando que a migração foi aplicada com êxito.

Parabéns! Agora você adicionou com sucesso uma nova tabela ao seu banco de dados e aplicou a migração correspondente usando o Prisma. Certifique-se de verificar se a nova tabela foi criada corretamente no banco de dados.

## Conclusão

Este guia forneceu instruções sobre como adicionar novas tabelas e executar migrações usando o Prisma. Lembre-se de que as migrações são uma prática recomendada para manter o controle e a integridade do esquema do banco de dados ao longo do tempo.

Certifique-se de consultar a [documentação oficial do Prisma](https://www.prisma.io/docs/) para obter informações mais detalhadas sobre migrações, esquema e outros recursos avançados.

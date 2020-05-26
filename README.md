# be-the-hero-application-backend-node
Semana OmniStack 11.0 - Projeto Be the Hero

O projeto consiste em ajudar ONGs, permitindo o cadastro de cada uma delas levando seus casos até as pessoas, para que possam realizar doações


# Para configurar a parte do banco
1 - Primeiramente execute npm install knex;
2 - npm install sqlite3;
3 - npx knex init;

# Em seguida para criar as migrations, siga os passos
Nesse caso estamos criando o schema da tabela
1 - npx knex migrate:make create_'nome da sua tabela'

Em seguida um arquivo será criado na sua estrutura do codigo onde você poderá definir as colunas da sua tabela;
Ele terá o modulo up e o down

Up: cria a tabela
Down: normalmente usado para droppar a tabela

por exemplo:
exports.up = function(knex) {
    return knex.schema.createTable('sua tabela', function (table) {
        table.string('id').primary();
        table.string('name').notNullable();
        ...
    });
};

exports.down = function(knex) {
  return knex.schema.dropTable('sua tabela');
};

Em seguida para executar a migration
2 - npx knex migrate:latest

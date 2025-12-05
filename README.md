Sistema-Gerenciamento-Master

Sistema completo de gerenciamento desenvolvido em PHP e MySQL, estruturado para servir como base educacional e também como ponto de partida para projetos reais. O sistema implementa CRUD, autenticação, organização modular e boas práticas fundamentais de desenvolvimento web.

Sumário

Descrição Geral

Funcionalidades

Arquitetura e Estrutura de Pastas

Requisitos do Sistema

Instalação e Configuração

Configuração do Banco de Dados

Fluxo de Funcionamento

Segurança e Boas Práticas

Possíveis Melhorias

Licença

Descrição Geral

O Sistema-Gerenciamento-Master é um sistema web desenvolvido em PHP com MySQL que implementa funcionalidades administrativas essenciais. O objetivo é demonstrar, de forma prática, a integração entre backend PHP e banco de dados MySQL, além da construção de módulos CRUD reutilizáveis e um fluxo simples de autenticação.

Este projeto também funciona como material de estudo para iniciantes em desenvolvimento web.

Funcionalidades

CRUD completo (Create, Read, Update, Delete)

Sistema de login e autenticação com PHP Sessions

Gerenciamento de usuários/itens/registros (dependendo da sua tabela principal)

Validação de formulários no backend

Feedback de erros e mensagens de sucesso

Conexão estruturada com MySQL

Código organizado e comentado

Interface simples e funcional

Arquitetura e Estrutura de Pastas

A estrutura abaixo reflete o padrão do projeto:

sistema-gerenciamento-master/
│
├── config/
│   └── conexao.php        # Configuração da conexão MySQL
│
├── pages/
│   ├── cadastrar.php       # Página de criação
│   ├── editar.php          # Página de edição
│   ├── listar.php          # Página de listagem
│   └── excluir.php         # Página de remoção
│
├── login/
│   ├── index.php           # Tela de login
│   ├── validar.php         # Validação de credenciais
│   └── logout.php          # Encerrar sessão
│
├── public/
│   ├── css/
│   └── js/
│
├── database/
│   └── script.sql          # Script para criação do banco (se aplicável)
│
└── index.php               # Página inicial após login

Requisitos do Sistema

PHP 7.4+

MySQL 5.7+ ou MariaDB

Servidor Apache ou Nginx

Extensões PHP:

mysqli

session

Ambientes recomendados:

XAMPP

WAMP

Laragon

LAMP (Linux)

Instalação e Configuração
1. Clonar o Repositório
git clone https://github.com/JonasFont/Sistema-Gerenciamento-Master---PHP-and-MySql.git

2. Mover para o diretório do servidor

Exemplo com XAMPP:

xampp/htdocs/sistema-gerenciamento-master

3. Configurar a conexão com o banco

No arquivo:

config/conexao.php


Atualize com o seu host, usuário, senha e nome do banco.

4. Importar banco de dados

Caso exista o arquivo SQL no diretório database/, importe via phpMyAdmin.

5. Acessar pelo navegador
http://localhost/sistema-gerenciamento-master

Configuração do Banco de Dados

Exemplo de estrutura sugerida (caso não haja SQL incluso):

CREATE DATABASE sistema_master;

USE sistema_master;

CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100),
    senha VARCHAR(255),
    criado_em TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);


Use senhas criptografadas caso deseje reforçar a segurança:

password_hash('senha123', PASSWORD_DEFAULT);

Fluxo de Funcionamento

Usuário acessa a tela de login

O sistema valida credenciais no banco

A sessão é criada e o usuário é redirecionado

A partir do painel, é possível acessar:

Cadastro

Edição

Exclusão

Listagem de registros

A sessão pode ser encerrada via logout

Segurança e Boas Práticas

Este projeto serve como base de aprendizado; recomenda-se implementar:

Prepared Statements (mysqli_stmt) para evitar SQL injection

Password Hashing com password_hash() e password_verify()

Controle de acesso por níveis

Validação mais rígida de campos no backend

Sanitização de dados via filter_input()

HTTPS em produção

Possíveis Melhorias

Migrar para arquitetura MVC

Criar uma interface mais moderna com Bootstrap ou TailwindCSS

Criar API REST com PHP

Implementar paginação e filtros de busca

Adicionar logs de auditoria

Utilizar PDO ao invés de mysqli

Criar testes unitários com PHPUnit

Licença

Este projeto está disponível como código aberto.
Sinta-se à vontade para modificar, melhorar e utilizar como desejar.

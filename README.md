Sistema de lista de tarefas em **uma única página** (`index.php`) com:
- Cadastro (título obrigatório, descrição opcional, **prazo data/hora** opcional)
- Listagem
- Alternar concluída/pendente (✔)
- Excluir
- **Ajax** (`fetch`) para operações sem recarregar
- **MySQL + PDO** com prepared statements
- **Bootstrap 5** + Bootstrap Icons (visual AdminLTE-like)
- Criação automática da tabela (se não existir)

## Requisitos
- PHP 8+
- MySQL 5.7+ / MariaDB 10.4+
- XAMPP (Apache + MySQL) ou equivalente

## Instalação
1. Copie esta pasta para `C:\xampp\htdocs\TODO-list`.
2. Inicie **Apache** e **MySQL** no XAMPP.
3. Crie o banco e a tabela no phpMyAdmin:
   ```sql
   CREATE DATABASE IF NOT EXISTS todo_db
     CHARACTER SET utf8mb4
     COLLATE utf8mb4_general_ci;
   USE todo_db;
   CREATE TABLE IF NOT EXISTS tarefas (
     id INT AUTO_INCREMENT PRIMARY KEY,
     title VARCHAR(255) NOT NULL,
     description TEXT NULL,
     due_date DATE NULL,
     due_time TIME NULL,
     done TINYINT(1) NOT NULL DEFAULT 0,
     created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP
   ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
Alternativamente, abra a página que a tabela é criada automaticamente via PDO.

Ajuste as credenciais no topo do index.php se necessário (DB_USER, DB_PASS).

Uso
Acesse: http://localhost/TODO-list/index.php

Cadastre tarefas, marque como concluídas, exclua e filtre.

Indicadores:

Vencida: prazo já passou (badge vermelha)

Vence em 24h: vence em até 24h (badge amarela)

Banco de dados
Banco: todo_db

Tabela: tarefas

Colunas:

id INT (PK, AI)

title VARCHAR(255)

description TEXT

due_date DATE (opcional)

due_time TIME (opcional)

done TINYINT(1) default 0

created_at TIMESTAMP default CURRENT_TIMESTAMP

Tecnologias e práticas
PHP + PDO (prepared statements)

Ajax (fetch) com respostas JSON

CSRF token nas ações POST

Escape de HTML na renderização

Bootstrap 5 + Icons

sql


---

# Assistência Técnica de Celulares

Sistema web para gerenciar clientes, aparelhos e agendamentos de reparos.

**Tecnologias:** Python, Flask e MySQL.

## Requisitos

- Python 3.10 ou superior
- MySQL 8 ou superior
- MySQL Workbench (recomendado)

## Instalar e executar — Windows (CMD)

Abra a pasta `sistema` no VS Code e selecione **Terminal → Novo Terminal**. Confira se existem `app.py` e `requirements.txt` na pasta atual.

Crie o ambiente e instale as dependências:

```cmd
python -m venv .venv
.venv\Scripts\python.exe -m pip install -r requirements.txt
```

No MySQL Workbench, conecte-se ao MySQL, abra o arquivo `assistencia_db.sql` que está na pasta principal do pacote e execute-o pelo ícone de raio.

> **Atenção:** o script apaga e recria o banco `assistencia_db` se ele já existir.

Na mesma janela do CMD, configure a senha do seu MySQL e inicie o sistema:

```cmd
set DB_HOST=localhost
set DB_PORT=3306
set DB_USER=root
set DB_PASSWORD=SUA_SENHA_MYSQL
set DB_NAME=assistencia_db
set SECRET_KEY=chave-secreta-de-teste
set CPF_ENCRYPTION_KEY=ZDJPXW1P2xasuIaO73ZD_wwn4I6XXOA4UYnJCLrc060=
.venv\Scripts\python.exe app.py
```

Troque `SUA_SENHA_MYSQL` pela senha do seu MySQL. Deixe o CMD aberto e acesse **http://localhost:5000**.

## Login de demonstração

- **Usuário:** `admin`
- **Senha:** `admin123`

## Testes

Para testar a conexão com o banco, em outro CMD na pasta `sistema`, execute:

```cmd
.venv\Scripts\python.exe testar_conexao.py
```

Para rodar os testes automatizados:

```cmd
.venv\Scripts\python.exe -m unittest discover -s tests -v
```

## Funcionalidades

- Login, sessão temporária e logout.
- Cadastro, busca e edição de clientes.
- CPF armazenado cifrado.
- Cadastro de aparelhos associados a clientes.
- Cadastro, consulta e reagendamento de reparos.

**Observação:** a chave Fernet e as credenciais incluídas são apenas para demonstração escolar. Não use dados reais com essas configurações.

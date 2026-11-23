# Cadastro de alunos — Django + SQLite

Aplicação didática para cadastrar, listar, editar e excluir alunos, construída com Django, SQLite e Bootstrap 5.

## Funcionalidades
- Cadastro com nome, e-mail, data de nascimento e turma.
- Listagem em ordem alfabética, edição e exclusão com confirmação.
- Validação de e-mail único e proteção CSRF.
- Interface responsiva em português.

## Requisitos
Python 3.13+, Windows/PowerShell e VS Code.

## Executar
```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```
Abra http://127.0.0.1:8000/.

Se o PowerShell bloquear a ativação: `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`.

## Estrutura
- `config/`: configurações, URLs e WSGI.
- `alunos/`: modelo, formulário, views, URLs, admin e templates.

## Deploy
Build: `pip install -r requirements.txt`
Start: `python manage.py migrate && gunicorn config.wsgi:application`

Configure `SECRET_KEY` forte e `DEBUG=False` no ambiente de produção. O app lê `RENDER_EXTERNAL_HOSTNAME` para hosts e origens CSRF. SQLite em disco efêmero pode perder dados em reinicializações; use disco persistente ou PostgreSQL em produção.

## Segurança
Projeto didático. Não publique dados pessoais reais de alunos. Para uso institucional, implemente autenticação, autorização, backups e controles de privacidade.

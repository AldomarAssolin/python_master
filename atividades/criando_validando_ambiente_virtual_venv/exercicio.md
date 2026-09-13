## Objetivo do exercício

Este exercício tem por objetivo Praticar a criação, ativação e validação de um ambiente virtual usando o módulo embutido venv do Python. Será praticado a criação da pasta do projeto, a geração da venv, sua ativação, verificação se está realmente em uso e instalação de um pacote para comprovar o isolamento do ambiente.

## Contexto

No módulo de ambientação do curso, vimos como criar e ativar ambientes virtuais com o venv (python -m venv ...), além de onde a pasta do ambiente é criada e como ativá-la em diferentes sistemas operacionais. Neste exercício, você colocará isso em prática para garantir que seu setup esteja correto e pronto para receber o Django em seguida.

## Objetivo

- Criar um projeto de exemplo e um ambiente virtual isolado dentro dele usando venv;
- Ativar o ambiente virtual no seu sistema operacional;
- Verificar, por meio de comandos, que o Python e o pip ativos são os da venv;
- Instalar um pacote (Django) dentro da venv para confirmar o isolamento;
- Desativar e reativar a venv.

## Entrega

A estratégia envolveu a busca do sistema operacional com o comando `uname -a`, foi criado o projeto em `~/Workspaces/learn` diretório de estudos utilizado no ambiente local, depois de desenvolvido foi feito o comando `tree -I "bin|include|lib|lib64|__pycache__|pyvenv.cfg"` para a exibição da árvore do projeto.

Como conclusão foi criado um repositório github com o nome `python_master` conectado via `git remote add origin git@github.com:AldomarAssolin/python_master.git` feito commit inicial.

A execução do exercício foi efetuado em uma branch de trabalho `feat/criando_validando_ambiente_virtual_venv`.

- **sistema operacional utilizado:**
    ```bash
    aldomar@aldomar-B450M-K:~$ uname -a
    Linux aldomar-B450M-K 7.0.0-31-generic #31~24.04.1-Ubuntu SMP PREEMPT_DYNAMIC Mon Aug 10 09:38:02 UTC 2 x86_64 x86_64 x86_64 GNU/Linux
    ```

- **estrutura de pastas do projeto:**

    ```bash

    (venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master$ tree -I "bin|include|lib|lib64|__pycache__|pyvenv.cfg"
    .
    ├── atividades
    │   ├── criando_validando_ambiente_virtual_venv
    │   │   ├── exercicio.md
    │   │   ├── README.md
    │   │   └── venv
    │   └── README.md
    └── README.md

    4 directories, 4 files

    ```

- Histórico dos comandos executados e suas saídas relevantes:

    - **Criação e ativação da venv:**

        - **Criação do ambiente virtual (venv):**

            ```bash

            aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv$ python3 -m venv venv

            ```

        - **Ativação do ambiente virtual (venv):**

            ```bash

            aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv$ source venv/bin/activate
            (venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv$

            ```

    - **Saída de which python:**

        ```bash

        (venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv$ which python
        /home/aldomar/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv/venv/bin/python

        ```
    
    - **Intalação django:**

        ```bash

        (venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv$ pip install django
        Collecting django
        Using cached django-6.1.1-py3-none-any.whl.metadata (3.9 kB)
        Collecting asgiref>=3.9.1 (from django)
        Using cached asgiref-3.12.1-py3-none-any.whl.metadata (9.4 kB)
        Collecting sqlparse>=0.5.0 (from django)
        Using cached sqlparse-0.6.0-py3-none-any.whl.metadata (6.0 kB)
        Using cached django-6.1.1-py3-none-any.whl (8.4 MB)
        Using cached asgiref-3.12.1-py3-none-any.whl (25 kB)
        Using cached sqlparse-0.6.0-py3-none-any.whl (50 kB)
        Installing collected packages: sqlparse, asgiref, django
        Successfully installed asgiref-3.12.1 django-6.1.1 sqlparse-0.6.0

        ```

    - **Saída de pip show django:**

        ```bash
        
        (venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv$ pip show django
        Name: Django
        Version: 6.1.1
        Summary: A high-level Python web framework that encourages rapid development and clean, pragmatic design.
        Home-page: 
        Author: 
        Author-email: Django Software Foundation <foundation@djangoproject.com>
        License: 
        Location: /home/aldomar/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv/venv/lib/python3.12/site-packages
        Requires: asgiref, sqlparse
        Required-by: 
        (venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv$ 

        ```

    - **Desativação (deactivate) e reativação:**

        ```bash

        (venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv$ deactivate
        aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv$ source venv/bin/activate
        (venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master/atividades/criando_validando_ambiente_virtual_venv$

        ```


## Critérios de avaliação

- ✅ Corretude: a pasta venv existe dentro do projeto e os comandos usados são compatíveis com o sistema informado;
- ✅ Evidência de isolamento: which/where aponta para o Python dentro de venv e pip show django mostra Location dentro da venv;
- ✅ Clareza: os passos estão documentados com comandos e saídas reais do seu terminal;
- ✅ Completude: você realizou ativar, verificar, instalar, desativar e reativar a venv.

## Observações

Neste exercícios pude praticar os conceitos de virtualização do python, além de aplicar conceitos de *Linux* e *git*.

Planejamento de tarefas adequando ao CI para versionamento, organização para escalabilidade com repositório no github comandos importantes e essenciais para desenvolvimento com python tais como:

- Para virtualização e empacotamento do projeto em um ambiente virtual python com o comando `python3 -m venv venv`;
- Ativação do ambiente com o comando `source venv/bin/activate`;
- Verificação do python ativo utilizando o comando `which python`;
- Instalação e visualização do django no projeto com os comandos `pip install django` e `pip show django` respectivamente;
- Desativação com `deactivate`.

Também utilizei comando do linux como `uname -a` para verificação do sistema utilizado e `tree -I "bin|include|lib|lib64|__pycache__|pyvenv.cfg"` para exibição da árvore do projeto ignorando arquivos e diretórios de *venv* para não tornar a saída mnuito extensa.

Para finalizar subi o projeto para o repositório remoto criado no github a partir de uma branch de trabalho `feat/criando_validando_ambiente_virtual_venv`.

**Comandos git para checagem:**

```bash

(venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master$ git status --short
 M README.md
 M atividades/criando_validando_ambiente_virtual_venv/README.md
 D atividades/criando_validando_ambiente_virtual_venv/exercicio_readme.md
?? .example.gitignore
?? .gitignore
?? atividades/criando_validando_ambiente_virtual_venv/exercicio.md
(venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master$ git diff --stat
 README.md                                          |   2 +-
 .../README.md                                      | 153 ++++++++++++++++++++-
 .../exercicio_readme.md                            | 151 --------------------
 3 files changed, 153 insertions(+), 153 deletions(-)
(venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master$ git diff --check
(venv) aldomar@aldomar-B450M-K:~/Workspaces/learn/python/python_master$ 


```

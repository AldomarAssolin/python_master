# Criando e validando um ambiente virtual com venv

## Objetivo do exercício

Pratique a criação, ativação e validação de um ambiente virtual usando o módulo embutido venv do Python. Você irá criar a pasta do projeto, gerar a venv, ativá-la, verificar se está realmente em uso e instalar um pacote para comprovar o isolamento do ambiente.

## Contexto

No módulo de ambientação do curso, vimos como criar e ativar ambientes virtuais com o venv (python -m venv ...), além de onde a pasta do ambiente é criada e como ativá-la em diferentes sistemas operacionais. Neste exercício, você colocará isso em prática para garantir que seu setup esteja correto e pronto para receber o Django em seguida.

## Objetivo

- Criar um projeto de exemplo e um ambiente virtual isolado dentro dele usando venv;
- Ativar o ambiente virtual no seu sistema operacional;
- Verificar, por meio de comandos, que o Python e o pip ativos são os da venv;
- Instalar um pacote (Django) dentro da venv para confirmar o isolamento;
- Desativar e reativar a venv.

## Pré-requisitos

Python e pip instalados (conforme visto nas aulas do módulo de ambientação);
Acesso a um terminal (VS Code, PowerShell, CMD, bash, zsh etc.).

## Tarefas

1. Crie a pasta do projeto e entre nela
    - Crie uma pasta para o exercício (ex.: projeto_pycode ou meu_projeto). Entre nessa pasta pelo terminal.
2. Crie o ambiente virtual com venv
    - No terminal, dentro da pasta do projeto, execute:

```bash

python -m venv venv

```

**Observações:**

- O nome da venv deve ser exatamente venv para mantermos um padrão neste exercício;
- Se tudo der certo, uma pasta venv será criada dentro do seu projeto.

3. Ative o ambiente virtual
    - **Windows (CMD):**
    ```bash
    venv\Scripts\activate
    ```
    - **Windows (PowerShell):**
    ```bash
    .\venv\Scripts\Activate.ps1
    ```

    - **Linux/macOS (bash/zsh):**
    ```bash
    source venv/bin/activate
    ```

>Dica: ao ativar, seu prompt normalmente exibirá um prefixo (venv).

4. Verifique se a venv está ativa de verdade
    - Execute um (apenas um) dos comandos abaixo, conforme seu sistema:
        - **Linux/macOS:**
            * `which python`
        - **Windows (CMD/PowerShell):**
            * `where python`

>O caminho retornado deve apontar para dentro da pasta venv do seu projeto (por exemplo, .../venv/bin/python no Linux/macOS, ou ...\venv\Scripts\python.exe no Windows).

5. Instale o Django dentro da venv
    - Ainda com a venv ativa, rode:
    ```bash
    pip install django
    ```

    - Verifique se o Django foi instalado dentro da venv:
    ```bash
    pip show django
    ```
> Você deve ver informações do pacote, incluindo o Location apontando para dentro da sua venv (por exemplo, .../venv/lib/pythonX.Y/site-packages ou ...\venv\Lib\site-packages).

6. Desative e reative a venv
    - Desative com:
    ```bash
    deactivate
    ```

    - Reative conforme seu sistema (passo 3) para garantir que você consegue alternar entre estados ativado e desativado sem erros.


## Entrega (o que enviar)

Envie um único bloco em Markdown contendo:

- O sistema operacional utilizado (Windows CMD, Windows PowerShell, Linux ou macOS);
- A estrutura de pastas do projeto (mostre que a pasta venv existe). Exemplo simplificado:

```bash
meu_projeto/
  venv/
  (demais arquivos, se houver)
```

- O histórico dos comandos executados e suas saídas relevantes, incluindo:
    - Ativação da venv;
    - Saída de which python (Linux/macOS) ou where python (Windows);
    - Saída de pip show django (somente os campos Name e - Location são suficientes);
    - Desativação (deactivate) e reativação.

## Critérios de avaliação

- Corretude: a pasta venv existe dentro do projeto e os comandos usados são compatíveis com o sistema informado;
- Evidência de isolamento: which/where aponta para o Python dentro de venv e pip show django mostra Location dentro da venv;
- Clareza: os passos estão documentados com comandos e saídas reais do seu terminal;
- Completude: você realizou ativar, verificar, instalar, desativar e reativar a venv.

Exemplos úteis (não copie/cole literalmente, use como referência)

**Criação da venv:**

```bash
python -m venv venv
```

**Ativação (Windows PowerShell):**

```bash
.\venv\Scripts\Activate.ps1
```

**Ativação (Linux/macOS):**

```bash
source venv/bin/activate
```

**Verificação de caminho do Python:**

```bash
which python    # Linux/macOS
where python    # Windows
```

**Instalação e verificação do Django:**

```bash
pip install django
pip show django
```

**Desativação:**

```bash
deactivate
```

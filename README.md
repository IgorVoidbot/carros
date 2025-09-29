# Projeto Carros

## Descrição

O "Projeto Carros" é uma aplicação web desenvolvida com Django para gerenciar um inventário de veículos. Ele permite que os usuários visualizem uma lista de carros à venda, pesquisem modelos específicos e visualizem os detalhes de cada veículo. Para usuários autenticados, a plataforma oferece funcionalidades de CRUD (Criar, Ler, Editar e Excluir) para os carros no inventário.

## Funcionalidades

  * **Visualização de Carros**: Os usuários podem ver uma lista de todos os carros disponíveis, com a opção de pesquisar por modelo.
  * **Detalhes do Carro**: Cada carro tem uma página de detalhes que exibe informações como marca, modelo, ano de fabricação, ano do modelo, placa, valor e uma biografia.
  * **Autenticação de Usuário**: O sistema inclui funcionalidades de registro, login e logout para usuários.
  * **Gerenciamento de Carros (CRUD)**: Usuários autenticados podem adicionar, editar e excluir carros do inventário.
  * **Validação de Formulários**: O formulário de cadastro de carros possui validações para garantir que o valor do carro seja de no mínimo R$20.000 e que o ano de fabricação não seja anterior a 1975.
  * **Inventário Automatizado**: O sistema mantém um registro do número total de carros e do valor total do inventário, atualizando-o automaticamente sempre que um carro é adicionado, editado ou removido.
  * **Integração com OpenAI (Desativada)**: O projeto inclui um módulo para gerar descrições de carros usando a API da OpenAI, mas ele está atualmente comentado no código.

## Instalação

Siga os passos abaixo para configurar e executar o projeto em seu ambiente local:

1.  **Clone o Repositório**

    ```bash
    git clone https://github.com/seu-usuario/projeto-carros.git
    cd projeto-carros
    ```

2.  **Crie e Ative um Ambiente Virtual**

    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows, use `venv\Scripts\activate`
    ```

3.  **Instale as Dependências**

    ```bash
    pip install -r requirements.txt
    ```

4.  **Configure o Banco de Dados**

    O projeto está configurado para usar o PostgreSQL. Certifique-se de que você tenha o PostgreSQL instalado e em execução. Em seguida, crie um banco de dados e um usuário para a aplicação.

    Atualize as credenciais do banco de dados no arquivo `app/settings.py`:

    ```python
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql',
            'NAME': 'seu_banco_de_dados',
            'USER': 'seu_usuario',
            'PASSWORD': 'sua_senha',
            'HOST': 'localhost',
            'PORT': '5432'
        }
    }
    ```

5.  **Aplique as Migrações**

    ```bash
    python manage.py migrate
    ```

6.  **Crie um Superusuário**

    ```bash
    python manage.py createsuperuser
    ```

7.  **Execute o Servidor de Desenvolvimento**

    ```bash
    python manage.py runserver
    ```

    A aplicação estará disponível em `http://127.0.0.1:8000/`.

## Como Usar

  * **Página Inicial**: A página inicial redireciona para a lista de carros.
  * **Ver Carros**: Acesse a URL `/cars/` para ver todos os carros disponíveis.
  * **Registro e Login**: Utilize os botões no menu para se registrar ou fazer login.
  * **Adicionar Carro**: Após o login, clique em "Cadastrar Carro" para adicionar um novo veículo ao inventário.
  * **Editar e Excluir**: Na página de detalhes de um carro, usuários autenticados verão os botões para editar ou excluir o veículo.

## Tecnologias Utilizadas

  * **Backend**:

      * Python
      * Django
      * PostgreSQL (via `psycopg2-binary`)

  * **Frontend**:

      * HTML
      * CSS

  * **Dependências Principais**:

      * `Django`
      * `psycopg2-binary`
      * `Pillow`

Para uma lista completa de todas as dependências, consulte o arquivo `requirements.txt`.

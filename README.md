
# ChatBotando

ChatBotando é um chatbot de turismo cultural em Salvador/Bahia, desenvolvido para fornecer informações turísticas e culturais de forma interativa e amigável.

## Introdução

Este projeto visa criar um chatbot que pode responder a perguntas e fornecer informações sobre pontos turísticos, eventos culturais e história de Salvador/Bahia. Utilizamos diversas tecnologias para garantir uma experiência agradável e informativa para os usuários.

## Pré-requisitos

Certifique-se de ter as seguintes ferramentas instaladas em sua máquina:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [Open WebUI](https://github.com/open-webui/open-webui)
- [Langflow](https://github.com/langflow-ai/langflow)
- [PostgreSQL](https://www.postgresql.org/docs/current/tutorial-install.html)

## Instalação

1. **Clone o repositório**:
    ```bash
    git clone https://github.com/olipericles/ChatBotando.git
    cd ChatBotando
    ```

2. **Configurar variáveis de ambiente**:

    Crie um arquivo `.env` na raiz do projeto e adicione as variáveis de ambiente necessárias:

    ```plaintext
    # Chave de API do OpenAI
    OPENAI_API_KEY=sk-proj-******************

    # Chave de API do Langchain (Langsmith)
    LANGCHAIN_API_KEY=******************
    LANGCHAIN_PROJECT=Pessoal

    # Configurações do Langflow
    USER_AGENT="ChatBotando"
    LANGFLOW_STORE_ENVIRONMENT_VARIABLES=true
    LANGFLOW_CONFIG_DIR=langflow
    LANGFLOW_DATABASE_URL=postgresql://langflow:langflow_password@postgres:5432/langflow
    LANGFLOW_AUTO_LOGIN=false
    LANGFLOW_SUPERUSER=admin
    LANGFLOW_SUPERUSER_PASSWORD=******************

    # Configurações do WebUI
    WEBUI_NAME="ChatBotando"
    DATABASE_URL=postgresql://webui:webui_password@postgres:5432/webui

    # Configurações do banco de dados
    POSTGRES_USER=postgres
    POSTGRES_PASSWORD=******************
    ```

3. **Construir e iniciar os contêineres Docker**:
    ```bash
    docker-compose up --build
    ```

## Configuração

Certifique-se de configurar corretamente as variáveis de ambiente no arquivo `.env` criado na etapa de instalação. Aqui estão algumas variáveis importantes que você deve definir:

- `OPENAI_API_KEY`: Chave da API do OpenAI para o chatbot.
- `LANGCHAIN_API_KEY`: Chave da API do Langchain.
- `LANGFLOW_DATABASE_URL`: URL do banco de dados do Langflow.
- `DATABASE_URL`: URL do banco de dados do WebUI.
- `POSTGRES_USER`: Usuário do banco de dados PostgreSQL.
- `POSTGRES_PASSWORD`: Senha do banco de dados PostgreSQL.

## Uso

Após iniciar os contêineres Docker, o chatbot estará disponível para uso. Você pode interagir com o chatbot através da interface fornecida.

Para acessar a interface do chatbot, abra seu navegador e vá para `http://localhost:<port>` (substitua `<port>` pela porta configurada).

## Estrutura do Projeto

Aqui está uma visão geral da estrutura do projeto:

```
ChatBotando/
├── langflow/
├── nginx/
├── open-webui/
├── postgres/
├── .gitignore
├── docker-compose.yaml
├── README.md
```

- `langflow/`: Contém arquivos relacionados ao fluxo de conversação do chatbot.
- `nginx/`: Configurações do servidor Nginx.
- `open-webui/`: Interface web do chatbot.
- `postgres/`: Configurações e scripts do banco de dados PostgreSQL.
- `.gitignore`: Arquivo para ignorar arquivos e diretórios desnecessários.
- `docker-compose.yaml`: Arquivo de configuração do Docker Compose.
- `README.md`: Documentação do projeto.

## Contribuição

Se você deseja contribuir com o projeto, siga estas etapas:

1. **Fork o repositório**.
2. **Crie uma nova branch**:
    ```bash
    git checkout -b feature/nova-funcionalidade
    ```
3. **Faça suas alterações**.
4. **Commit suas alterações**:
    ```bash
    git commit -m "Adiciona nova funcionalidade"
    ```
5. **Envie para o repositório remoto**:
    ```bash
    git push origin feature/nova-funcionalidade
    ```
6. **Abra um Pull Request**.

Agradecemos suas contribuições!
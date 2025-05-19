# Sistema de Criação de Posts para Instagram com Agentes

Este projeto demonstra um sistema de criação de posts para Instagram utilizando múltiplos agentes baseados em modelos de linguagem, orquestrados para realizar diferentes etapas do processo criativo: busca de notícias, planejamento do post, redação e revisão.

## Visão Geral do Projeto

O sistema é composto por quatro agentes principais, cada um com uma função específica:

1.  **Agente Buscador:** Responsável por pesquisar as últimas notícias e lançamentos relevantes sobre um determinado tópico utilizando o Google Search.
2.  **Agente Planejador:** Analisa os lançamentos encontrados e planeja os pontos chave a serem abordados em um post, selecionando o tema mais relevante.
3.  **Agente Redator:** Cria um rascunho de post para Instagram com base no plano fornecido, visando um tom engajador e informativo.
4.  **Agente Revisor:** Revisa o rascunho gerado, verificando clareza, concisão e adequação ao público-alvo, e sugere melhorias se necessário.

O objetivo é automatizar parte do processo de criação de conteúdo para redes sociais, permitindo a geração rápida de rascunhos de posts sobre tendências atuais.

## Como Rodar o Projeto

Para rodar este projeto, você precisará de um ambiente Python e as bibliotecas listadas nos requisitos.

### Pré-requisitos

*   Python 3.7+
*   Uma API Key do Google Gemini.

### Instalação

1.  Clone o repositório (assumindo que você o tenha em um repositório Git):

bash git clone cd

2.  Instale as dependências necessárias:

bash pip install -q google-genai google-adk

### Configuração da API Key

É necessário configurar sua API Key do Google Gemini como uma variável de ambiente ou utilizando o `userdata` do Google Colab, como demonstrado no código fornecido.

python import os from google.colab import userdata

Se estiver no Colab:
os.environ["GOOGLE_API_KEY"] = userdata.get('GOOGLE_API_KEY')

Se estiver em outro ambiente, configure a variável de ambiente GOOGLE_API_KEY
os.environ["GOOGLE_API_KEY"] = "SUA_API_KEY"

### Execução

Execute o script Python principal (ou o notebook Jupyter/Colab). O programa solicitará que você digite o tópico sobre o qual deseja criar o post.

bash python seu_script.py # Ou execute as células no Colab/Jupyter

O sistema irá então executar a sequência de agentes e exibir os resultados de cada etapa, culminando no rascunho do post e a revisão final.

## Agentes Detalhados

### Agente Buscador

*   **Instrução:** Utilizar a ferramenta `google_search` para encontrar as últimas notícias de lançamentos relevantes sobre um tópico específico, focando em no máximo 5 lançamentos atuais e relevantes.
*   **Ferramentas:** `google_search`

### Agente Planejador

*   **Instrução:** Analisar os lançamentos buscados, usar `google_search` para aprofundar a pesquisa sobre os pontos mais relevantes de cada um, escolher o tema mais relevante e criar um plano de post.
*   **Ferramentas:** `google_search`

### Agente Redator

*   **Instrução:** Escrever um rascunho de post para Instagram baseado no plano, com linguagem simples, engajadora e incluindo hashtags.
*   **Modelo:** `gemini-2.5-pro-preview-03-25`

### Agente Revisor

*   **Instrução:** Revisar o rascunho do post, focando em clareza, concisão, correção e adequação ao público jovem (18-30 anos) da Alura.
*   **Modelo:** `gemini-2.5-pro-preview-03-25`

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues para relatar bugs ou sugerir melhorias, ou enviar pull requests com suas alterações.

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## Autor

[evertonAlvaro]

Observações:

Substitua <url_do_seu_repositorio> e <nome_do_seu_seu_repositorio> pelos dados do seu repositório GitHub.
Crie um arquivo LICENSE no seu repositório e adicione os detalhes da licença escolhida.
Você pode adicionar uma seção de "Demonstração" com capturas de tela ou um pequeno GIF mostrando o sistema em funcionamento.
A seção "Pré-requisitos" e "Instalação" assume que você está rodando o código localmente. Se o principal uso for no Google Colab, você pode adaptar essas seções para refletir isso.
Considere adicionar uma seção "Estrutura do Projeto" se o seu código estiver dividido em múltiplos arquivos.
Este README fornece uma base sólida para apresentar o seu projeto no GitHub, explicando o que ele faz, como rodá-lo e seus componentes principais.

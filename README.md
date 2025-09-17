# Imersão Agentes de IA - Alura 

Este repositório documenta o projeto desenvolvido durante a **Imersão de Agentes de Inteligência Artificial** da Alura. O objetivo da imersão foi a construção de agentes de IA utilizando ferramentas de ponta como o modelo Gemini do Google e a biblioteca LangChain.

## 🚀 Sobre o Projeto

O projeto consiste na criação de um sistema de agentes de IA para auxiliar pesquisadores na área de Psicologia Social e Cognitiva. O sistema evolui ao longo de três aulas, começando com um agente simples e culminando em um fluxo de trabalho multi-agente robusto.

1.  **Aula 01 - Assistente de Pesquisa:** Foi desenvolvido um agente inicial capaz de receber uma ideia de pesquisa e estruturá-la como um Teste de Associação Implícita (IAT), gerando um JSON com a hipótese, categorias, atributos e estímulos sugeridos.
2.  **Aula 02 - Agente com RAG (Geração Aumentada por Recuperação):** O agente foi aprimorado com a técnica de RAG. Ele passou a consultar uma base de conhecimento de documentos científicos em PDF para validar e enriquecer a justificativa metodológica de suas respostas, tornando-as mais embasadas.
3.  **Aula 03 - Sistema Multi-Agente com LangGraph:** Na etapa final, foi construída uma arquitetura mais sofisticada com múltiplos agentes especializados, orquestrados pelo LangGraph. Este sistema implementa um fluxo de trabalho onde:
      * Um agente realiza uma **análise preliminar** da hipótese.
      * Outro agente gera uma **estrutura inicial** para o IAT.
      * Um terceiro agente, com RAG, **valida e enriquece** a estrutura com base na literatura científica.

## 🛠️ Tecnologias Utilizadas

Este projeto foi construído com as seguintes tecnologias e bibliotecas:

  * **Google Gemini:** Utilizado como o modelo de linguagem (LLM) principal para as tarefas de geração e análise.
  * **LangChain:** Framework central para o desenvolvimento dos agentes, manipulação de prompts e integração com o Gemini.
  * **LangChain Google GenAI:** Biblioteca para a integração específica com os modelos do Google.
  * **FAISS (Facebook AI Similarity Search):** Utilizado para a criação de um índice de vetores para a busca de similaridade nos documentos do RAG.
  * **LangGraph:** Biblioteca para a criação de sistemas multi-agente robustos e cíclicos.
  * **Pydantic:** Utilizado para a definição de esquemas de dados e validação da saída do modelo de linguagem, garantindo a geração de JSONs estruturados.
  * **PyMuPDF:** Biblioteca para o carregamento e extração de texto de documentos PDF.
  * **Google Colab:** Ambiente de desenvolvimento utilizado para a execução dos notebooks.

## ✨ Funcionalidades

  * **Análise Preliminar de Hipóteses:** O sistema avalia se uma ideia de pesquisa contém os elementos mínimos para a criação de um Teste de Associação Implícita (IAT).
  * **Estruturação Automática de IATs:** A partir de uma hipótese válida, o agente gera uma estrutura completa em JSON para um IAT, incluindo hipótese, categorias-alvo, atributos e estímulos sugeridos.
  * **Geração Aumentada por Recuperação (RAG):** O agente de validação consulta uma base de conhecimento de artigos científicos para enriquecer a justificativa metodológica e garantir que a estrutura do IAT esteja alinhada com as boas práticas científicas.
  * **Fluxo de Agentes Orquestrado:** Utiliza o LangGraph para criar um fluxo de trabalho condicional, onde diferentes agentes colaboram para produzir um resultado final mais completo e validado, ou para solicitar esclarecimentos ao usuário quando necessário.

## 📂 Estrutura do Projeto

  * `Imersão_Agentes_de_IA_do_Alura.ipynb`: Notebook principal contendo todo o código e as explicações das aulas.
      * **Aula 01:** Introdução ao Gemini e LangChain, e criação do primeiro agente para estruturação de IATs.
      * **Aula 02:** Implementação do RAG com FAISS e PyMuPDF para enriquecer o agente com conhecimento de uma base de documentos.
      * **Aula 03:** Criação de um sistema multi-agente com LangGraph para orquestrar o fluxo de análise, geração e validação.

## ⚙️ Como Executar

Para executar o projeto, siga os passos abaixo:

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/lumab23/imersao-agentes-ia.git
    ```
2.  **Abra o notebook:**
    Carregue o arquivo `Imersão_Agentes_de_IA_do_Alura.ipynb` no Google Colab ou em um ambiente Jupyter de sua preferência.
3.  **Instale as dependências:**
    Execute as células de instalação no início de cada seção do notebook para instalar as bibliotecas necessárias.
    ```python
    !pip install -q --upgrade langchain langchain-google-genai google-generativeai langchain_community faiss-cpu langchain-text-splitters pymupdf langgraph
    ```
4.  **Configure a Chave de API:**
    Para utilizar o modelo Gemini, você precisará de uma chave de API do Google AI Studio. No Google Colab, crie um *secret* chamado `GEMINI_API_KEY` com a sua chave.
5.  **Execute as células:**
    Execute as células do notebook em sequência para acompanhar o desenvolvimento e os resultados de cada aula.

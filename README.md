# 🎬 Emotional Movie Recommender (Cine-Curador IA)

Este é um chatbot inteligente desenvolvido em Python que recomenda filmes com base no estado emocional e nas preferências do usuário. Diferente de algoritmos de recomendação tradicionais baseados apenas em gêneros, este projeto utiliza **LLMs (Large Language Models)** para interpretar nuances sentimentais e buscar dados reais via API.

## 🚀 Tecnologias Utilizadas

* **Linguagem:** Python 3.10+
* **IA (LLM):** [Groq Cloud](https://console.groq.com/) utilizando o modelo `Llama-3.3-70b-versatile`.
* **Dados Cinematográficos:** [The Movie Database (TMDB) API](https://www.themoviedb.org/documentation/api).
* **Ambiente:** Desenvolvido inicialmente em ambiente `Google Colab` (.ipynb).

## 🧠 Como Funciona?

O sistema opera em um fluxo de três camadas:

1.  **Análise de Sentimento (IA):** O usuário descreve como se sente. O modelo Llama 3.3 processa essa entrada e identifica se o usuário precisa de um "Comfort Movie" (em caso de ansiedade/tristeza) ou algo mais enérgico.
2.  **Busca Técnica (API):** A IA gera nomes de filmes reais e famosos. O sistema então consulta a API do TMDB para obter:
    * Nota média da crítica.
    * Sinopse oficial em Português.
    * Ano de lançamento e Gêneros.
3.  **Localização de Streaming:** Utiliza o endpoint `watch/providers` para informar em quais plataformas (Netflix, Disney+, Prime Video, etc.) o filme está disponível no **Brasil**.

## 🛠️ Funcionalidades Principais

* ✅ **Recomendação por Humor:** Aceita prompts como "estou ansioso", "quero algo divertido" ou "frustrado e preciso de superação".
* ✅ **Refinamento de Busca:** Mantém o histórico da conversa, permitindo pedir "mais opções" ou "mudar o estilo" (ex: "quero algo mais antigo") sem perder o contexto.
* ✅ **Filtro Anti-Alucinação:** Configurado com temperatura baixa (`0.3 - 0.5`) para garantir que apenas filmes reais e lançados sejam sugeridos.
* ✅ **Onde Assistir:** Exibe as plataformas de streaming disponíveis para o território brasileiro.

## 📋 Pré-requisitos

Para rodar o projeto localmente ou no Colab, você precisará de:

1. Uma **Groq API Key** (Gratuita).
2. Uma **TMDB API Key** (Gratuita para desenvolvedores).

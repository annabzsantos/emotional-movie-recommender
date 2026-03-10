# 🎬 Emotional Movie Recommender

Um chatbot interativo com interface visual moderna que usa IA para recomendar filmes personalizados com base no seu humor e preferências, validando cada sugestão em tempo real via TMDB.

---

## Funcionalidades

* **Interface Moderna** — Web UI customizada com Gradio (estilo "Netflix Dark") com posters e cards detalhados.
* **Recomendações Inteligentes** — O modelo Llama-3.3 sugere 3 filmes reais baseados no seu estado emocional ou pedidos específicos.
* **Filtro de Qualidade** — Apenas filmes com **nota IMDb ≥ 7.0** e mais de **50.000 avaliações** são considerados pela IA.
* **Validação em Tempo Real** — Cada sugestão é cruzada com o banco de dados do TMDB (mínimo de 500 votos na plataforma) para evitar alucinações.
* **Onde Assistir** — Identificação automática de plataformas de streaming disponíveis no **Brasil** (Flatrate e Aluguel).
* **Histórico Inteligente** — O sistema mantém um registro da sessão para garantir que filmes já sugeridos não apareçam novamente.

---

## Tecnologias

| Tecnologia | Uso |
| --- | --- |
| [Groq API](https://groq.com) | LLM (llama-3.3-70b-versatile) para o motor de recomendação |
| [TMDB API](https://www.themoviedb.org/documentation/api) | Validação de dados, posters e provedores de streaming |
| [Gradio](https://www.gradio.app/) | Interface de usuário (Web UI) interativa e responsiva |
| Python 3.10+ | Linguagem principal e processamento de dados |

---

## Como usar

### 1. Configure as chaves de API no Google Colab

Acesse **Secrets** (🔑) no painel lateral do Colab e adicione:

```
GROQ_API_KEY  → sua chave da Groq
TMDB_API_KEY  → sua chave do TMDB

```

### 2. Instale as dependências

```bash
!pip install -q groq requests gradio

```

### 3. Execute o código

Rode todas as células. O link da interface aparecerá logo abaixo da última célula (utilize o link `inline` ou o link `public` gerado pelo Gradio).

### 4. Interaja na Interface

Ao abrir a interface **CinemaEmocional**, digite seu pedido no campo de texto:

* *"Quero um thriller que me deixe na ponta da cadeira"*
* *"Um filme para assistir com a família e comer pipoca"*

---

## Exemplos de pedidos

| Pedido | O que esperar |
| --- | --- |
| `"quero algo alegre"` | Comédias e animações com nota alta |
| `"algo triste, drama pesado"` | Dramas aclamados pela crítica |
| `"terror psicológico"` | Filmes de suspense com alta pontuação |
| `"ficção científica clássica"` | Sci-fi com grande volume de votos |

---

## Como funciona

```
Usuário envia pedido pela interface Gradio
         ↓
IA (Groq/Llama) analisa histórico e sugere 3 títulos (JSON)
         ↓
Busca e Validação no TMDB (Filtro: ≥ 500 votos)
         ↓
Busca de Provedores de Streaming (Região: BR)
         ↓
Renderização de Cards HTML personalizados (Poster, Nota, Sinopse)
         ↓
Atualização do Histórico Global (evita repetições)

```

---

## Requisitos

* Conta no [Groq Console](https://console.groq.com)
* Chave de API do [TMDB](https://www.google.com/search?q=https://www.themoviedb.org/settings/api)
* Ambiente Python ou Google Colab

---

## Observações

* **Nota:** A IA está instruída a priorizar filmes com nota superior a 7.0 para garantir a qualidade das indicações.
* **Streaming:** Se um filme não estiver disponível em plataformas de assinatura, o sistema tentará listar opções de aluguel ou informará a indisponibilidade no Brasil.
* **Normalização:** O sistema utiliza normalização Unicode para garantir que buscas com ou sem acento funcionem corretamente.

---

## Licença

Projeto de uso pessoal/educacional desenvolvido para a disciplina de Deep Learning do curso de Ciência da Computação.

## Autoras

* **Anna Bheatryz Martins dos Santos**
* **Mariana Sanchez Pedroni**

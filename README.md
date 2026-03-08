# 🎬 Emotional Movie Recommender

Um chatbot interativo que usa IA para recomendar filmes personalizados com base no seu humor e preferências, validando cada sugestão em tempo real via TMDB.

---

## ✨ Funcionalidades

- **Recomendações inteligentes** — A IA sugere 3 filmes reais baseados no seu pedido (humor, gênero, sentimento)
- **Validação automática** — Cada filme é verificado no TMDB (mínimo 500 votos), eliminando títulos inventados
- **Detalhes completos** — Gênero, ano, nota IMDb, número de votos e sinopse
- **Onde assistir** — Plataformas de streaming disponíveis no Brasil (via TMDB Watch Providers)
- **Histórico de sessão** — Filmes já sugeridos nunca são repetidos na mesma conversa
- **Correção de grafia** — Se a IA errar o título, o sistema tenta corrigir automaticamente

---

## 🛠️ Tecnologias

| Tecnologia | Uso |
|---|---|
| [Groq API](https://groq.com) | LLM (llama-3.3-70b-versatile) para sugestões de filmes |
| [TMDB API](https://www.themoviedb.org/documentation/api) | Validação, detalhes e disponibilidade de streaming |
| Python 3.10+ | Linguagem principal |
| Google Colab | Ambiente de execução |

---

## 🚀 Como usar

### 1. Configure as chaves de API no Google Colab

Acesse **Secrets** (🔑) no painel lateral do Colab e adicione:

```
GROQ_API_KEY   → sua chave da Groq
TMDB_API_KEY   → sua chave do TMDB
```

### 2. Instale as dependências

```bash
!pip install -q groq requests
```

### 3. Execute o notebook

Rode todas as células. O chatbot iniciará automaticamente no terminal interativo.

### 4. Converse!

```
🎬 Bem-vindo ao seu cinema particular! (Digite 'sair' para encerrar)

Você: quero algo pra chorar bastante
Você: me sugira um filme de ação anos 90
Você: algo leve pra assistir em família
```

Digite `sair` para encerrar a sessão.

---

## 💡 Exemplos de pedidos

| Pedido | O que esperar |
|---|---|
| `"quero algo alegre"` | Comédias e filmes leves |
| `"algo triste, drama pesado"` | Dramas emocionantes |
| `"terror que não seja muito violento"` | Terror psicológico / suspense |
| `"animação para criança"` | Animações infantis conhecidas |
| `"ficção científica clássica"` | Sci-fi com alto número de votos |
| `"quero animações"` *(após uma sugestão)* | Refina sem repetir anteriores |

---

## ⚙️ Como funciona

```
Usuário digita pedido
        ↓
IA (Groq/Llama) sugere 3 títulos reais em JSON
        ↓
Cada título é buscado no TMDB
        ↓
Validação: ≥ 500 votos + correspondência de título
        ↓
Se inválido → descartado com aviso
Se válido   → exibe detalhes + streaming BR
        ↓
Títulos adicionados ao histórico (não se repetem)
```

---

## 📋 Requisitos

- Conta no [Groq](https://console.groq.com) (plano gratuito disponível)
- Conta no [TMDB](https://www.themoviedb.org/signup) (API gratuita)
- Google Colab ou Python 3.10+ local

---

## ⚠️ Observações

- O chatbot usa o modelo `llama-3.3-70b-versatile` via Groq com `temperature=0.6` para balancear criatividade e precisão
- Filmes com menos de 500 votos no TMDB são automaticamente descartados
- A disponibilidade de streaming reflete o catálogo **brasileiro (BR)** no momento da consulta
- O histórico é mantido apenas durante a sessão — reiniciar o chatbot limpa o histórico

---

## 📄 Licença

Projeto de uso pessoal/educacional. APIs utilizadas sujeitas aos termos de serviço da [Groq](https://groq.com/terms) e do [TMDB](https://www.themoviedb.org/documentation/api/terms-of-use).

## Autoras
- Anna Bheatryz Martins dos Santos
- Mariana Sanchez Pedroni

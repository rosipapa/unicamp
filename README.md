# 🏥 CharityAI: Consulta de Instituições de Doação

Este projeto implementa um sistema de **Perguntas e Respostas sobre instituições de doação** utilizando **Large Language Models (LLMs)** e **consultas SPARQL**.  
A solução permite que usuários façam perguntas em linguagem natural, como:

> *"Onde posso doar roupas no centro?"*  
> *"Quais instituições aceitam alimentos no bairro Vila Mariana?"*

O modelo então traduz a pergunta em uma query SPARQL, consulta a base de dados, aplica técnicas de limpeza de resultados e retorna informações relevantes sobre instituições de doação.

---

## 🚀 Funcionalidades

- Conversão automática de **linguagem natural → SPARQL**  
- Consulta de uma base de dados de **instituições de doação por bairro**  
- Módulo de **limpeza de resultados** para maior consistência  
- Interface em **Gradio** com:
  - Aba de **Busca**
  - Aba de **Resultados**
  - Possibilidade futura de adicionar uma aba de **Ajuda** (explicações sobre o sistema)

---

## 📂 Estrutura do Projeto

- `CharityAI_rosilaine.ipynb` → Notebook principal com implementação e interface
- `data/` → Base de dados RDF/TTL com informações de instituições de doação (separar futuramente)
- `utils/` → Funções auxiliares (pré-processamento, geração de queries, limpeza)

---

## ⚙️ Tecnologias Utilizadas

- **Python 3.10+**
- **Gradio** → interface interativa
- **SPARQLWrapper** → execução de queries
- **Pandas** → manipulação de dados
- **Matplotlib** → visualização de métricas e resultados
- **LLM (Groq + LLaMA3)** → geração automática de queries SPARQL

---

## 📊 Fluxo de Funcionamento

1. Usuário escreve sua pergunta em linguagem natural.
2. O sistema envia a pergunta para o **LLM**, que gera uma query SPARQL.
3. A query é executada contra a base RDF.
4. Os resultados passam por um processo de **validação e limpeza**.
5. O sistema retorna a resposta para o usuário na interface Gradio.

---

## 📈 Exemplos de Uso

- Pergunta: *"Onde posso doar roupas no centro?"*  
  Resposta: *"Você pode doar na Casa da Acolhida, localizada na Rua X, Centro."*

- Pergunta: *"Quais instituições aceitam alimentos em Pinheiros?"*  
  Resposta: *"Instituto Solidariedade e ONG Alimente-se Bem aceitam doações de alimentos no bairro Pinheiros."*

---

## 🧪 Avaliação do Sistema

- **Métricas utilizadas**:
  - Taxa de acerto das queries SPARQL
  - Consistência dos resultados (respostas válidas vs inválidas)
  - Feedback qualitativo dos usuários

- **Observação**: os resultados podem variar a cada execução, já que dependem do **comportamento probabilístico da LLM**.  
  - Para reduzir variação: controle de parâmetros como `temperature`, `top_p` e estratégias de **prompt engineering**.  
  - Trabalhos relacionados, como *Investigating Large Language Models for Text-to-SPARQL Generation (D’Abramo et al., 2025)*, exploram técnicas para mitigar inconsistências na geração de queries.

---

## 📌 Próximos Passos

- Melhorar robustez da geração SPARQL (testar outras LLM e fine-tuning)
- Adicionar aba de **Ajuda** na interface, explicando como o sistema funciona

---

## 🧑‍💻 Autora

Projeto desenvolvido por **Rosilaine Silva** como parte de estudos em **IA aplicada a dados e produto**.  

---

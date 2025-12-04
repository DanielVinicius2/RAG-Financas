# 📄 RAG Drive Indexer – Sistema Automático de Busca Semântica com Supabase
# 🧩 Descrição do Problema

O projeto resolve o problema de armazenar, indexar e pesquisar documentos automaticamente a partir do Google Drive usando técnicas de RAG (Retrieval-Augmented Generation).

Sempre que um arquivo é enviado ou atualizado no Drive, o sistema:

 - Baixa o documento
 - Extrai o conteúdo
 - Gera embeddings usando OpenAI
 - Armazena tudo no banco vetorial do Supabase
 - Mantém sincronização automática 
 - Permite que um agente de IA responda perguntas com base nos documentos indexados

Esse processo cria uma base de conhecimento totalmente automatizada, capaz de responder perguntas sobre qualquer arquivo enviado.

# 🛠 Tecnologias Usadas

- Google Drive API — armazenamento dos arquivos e triggers automáticos
- OpenAI Embeddings & GPT — geração de vetores e respostas contextuais
- Supabase Vector Store (pgvector) — banco vetorial para busca semântica
- Workflows de automação — pipeline completo de ingestão, atualização e limpeza
- AI Agent — responsável por consultar o Supabase e responder perguntas usando RAG

# 🎥 Link do Vídeo (Demonstração)
https://www.loom.com/share/999d4556795543c7bb2f9acd8a8fd9b7

# ▶ Como Executar o Projeto
## 1. Configure as APIs

- Crie uma conta no Supabase
- Crie uma tabela vetorial com coluna embedding vector
- Habilite a extensão pgvector
- Copie sua URL e API Key

## 2. Configure o Google Drive

- Gere credenciais OAuth ou chave de serviço
- Defina uma pasta específica para monitoramento
- Conecte ao bloco Google Drive Trigger

## 3. Configure OpenAI

- Gere sua API key
- No workflow, conecte aos blocos:
- Embeddings OpenAI
- OpenAI Chat Model

## 4. Monte os Workflows (conforme a imagem enviada)
### O projeto é composto por 3 fluxos:

- 📌 A. Pipeline de Ingestão (Arquivo Criado)

  - Google Drive Trigger (fileCreated)
  - Download File
  - Default Data Loader
  - Embeddings OpenAI
  - Supabase Vector Store (Store1)

- 📌 B. Pipeline de Atualização (Arquivo Atualizado)

  - Google Drive Trigger (fileUpdated)
  - Delete Row (Supabase)
  - Download File
  - Default Data Loader
  - Embeddings OpenAI
  - Supabase Vector Store (Store2)

- 📌 C. Pipeline de Sincronização Automática

  - Schedule Trigger
  - Search Files & Folders
  - Aggregate
  - Get Many Rows (Supabase)
  - Delete Row (Supabase)

- 📌 D. AI Agent

  - Recebe perguntas
  - Faz busca semântica no Supabase
  - Usa GPT para responder baseado nos documentos

## 5. Inicie o agente de IA

Abra a interface de chat do seu agente e faça perguntas como:

- "Quais são os pontos principais do documento X?"
- "Explique o conteúdo do PDF sobre finanças."

## 📸 Prints / GIFs do Funcionamento

### 📌 Workflow Geral
<img width="925" height="642" alt="image" src="https://github.com/user-attachments/assets/e856b496-365a-409c-8609-883b6514b6f5" />


### 📌 Trigger de Arquivo Criado

<img width="737" height="277" alt="image" src="https://github.com/user-attachments/assets/9faefdc4-7c9b-4f59-a6c8-e45dab17a6a8" />

### 📌 Trigger de Atualização

<img width="981" height="303" alt="image" src="https://github.com/user-attachments/assets/f47cfcf4-409a-45cf-a973-4faa9f75ce03" />

### 📌 Trigger de Deleção

<img width="885" height="143" alt="image" src="https://github.com/user-attachments/assets/30fe8612-b5bd-464b-940a-deae8642a0c4" />


### 📌 AI Agent funcionando

<img width="555" height="398" alt="image" src="https://github.com/user-attachments/assets/596a97a4-db0d-4469-8d38-37ee3df8b931" />
<img width="552" height="394" alt="image" src="https://github.com/user-attachments/assets/3ef2836e-6c75-41ab-a06c-bfc6acd3a576" />
<img width="533" height="546" alt="image" src="https://github.com/user-attachments/assets/e196bf41-d147-4c36-bafc-873610467e4e" />
<img width="525" height="503" alt="image" src="https://github.com/user-attachments/assets/8c77d1b3-a8ed-4a60-ad73-9a69c703dd8e" />

### ✔ Status do Projeto

- ✔ Finalizado
- ✔ Automatizado
- ✔ Compatível com Supabase e OpenAI
- ✔ Busca semântica totalmente funcional

### Dupla: 

Daniel Vinicius Sobral Viana

João Vitor Vilarinho

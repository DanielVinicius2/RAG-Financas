# 📄 RAG Drive Indexer – Sistema Automático de Busca Semântica com Supabase
## 🧩 Descrição do Problema

O projeto resolve o problema de armazenar, indexar e pesquisar documentos automaticamente a partir do Google Drive usando técnicas de RAG (Retrieval-Augmented Generation).

Sempre que um arquivo é enviado ou atualizado no Drive, o sistema:

 - Baixa o documento
 - Extrai o conteúdo
 - Gera embeddings usando OpenAI
 - Armazena tudo no banco vetorial do Supabase
 - Mantém sincronização automática 
 - Permite que um agente de IA responda perguntas com base nos documentos indexados

Esse processo cria uma base de conhecimento totalmente automatizada, capaz de responder perguntas sobre qualquer arquivo enviado.

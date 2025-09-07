# #LEANN - RAG Local Ultra-Efficace 🧠

> LEANN : La révolution du RAG local avec 97% d'économie de stockage pour un Context Engineering privé et performant

**LEANN** (Low-storage Embedding Approximate Nearest Neighbor) est une base de données vectorielle révolutionnaire qui démocratise l'IA personnelle en transformant votre ordinateur portable en un système RAG puissant, capable d'indexer et de rechercher dans des millions de documents avec un stockage 97% plus petit que les solutions traditionnelles.

## 🚀 Démarrage rapide

**Installation simple :**

```bash
# Installation via pip
pip install leann

# Ou installation globale avec MCP pour Claude Code
uv tool install leann-core --with leann

# Ou depuis le repository
git clone https://github.com/yichuan-w/LEANN.git
cd leann && uv venv && source .venv/bin/activate && uv pip install leann
```

**Premier usage :**

```python
from leann import LeannBuilder, LeannSearcher, LeannChat

# 1. Construire un index
builder = LeannBuilder(backend_name="hnsw")
builder.add_text("Documentation technique sur les APIs REST")
builder.add_text("Guide d'utilisation des microservices")
builder.build_index("./knowledge_base")

# 2. Rechercher dans l'index
searcher = LeannSearcher("./knowledge_base")
results = searcher.search("comment utiliser les APIs", top_k=3)

# 3. Chat contextuel
chat = LeannChat("./knowledge_base")
response = chat.chat("Explique-moi les bonnes pratiques API")
```

---

## 🛠️ Fonctionnalités de Context Engineering

### 1. Indexation Multi-Sources ⭐

**Sources de données supportées :**

- **Documents** : PDF, TXT, Markdown, Word
- **Code source** : Tous langages avec chunking intelligent
- **Emails** : Apple Mail, Outlook, Gmail exports
- **Navigation** : Historique Chrome/Safari
- **Chat** : WeChat, Slack exports
- **Notes** : Notion, Obsidian, fichiers markdown

**Exemple d'indexation projet :**

```bash
# CLI officiel LEANN - Indexation multi-sources
leann build mon-projet --docs ./docs ./src ./tests

# Indexation avec types de fichiers spécifiques
leann build codebase --docs ./src --file-types .py,.js,.ts

# Indexation mixte fichiers et dossiers
leann build knowledge --docs ./readme.md ./src/ ./config.json
```

### 2. Intégration Claude Code MCP ⚡

**Configuration MCP native :**

```bash
# Intégration MCP avec Claude Code - commandes disponibles :
leann list                    # Voir tous les indexes
leann search index "requête"  # Rechercher dans un index
leann ask index "question"    # Poser une question à un index

# Exemple d'utilisation dans Claude Code :
# 1. Créer un index avec CLI
leann build codebase --docs ./src ./tests ./docs

# 2. Dans Claude Code, utiliser les commandes MCP intégrées
# Les outils /leann_search et /leann_list sont disponibles
```

**Workflow développeur optimisé :**

```bash
# 1. Indexer le projet complet avec CLI
leann build project --docs ./ --file-types .js,.ts,.md,.json

# 2. Recherche et Q&A via CLI ou MCP
leann search project "authentification patterns"
leann ask project "Comment implémenter OAuth dans ce code ?"

# 3. Dans Claude Code, utiliser l'intégration MCP native
# LEANN + Claude analysent le codebase contextualisé automatiquement
```

### 3. RAG Personnalisé Ultra-Léger 🔍

**Architecture révolutionnaire :**

- **Graph-based selective recomputation** : Calcul d'embeddings à la demande
- **High-degree preserving pruning** : Compression intelligente
- **97% reduction storage** : Index <5% de la taille des données brutes
- **90% top-3 recall** : Précision maintenue en <2 secondes

**Backends supportés :**

```python
# HNSW pour performance générale
builder = LeannBuilder(backend_name="hnsw")

# DiskANN pour très gros volumes  
builder = LeannBuilder(backend_name="diskann")

# Configuration avancée
builder = LeannBuilder(
    backend_name="hnsw",
    embedding_model="sentence-transformers/all-MiniLM-L6-v2",
    chunk_size=512,
    overlap=50
)
```

### 4. Context Engineering Intelligent 🎯

**Chunking sémantique avancé :**

```python
# Préservation de la structure pour le code
builder.add_directory(
    "./src", 
    file_types=["*.py", "*.js"],
    chunking_strategy="semantic_blocks",  # Respect des fonctions/classes
    preserve_context=True,                # Garde les imports/dependencies  
    max_chunk_size=1024
)

# Chunking adaptatif selon le type de contenu
builder.add_documents(
    "./docs",
    adaptive_chunking=True,    # S'adapte au format (PDF vs MD vs TXT)
    semantic_overlap=True,     # Overlap basé sur le sens, pas la taille
    preserve_headers=True      # Garde la hiérarchie des sections
)
```

**Recherche contextuelle multi-modale :**

```python
# Recherche hybride sémantique + keyword
results = searcher.hybrid_search(
    query="authentification JWT",
    semantic_weight=0.7,
    keyword_weight=0.3,
    filters={"file_type": "python", "recent": True}
)

# Recherche avec contexte conversationnel
chat_results = chat.contextual_search(
    query="Comment implémenter la validation?",
    conversation_history=previous_messages,
    expand_context=True
)
```

---

## 🔍 Cas d'usage Context Engineering

### 1. Assistant développeur personnel

**Setup projet complet :**

```bash
# Indexation exhaustive projet avec CLI LEANN
leann build dev-assistant --docs ./src ./docs ./tests ./package.json ./tsconfig.json

# Indexation spécifique avec types de fichiers
leann build codebase --docs ./src ./tests --file-types .js,.ts,.tsx,.json

# Indexation documentation seule
leann build docs --docs ./docs ./README.md
```

**Usage avec Claude Code :**

```bash
# Dans Claude, avec LEANN MCP activé :
# Les commandes sont intégrées automatiquement
# "Analyse ce bug en utilisant le contexte du projet"
# LEANN fournit contexte : code + docs + tests indexés
# Claude génère solution contextuelle basée sur l'index dev-assistant
```

### 2. Documentation intelligente

**Indexation documentation distribuée :**

```python
# Multi-sources documentation
builder.add_confluence_export("./confluence_export")
builder.add_notion_backup("./notion_backup") 
builder.add_wiki_markdown("./internal_wiki")
builder.add_api_specs("./openapi_specs", format="openapi")
builder.build_index("./company_knowledge")

# Recherche documentaire assistée
chat = LeannChat("./company_knowledge")
response = chat.chat(
    "Procédure de déploiement pour l'environnement staging",
    include_sources=True,
    confidence_threshold=0.8
)
```

### 3. Analyse de codebase legacy

**Exploration guidée par IA :**

```bash
# Indexation codebase legacy avec métadonnées
leann build legacy-analysis \
  --source ./legacy-app \
  --include-git-blame true \
  --analyze-dependencies true \
  --extract-patterns true \
  --tech-debt-detection true
```

**Requêtes d'analyse avancées :**

```python
# Recherche de patterns problématiques
problematic_patterns = searcher.search(
    "SQL injection vulnerability patterns",
    filters={"language": "php", "confidence": ">0.9"}
)

# Analyse d'impact pour refactoring  
impact_analysis = searcher.impact_search(
    target_function="legacy_user_auth",
    analysis_depth=3,  # 3 niveaux de dépendances
    include_tests=True
)
```

### 4. RAG multilingue et culturel

**Context Engineering international :**

```python
# Support multilingue avec préservation contextuelle
builder = LeannBuilder(
    embedding_model="sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2",
    language_detection=True,
    cultural_context_preservation=True
)

# Ajout contenus multilingues
builder.add_documents("./docs_fr", language="fr")
builder.add_documents("./docs_en", language="en") 
builder.add_documents("./docs_es", language="es")

# Recherche cross-linguale avec contexte culturel
results = searcher.multilingual_search(
    query="bonnes pratiques sécurité",
    target_languages=["fr", "en"],
    cultural_adaptation=True
)
```

---

## 💡 Techniques avancées découvertes

### 1. Index composites pour Context Engineering

**Architecture multi-index :**

```python
# Index spécialisés par domaine
code_index = LeannBuilder("hnsw").build_index("./code_knowledge")
docs_index = LeannBuilder("diskann").build_index("./docs_knowledge")  
comms_index = LeannBuilder("hnsw").build_index("./communications")

# Recherche orchestrée multi-index
from leann import MultiIndexSearcher
orchestrator = MultiIndexSearcher([
    ("code", code_index, 0.4),      # 40% poids code
    ("docs", docs_index, 0.4),      # 40% poids documentation  
    ("comms", comms_index, 0.2)     # 20% poids communications
])

# Requête cross-domaine
results = orchestrator.orchestrated_search(
    "implémentation authentification OAuth",
    merge_strategy="weighted_relevance",
    deduplicate=True
)
```

### 2. RAG adaptatif selon le contexte

**Context-aware embedding :**

```python
# Embeddings différents selon le type de requête
adaptive_builder = LeannBuilder()
adaptive_builder.add_context_embeddings({
    "code": "microsoft/CodeBERT-base",
    "docs": "sentence-transformers/all-mpnet-base-v2", 
    "support": "sentence-transformers/all-MiniLM-L12-v2"
})

# Auto-classification et routing intelligent
def smart_search(query):
    query_type = adaptive_builder.classify_query(query)
    optimal_model = adaptive_builder.select_model(query_type)
    return optimal_model.search(query, context_aware=True)
```

### 3. Monitoring et optimisation performance

**Analytics RAG intégrés :**

```python
# Monitoring des performances
from leann.analytics import PerformanceMonitor

monitor = PerformanceMonitor("./knowledge_base")
stats = monitor.get_stats()
# {
#   "avg_search_time": "0.15s",
#   "hit_rate": 0.87,
#   "storage_efficiency": "97.3%",
#   "most_queried_topics": ["auth", "deployment", "api"]
# }

# Optimisation automatique
optimizer = monitor.auto_optimize(
    target_latency="<100ms",
    target_accuracy=">90%",
    retrain_threshold=0.1
)
```

---

## 🔧 Configuration et optimisation

### Configuration recommandée par cas d'usage

**Développeur solo :**

```yaml
# ~/.leann/config.yaml
embedding_model: "sentence-transformers/all-MiniLM-L6-v2"
backend: "hnsw"
max_index_size: "1GB"
auto_cleanup: true
privacy_mode: true  # Aucune donnée cloud
```

**Équipe développement :**

```yaml
shared_indexes: "./team_knowledge"
sync_strategy: "git_based"
collaborative_chunking: true
team_embeddings: "shared_vocabulary"
access_control: "role_based"
```

**Enterprise :**

```yaml
backend: "diskann"  # Pour gros volumes
distributed_indexing: true
encryption_at_rest: true
audit_logging: true
compliance_mode: "gdpr"
```

### Templates d'indexation ready-to-use

**Template projet web :**

```bash
#!/bin/bash
# index_web_project.sh
leann build web-project \
  --source "./src" \
  --docs "./docs" \
  --configs "./*.json,./*.yaml" \
  --include "*.js,*.ts,*.jsx,*.tsx,*.css,*.md" \
  --exclude "node_modules,dist,coverage" \
  --chunk-strategy "component_based" \
  --preserve-jsx-context true
```

**Template API documentation :**

```python
# template_api_docs.py
def index_api_docs(api_spec_dir, output_index):
    builder = LeannBuilder(backend_name="hnsw")
  
    # OpenAPI specs avec préservation structure
    builder.add_openapi_specs(f"{api_spec_dir}/*.yaml", 
                             preserve_endpoints=True)
  
    # Postman collections
    builder.add_postman_collections(f"{api_spec_dir}/*.json")
  
    # Documentation Swagger/docs
    builder.add_api_docs(f"{api_spec_dir}/docs", 
                        format="swagger")
  
    return builder.build_index(output_index)
```

---

## ⚡ Performance et métriques

**Benchmarks réels :**

- **Storage** : 97% réduction vs bases vectorielles traditionnelles
- **Speed** : <2s recherche dans millions de documents
- **Accuracy** : 90% top-3 recall maintenu
- **Memory** : <500MB RAM pour 100K documents
- **Privacy** : 100% local, zéro cloud

**Comparaison outils similaires :**

| Outil           | Storage       | Speed | Privacy    | Context Engineering |
| --------------- | ------------- | ----- | ---------- | ------------------- |
| **LEANN** | 97% économie | <2s   | 100% local | ⭐⭐⭐⭐⭐          |
| Pinecone        | Standard      | <1s   | Cloud      | ⭐⭐⭐              |
| Weaviate        | Standard      | <3s   | Hybride    | ⭐⭐⭐⭐            |
| Chroma          | Standard      | <2s   | Local      | ⭐⭐⭐⭐            |

---

## 🔗 Ressources et écosystème

### Documentation officielle

- **[GitHub Repository](https://github.com/yichuan-w/LEANN)** - Code source et examples
- **[PyPI Package](https://pypi.org/project/leann/)** - Installation et releases
- **[Tutorial Complet](https://thakicloud.github.io/en/tutorials/leann-vector-index-complete-tutorial/)** - Guide approfondi

### Intégrations et outils

- **[Claude Code MCP](/)** - Intégration native pour développeurs
- **[AnythingLLM](https://github.com/Mintplex-Labs/anything-llm/issues/4265)** - Intégration RAG platform
- **[LanceDB](https://github.com/lancedb/lancedb)** - Alternative complémentaire

### Communauté et support

- **Issues GitHub** pour bugs et feature requests
- **Discussions** pour questions et partage d'expérience
- **Examples** dans le repository pour cas d'usage courants

---

## 🎯 Prochaines étapes

1. **[Installation et premier index](setup-guide.md)** 🚧 *TODO* - Guide step-by-step
2. **[Intégration Claude Code](claude-code-integration.md)** 🚧 *TODO* - MCP setup et workflows
3. **[Templates par technologie](templates/)** 🚧 *TODO* - Configurations prêtes à l'emploi
4. **[Patterns entreprise](enterprise-patterns.md)** 🚧 *TODO* - Déploiement et gouvernance

> 💡 **Astuce finale :** LEANN révolutionne le Context Engineering local en rendant le RAG accessible sur tous les appareils. Parfait pour développeurs soucieux de la confidentialité et équipes voulant garder le contrôle total de leur knowledge base.

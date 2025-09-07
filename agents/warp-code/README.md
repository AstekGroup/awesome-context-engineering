# Warp - Context Engineering Guide 🎼

> Guide pour maîtriser le Context Engineering avec Warp, l'environnement de développement agentique

Warp est un terminal moderne construit en Rust qui intègre l'IA directement dans l'interface. Il se positionne comme un "environnement de développement agentique" où les agents IA peuvent écrire du code, débugger, et utiliser le contexte de votre codebase pour améliorer la productivité.

## 🚀 Démarrage rapide

**Installation et configuration :**
```bash
# Installation via site officiel
https://www.warp.dev/

# Disponible sur macOS, Linux, et Windows
# Installation inclut automatiquement les fonctionnalités IA
```

**Documentation officielle** → [docs.warp.dev](https://docs.warp.dev/)

---

## 🛠️ Outils officiels de Context Engineering

### 1. Codebase Context - Indexation intelligente ⭐

**Indexation automatique des projets :**
- **Auto-scan des repos Git** : Création d'index embeddings pour compréhension IA
- **Multi-repo support** : Référence croisée entre plusieurs projets indexés
- **Filtrage intelligent** : Support `.gitignore`, `.warpindexingignore`, `.cursorignore`
- **Sync automatique** : Re-indexation lors de conversations agent ou manuellement

**Optimisation Context Engineering :**
```bash
# Commandes d'indexation
/index                    # Indexer le codebase actuel
/init                     # Indexer + générer WARP.md projet

# Contrôle de l'indexation
# .warpindexingignore - fichier racine pour exclure
node_modules/
*.log
build/
dist/
```

### 2. Contexte multimodal pour Agents 🧠

**Types de contexte attachables :**
- **Blocks as Context** : Attacher blocs de terminal aux prompts
- **Images as Context** : Upload d'images (screenshots, diagrammes, mockups)
- **URLs as Context** : Pages web, documentation, issues GitHub
- **Text Selections** : Sélections de texte depuis l'éditeur
- **Syntaxe @** : Référencer fichiers, dossiers, symboles code

**Utilisation pratique :**
```bash
# Attachement de contexte lors de conversations agent
@src/components/Button.tsx     # Référence fichier spécifique
@docs/                        # Référence dossier documentation
# + Drag & drop d'images directement dans l'interface
# + Copier-coller d'URLs dans les prompts
```

### 3. Slash Commands - Raccourcis Context Engineering 🎨

**Commandes contextuelles intégrées :**
- **`/add-mcp`** : Ajouter serveurs MCP (Model Context Protocol)
- **`/add-prompt`** : Créer prompts d'agent réutilisables
- **`/add-rule`** : Définir règles globales pour les agents
- **`/diff-review`** : Ouvrir le panneau de review des diffs
- **`/open-project-rules`** : Éditer les règles spécifiques au projet
- **`/view-mcp`** : Voir le statut des serveurs MCP

**Workflow optimisé :**
```bash
# Accès rapide via '/' en mode Agent
/init                         # Setup complet nouveau projet
/add-rule "Always use TypeScript strict mode"
/add-prompt "Code Review" "Review this code for best practices"
```

### 4. Active AI - IA proactive 🎵

**Assistance contextuelle automatique :**
- **Prompt Suggestions** : Suggestions de prompts selon le contexte terminal
- **Next Command** : Prédiction de la prochaine commande selon l'historique
- **Code Diffs automatiques** : Corrections suggérées pour erreurs compilateur
- **Secret Redaction** : Protection automatique des données sensibles

**Intégration transparente :**
```bash
# Active AI fonctionne en arrière-plan
# Suggestions illimitées (ne comptent pas dans les limites API)
# Désactivable dans Settings > AI
# Contextuel selon votre session et historique
```

### 5. Workflows et Code Editor intégrés 🤝

**Workflows YAML personnalisables :**
```yaml
# ~/.warp/workflows/deploy.yaml
name: "Deploy to Production"
description: "Full deployment pipeline"
command: |
  npm run build &&
  npm run test &&
  docker build -t app . &&
  kubectl apply -f k8s/
tags: ["deployment", "production"]
```

**Code Editor contexte-aware :**
- **Ouverture rapide** : `CMD+O`, file tree, ou liens depuis terminal
- **Édition in-flow** : Modifications rapides de code généré par agents
- **Syntax highlighting** : Support multi-langages
- **Vim keybindings** : Navigation familière
- **Intégration agents** : Édition collaborative avec IA

---

## 🔍 Découvertes de la communauté

### 1. Optimisation de l'expérience développeur 🌊

**Problème identifié :** Complexité de gestion des environnements de développement multiples

**Solutions Warp :**

**Environnements unifiés :**
```bash
# Warp centralise contexte et outils en un environnement
# Agents IA intégrés pour assistance continue
# Interface moderne qui remplace le terminal traditionnel
```

**Workflows personnalisés :**
```yaml
# Création via interface Warp ou fichiers YAML
# Repository communautaire disponible
# Format standardisé pour partage équipe
# Intégration avec commands.dev pour découverte
```

### 2. Patterns avancés de Context Engineering 🧩

**Stratégies de contexte découvertes :**

**Contexte sélectionné pour debugging :**
```bash
# 1. Copier l'erreur dans le terminal (selection as context)
# 2. Ouvrir le fichier problématique dans l'éditeur  
# 3. Sélectionner la fonction buggée
# 4. Prompt : "@src/utils/auth.ts Analyse cette erreur avec le contexte"
# 5. Agent reçoit : erreur + code + structure fichier
```

**Workflow images pour UI :**
```bash
# Drag & drop d'une maquette/screenshot dans Warp
# Prompt : "Génère le composant React pour cette UI"
# Agent analyse l'image + structure existante du projet
# Génère code contextualisé selon les conventions détectées
```

### 3. Développement assisté par agents 🎯

**Méthodologie émergente basée sur les agents IA :**

**Phase 1 - Analyse de code :**
```bash
# Agents analysent automatiquement le codebase
# Suggestions contextuelles selon le projet
# Détection intelligente des patterns existants
```

**Phase 2 - Génération de code :**
```bash
# Écriture de code directement par les agents
# Respect des conventions du projet
# Intégration avec l'environnement existant
```

**Phase 3 - Debug collaboratif :**
```bash  
# Agents identifient et corrigent automatiquement les bugs
# Suggestions de tests et validation
# Amélioration continue du code
```

### 4. Intégration avec l'écosystème de développement 🔗

**Découvertes d'intégration :**

**Warp + VS Code :**
```bash
# Ouverture contextuelle
> "ouvre le composant qui plante"
AI: code src/components/ProblemComponent.tsx

# Debug synchronisé
> "debug dans VS Code ce que je viens de lancer"
AI: Lance debugger VS Code sur le bon process
```

**Warp + Git workflows :**
```bash
# Commits contextuels
> "commit ce que je viens de faire"  
AI: git add . && git commit -m "fix(auth): resolve OAuth callback issue"

# Branch management intelligent
> "nouvelle branche pour cette feature"
AI: git checkout -b feature/user-profile-$(date +%Y%m%d)
```

### 5. Performance et optimisation "vibe" 🚀

**Techniques de performance découvertes :**

**Lazy Context Loading :**
```bash
# Chargement progressif du contexte
warp config set context.mode="lazy"
# Contexte léger au démarrage, enrichi selon les besoins
```

**Predictive Command Caching :**
```bash
# Cache intelligent des commandes probables
warp config set prediction.cache=true  
# 3x plus rapide sur les suggestions fréquentes
```

---

## 📁 Templates battle-tested

### Template de workflow Warp

```yaml
# Configuration workflow exemple
name: "React Development Setup"
description: "Initialize React development environment"
command: |
  npm create react-app my-app --template typescript &&
  cd my-app &&
  npm start
tags: ["react", "typescript", "frontend"]
author: "warp-community"
source_url: "https://github.com/warpdotdev/workflows"
```

### Exemples de workflows communautaires

```yaml
# Workflow Docker Compose
name: "Docker Development"
command: "docker-compose up -d && docker-compose logs -f"
description: "Start Docker services and follow logs"

# Workflow Git
name: "Git Status Overview" 
command: "git status && git log --oneline -10"
description: "Quick git repository overview"

# Workflow Test
name: "Run Tests with Coverage"
command: "npm test -- --coverage && open coverage/lcov-report/index.html"
description: "Execute tests and open coverage report"
```

---

## 💡 Cas d'usage avancés

### Session de développement avec agents

```bash
# 1. Analyse du contexte
> "Analyse ce codebase React et identifie les améliorations possibles"
Agent: [Analyse la structure] Détection de patterns, suggestions d'optimisation

# 2. Génération de code
> "Crée un composant de profil utilisateur avec TypeScript"
Agent: [Génère le code] Respect des conventions, intégration des types existants

# 3. Tests automatiques
> "Ajoute des tests pour ce composant"
Agent: [Génère les tests] Jest + React Testing Library selon la config

# 4. Review et intégration
> "Intègre ce composant dans l'application"
Agent: [Modifie les fichiers] Import, routing, mise à jour de la navigation
```

### Collaboration d'équipe avec Warp Drive

```bash
# Partage via Warp Drive
# 1. Notebooks partagés avec documentation exécutable
# 2. Workflows d'équipe standardisés
# 3. Variables d'environnement centralisées
# 4. Prompts réutilisables pour l'équipe
# 5. Collaboration web temps réel

# Onboarding automatique via Drive
# Accès immédiat aux ressources partagées
# Synchronisation des environnements
```

### Debug intelligent avec agents

```bash
# Analyse automatique d'erreurs
> "Cette erreur TypeScript est complexe, aide-moi"
Agent: [Analyse le code] Identification du type manquant
        Proposition de correction automatique
        Explication du problème et solution
    
# Collaboration via Drive
> "Partage cette solution avec l'équipe"
Agent: [Sauvegarde dans Drive] Notebook créé avec contexte + solution
       Accessible à toute l'équipe pour référence future
```

---

## 🔗 Ressources et communauté

### Documentation officielle
- **[Warp Docs](https://docs.warp.dev/)** - Documentation complète
- **[Warp AI Guide](https://docs.warp.dev/features/ai)** - Guide spécifique IA
- **[Warp Blog](https://www.warp.dev/blog)** - Actualités et cas d'usage

### Communauté et ressources
- **[Warp Discord](https://discord.com/invite/warpdotdev)** - Support et échanges temps réel

### Intégrations et outils
- **[Warp Themes](https://github.com/warpdotdev/themes)** - Thèmes communautaires (866+ stars)
- **[Warp Workflows](https://github.com/warpdotdev/workflows)** - Workflows partagés et commands.dev

---

## 🎯 Prochaines étapes

1. **[Configuration optimale](setup-guide.md)** 🚧 *TODO* - Guide d'installation et configuration
2. **[Workflows avancés](workflows/)** 🚧 *TODO* - Collection de workflows par domaine
3. **[Vibe Profiles](vibe-profiles.md)** 🚧 *TODO* - Profils optimisés par style de développement  
4. **[Team Setup](team-setup.md)** 🚧 *TODO* - Configuration collaborative

> 💡 **Astuce finale :** Warp Code excelle dans le "vibe coding" - laissez l'IA s'adapter à votre style et humeur de développement. Plus vous l'utilisez, plus elle comprend votre flow naturel.
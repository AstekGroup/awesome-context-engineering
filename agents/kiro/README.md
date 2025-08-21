# Kiro - Context Engineering Guide 🤖

> Guide complet pour maîtriser le Context Engineering avec l'IDE agentique Kiro (AWS Preview)

Kiro est un IDE agentique expérimental d'AWS, basé sur VS Code (Code-OSS). Il se distingue par son développement **spec-driven**, ses **Agent Hooks** automatisés, et ses **Steering Files** modulaires pour un contexte persistant structuré.

## 🚀 Démarrage rapide

**Installation et configuration :**
```bash
# Installation macOS via Homebrew
brew install aws/tap/kiro

# Authentification (Google, GitHub, Builder ID, AWS SSO)
kiro login

# Alternative : Téléchargement direct
https://kiro.dev/
```

**Documentation officielle** → [kiro.dev/docs](https://kiro.dev/docs/)

---

## 🛠️ Outils officiels de Context Engineering

### 1. Steering Files (Contexte persistant modulaire) ⭐

**Kiro utilise des fichiers Markdown structurés pour le contexte projet :**

```
projet/
├── .kiro/
│   └── steering/
│       ├── product.md           # Vision produit et objectifs métier
│       ├── tech.md             # Stack technique et contraintes
│       ├── structure.md        # Architecture et conventions
│       ├── api-standards.md    # Standards API (optionnel)
│       └── ui-guidelines.md    # Guidelines UI/UX (optionnel)
```

**Génération automatique :** Kiro crée les 3 fichiers de base (product.md, tech.md, structure.md) lors de l'initialisation projet.

**Avantages uniques :**
- **Contexte persistant** : Plus besoin d'expliquer les conventions à chaque session
- **Cohérence équipe** : Tous les développeurs travaillent avec les mêmes standards
- **Scalabilité** : Documentation qui évolue avec le projet
- **Réduction répétition** : Kiro se souvient des préférences établies

### 2. Modes d'inclusion conditionnelle (3 modes) 🎯

**Innovation Kiro : Contrôle granulaire du contexte via front matter YAML**

**Mode 1 - Always (inclusion systématique) :**
```yaml
---
inclusion: always
---

# Ce fichier est TOUJOURS inclus dans le prompt
Standards universels, règles critiques du projet
```

**Mode 2 - fileMatch (inclusion conditionnelle) :**
```yaml
---
inclusion: fileMatch
fileMatchPattern: "src/frontend/**"
---

# Inclus SEULEMENT pour fichiers frontend
Guidelines React, patterns UI, standards accessibilité
```

**Mode 3 - manual (inclusion sur demande) :**
```yaml
---
inclusion: manual
---

# Inclus SEULEMENT si mentionné via #nom-du-fichier
Guide troubleshooting, patterns avancés, documentation détaillée
```

### 3. Références dynamiques aux fichiers live 📄

**Syntaxe spéciale `#[[file:path]]` pour inclusion temps réel :**

```markdown
# Dans api-standards.md
## Contrat API actuel
#[[file:api/openapi.yaml]]

## Configuration base de données  
#[[file:config/database.json]]

## Variables d'environnement
#[[file:.env.example]]
```

**Avantages :**
- **Vérité terrain** : Toujours la dernière version des fichiers
- **Cohérence** : Impossible d'avoir documentation obsolète
- **Automatisation** : Pas de maintenance manuelle des références

### 4. Développement Spec-Driven (méthodologie structurée) 📋

**Workflow Spec-Driven en 3 phases :**

**Phase 1 - Requirements (requirements.md) :**
```markdown
# Format EARS (Easy Approach to Requirements Syntax)
When [trigger], the system shall [action] where [condition].

Example:
When a user clicks the login button, 
the system shall authenticate credentials 
where the email format is valid.
```

**Phase 2 - Design (design.md) :**
```markdown
## Architecture technique
- Frontend: React 18 + TypeScript + Next.js
- Backend: Node.js + Express + Prisma
- Database: PostgreSQL + Redis cache
- Auth: JWT + refresh tokens

## Patterns d'implémentation
- Clean Architecture (Domain/Application/Infrastructure)
- Repository pattern pour data access
- CQRS pour séparation lecture/écriture
```

**Phase 3 - Tasks (tasks.md) :**
```markdown
## Tâches d'implémentation
- [ ] Créer modèles User et Auth
- [ ] Implémenter routes authentification  
- [ ] Ajouter middleware JWT
- [ ] Tests unitaires + intégration
- [ ] Documentation API Swagger
```

**Exécution guidée :** Kiro implémente chaque tâche selon la spec validée.

### 5. Agent Hooks (automatisation intelligente) 🔄

**Hooks = Automatisation déclenchée par événements IDE**

**Configuration Agent Hooks :**
```yaml
# .kiro/hooks/auto-test.yaml
trigger: file_saved
pattern: "src/components/**/*.tsx"  
action: |
  Génère ou met à jour automatiquement le fichier de test 
  correspondant selon les standards du projet
```

**Exemples d'hooks courants :**
```yaml
# Hook documentation automatique
trigger: file_created
pattern: "src/api/**/*.ts"
action: |
  Génère documentation Swagger pour les nouveaux endpoints
  Met à jour le fichier openapi.yaml
  
# Hook sécurité pre-commit  
trigger: pre_commit
action: |
  Scanne les fichiers pour détecter secrets/clés API
  Bloque commit si vulnérabilités détectées
  
# Hook optimisation images
trigger: file_saved  
pattern: "**/*.{jpg,png,gif}"
action: |
  Optimise automatiquement les images ajoutées
  Génère formats WebP et AVIF
```

### 6. Modes Vibe Coding vs Code with Spec 🎨

**Deux modes de conversation distincts :**

**Vibe Coding (mode libre) :**
- Brainstorming et exploration créative
- Pas de contraintes spec strictes
- Idéal pour prototypage et idéation
- Liberté d'expérimentation

**Code with Spec (mode guidé) :**
- Verrouillé sur la spec actuelle (requirements/design/tasks)
- Référence constante aux fichiers de spec
- Implémentation stricte selon plan validé
- Workflow de production discipliné

**Bascule en un clic :** Interface pour changer de mode selon contexte.

### 7. Privacy-First et MCP Integration 🔐

**Approche Privacy-First :**
- Code reste local par défaut
- Steering files et specs stockés localement
- Connexion services externes seulement si activée explicitement
- Contrôle granulaire des données partagées

**MCP Servers configurables :**
```json
// Dans settings Kiro
{
  "mcpServers": {
    "brave-search": {
      "enabled": true,
      "apiKey": "your-brave-key"  
    },
    "notion": {
      "enabled": false,
      "databaseId": "your-notion-db"
    }
  }
}
```

---

## 🔍 Découvertes de la communauté

### 1. AWS DNA d'entreprise et méthodologie 🏢

**Contexte découvert :** Kiro vient d'AWS avec un ADN enterprise et méthodologie rigoureuse.

**Feedback communauté (béta-testeurs AWS) :**
- **Spec-driven** peut sembler lourd pour petits scripts
- **Excellent** pour projets d'équipe et applications complexes
- **Méthodologie AWS** transparaît (rigueur, scalabilité, gouvernance)

**Équilibre trouvé :** Mode Vibe Coding pour usage rapide + Spec mode pour production.

### 2. Personnalisation avancée des prompts système 🛠️

**Limitation officielle :** Prompt système Kiro non directement modifiable.

**Workaround communautaire découvert :**
```markdown
# Fichier persona.md dans .kiro/steering/
---
inclusion: always
---

# Personnalité et rôle de l'agent
Tu es un développeur senior expert en sécurité logicielle.
Tu privilégies les solutions robustes et maintenables.
Tu expliques toujours tes choix techniques.
```

**Résultat :** Enrichissement du rôle de l'agent via steering files.

### 3. Intégration écosystème AWS 🌐

**Découverte :** Kiro s'intègre naturellement avec services AWS.

**Intégrations testées par la communauté :**
```yaml
# Hooks intégrés AWS  
- CodeCatalyst: Sync tasks Kiro ↔ Issues CodeCatalyst
- CodeWhisperer: Utilisation comme modèle backend
- CodePipeline: Déclenchement builds via Agent Hooks
- CloudFormation: Génération IaC depuis design.md
```

**Avantage entreprise :** Workflow Kiro → AWS natif pour équipes entreprise.

### 4. Usage créatif hors développement 📝

**Découverte inattendue :** Utilisation pour documentation technique.

**Exemple communautaire :**
```markdown
# Spec pour documentation (mode détourné)
Requirements: "Écrire guide architecture pour module X"
Design: Structure documentation, public cible, niveau technique
Tasks: Rédaction sections, diagrammes, exemples code

→ Kiro génère documentation structurée et cohérente
```

**Cas d'usage étendus :** Specs pour formation, processus métier, guides techniques.

### 5. Optimisation des Steering Files 📏

**Problème découvert :** Steering Files volumineux impactent performance.

**Stratégies d'optimisation communautaires :**

**Hiérarchie intelligente :**
```markdown
# .kiro/steering/core.md (20-30 lignes max)
---
inclusion: always
---
Stack: React + TypeScript + Node.js
Patterns: Clean Architecture + TDD
Standards: ESLint Airbnb + Prettier

# .kiro/steering/detailed-frontend.md (mode fileMatch)
---
inclusion: fileMatch  
fileMatchPattern: "src/frontend/**"
---
[Détails patterns React spécifiques]
```

**Règle communautaire :** Core files <50 lignes, detailed files <200 lignes.

### 6. Limitations Preview et feedback 🚧

**Statut Preview :** Kiro en preview publique avec limitations.

**Feedback communauté → Améliorations :**
- **Steering Files reload** : Détection changements temps réel améliorée
- **Agent Hooks debug** : Interface debug pour hooks qui échouent
- **Spec templates** : Templates pré-configurés par type projet
- **Performance optimization** : Cache intelligent pour gros projets

**Évolution rapide :** Releases fréquentes intégrant feedback utilisateurs.

---

## 📁 Templates battle-tested

### Template product.md (vision métier)

```markdown
# Product Vision - [NOM_PROJET]

## 🎯 Objectif métier  
Application de [DOMAINE] permettant aux utilisateurs de [OBJECTIF_PRINCIPAL].

**Public cible :** [DESCRIPTION_UTILISATEURS]
**Proposition de valeur :** [VALEUR_UNIQUE]

## 📊 Métriques de succès
- **Adoption :** [METRIC] utilisateurs actifs en [PERIOD]  
- **Engagement :** [METRIC] sessions par utilisateur/semaine
- **Performance :** Temps de réponse <200ms
- **Qualité :** Disponibilité >99.9%

## 🚀 Roadmap fonctionnelle
**Phase 1 (MVP) :** [FONCTIONNALITÉS_CORE]
**Phase 2 (Growth) :** [FONCTIONNALITÉS_AVANCÉES]  
**Phase 3 (Scale) :** [OPTIMISATIONS_PERFORMANCE]

## 🎨 Contraintes design
- Interface mobile-first responsive
- Accessibilité WCAG 2.1 AA
- Support navigateurs: Chrome, Firefox, Safari, Edge
- Temps de chargement <3s sur 3G
```

### Template tech.md (stack technique)

```markdown
# Stack Technique - [NOM_PROJET]

## 🏗️ Architecture générale
**Pattern :** Clean Architecture + Domain-Driven Design
**Déploiement :** Microservices containerisés (Docker)
**Monitoring :** Observabilité complète (logs, métriques, traces)

## 💻 Stack développement
**Frontend :**
- React 18 + TypeScript 5.0+
- Next.js 14 (App Router)  
- TailwindCSS + Radix UI
- Zustand + TanStack Query

**Backend :**
- Node.js 18+ + TypeScript
- Express.js + Helmet security
- Prisma ORM + PostgreSQL 14+
- Redis cache + Bull queues

**Tests & Qualité :**
- Jest + Testing Library + Playwright
- ESLint Airbnb + Prettier + Husky
- SonarQube + Snyk security scanning
- Coverage: 85%+ unit, 70%+ integration

## 🚫 Contraintes techniques
- Pas de frameworks expérimentaux (stabilité requise)
- Node.js LTS uniquement (support long terme)
- PostgreSQL over NoSQL (consistance ACID)
- TypeScript strict mode obligatoire
- Audit sécurité avant chaque release

## 🛠️ Outils de développement
- IDE: VS Code + extensions standardisées
- Git: Conventional Commits + GitHub Flow  
- CI/CD: GitHub Actions + AWS CodePipeline
- Monitoring: CloudWatch + Grafana + Sentry
```

### Template Agent Hook sophistiqué

```yaml
# .kiro/hooks/advanced-testing.yaml
name: "Advanced Testing Workflow"
description: "Génération automatique tests + coverage + documentation"

trigger: file_saved
pattern: "src/**/*.{ts,tsx}"
conditions:
  - file_type: "component|service|utility"
  - has_tests: false

action: |
  1. Analyser le fichier sauvegardé et sa complexité
  2. Générer tests unitaires appropriés (Jest + Testing Library)
  3. Si composant React: ajouter tests d'intégration
  4. Exécuter tests automatiquement  
  5. Générer rapport coverage
  6. Si coverage <85%: suggérer tests additionnels
  7. Mettre à jour documentation JSDoc si nécessaire

post_action: |
  Afficher résultats dans Output panel:
  - ✅ Tests générés: [nombre]  
  - 📊 Coverage: [pourcentage]
  - 🐛 Tests en échec: [détails]
  - 📝 Documentation mise à jour: [oui/non]
```

---

## 💡 Cas d'usage avancés

### Développement entreprise avec gouvernance

```markdown
# Workflow entreprise structuré
1. Spec-driven → Requirements EARS validés
2. Design review → Architecture approuvée  
3. Implémentation guidée → Code selon standards
4. Agent Hooks → Validation automatique qualité/sécurité
5. Déploiement AWS → Pipeline automatisé
```

### Collaboration équipe avec contexte partagé

```markdown
# Standards équipe via Steering Files
1. .kiro/steering/ versionné avec Git
2. Hooks partagés pour workflow uniforme
3. Specs templates par type de projet
4. Gouvernance et review des steering files
```

### Intégration CI/CD avec Agent Hooks

```markdown
# Pipeline automatisé  
1. Hook pre-commit → Scan sécurité + tests
2. Hook post-merge → Génération docs + déploiement staging
3. Hook production → Monitoring + rollback automatique
```

---

## ⚠️ Limitations et contournements

| **Limitation** | **Impact** | **Contournement** |
|----------------|------------|------------------|
| Preview AWS (instable) | Bugs et limitations | Attendre version stable |
| Steering Files parfois ignorés | Contexte perdu | Redémarrage session + refresh |
| Agent Hooks debug limité | Hooks en échec silencieux | Logs manuels + validation |
| Pricing élevé version finale | Coût prohibitif équipes | Évaluer alternatives |

---

## 🔗 Ressources et communauté

### Documentation officielle
- **[Kiro Docs](https://kiro.dev/docs/)** - Documentation complète
- **[GitHub Repository](https://github.com/kirodotdev/Kiro)** - Code source et issues

### AWS et communauté
- **[AWS re:Post Kiro](https://repost.aws/articles/AROjWKtr5RTjy6T2HbFJD_Mw)** - Guide AWS détaillé
- **[AWS Builder Program](https://aws.amazon.com/developer/community/heroes/)** - Communauté développeurs AWS

### Ressources complémentaires
- **[RuleSync](https://github.com/dyoshikawa/rulesync)** - Migration règles autres agents
- **[Spec Templates](https://github.com/kiro-specs)** 🚧 *TODO* - Templates spec par domaine

---

## 🎯 Prochaines étapes

1. **[Installation et setup](setup-guide.md)** 🚧 *TODO* - Guide installation complète
2. **[Steering Files avancés](steering-guide.md)** 🚧 *TODO* - Mastering steering files
3. **[Agent Hooks workflows](hooks-guide.md)** 🚧 *TODO* - Automatisation avancée  
4. **[Spec-driven methodology](spec-methodology.md)** 🚧 *TODO* - Méthodologie complète

> 💡 **Astuce finale :** Kiro excelle dans les projets structurés avec méthodologie rigoureuse. Exploitez les Steering Files pour contexte persistant et les Agent Hooks pour automatisation intelligente. Idéal pour équipes enterprise cherchant gouvernance et scalabilité.
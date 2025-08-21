# KiloCode - Context Engineering Guide ⚡

> Guide complet pour maîtriser le Context Engineering avec l'IDE IA open-source KiloCode

KiloCode est un assistant de codage IA open-source pour VS Code, fork de Roo Code et Cline. Il se distingue par son système de **Rules par mode**, son support legacy complet, et ses templates modulaires avec interface UI intégrée.

## 🚀 Démarrage rapide

**Installation et configuration :**
```bash
# Installation depuis VS Code Marketplace
ext install KiloOrg.kilocode

# Ou téléchargement depuis GitHub Releases
https://github.com/Kilo-Org/kilocode/releases

# Initialisation avec règles
mkdir .kilocode/rules
touch .kilocode/rules/main.md
```

**Documentation officielle** → [kilocode.ai/docs](https://kilocode.ai/docs/)

---

## 🛠️ Outils officiels de Context Engineering

### 1. Système Custom Rules modulaire ⭐

**KiloCode propose une approche multi-niveaux sophistiquée :**

**A. Global Rules (Règles utilisateur globales) :**
```
~/.kilocode/rules/
├── coding_standards.md         # Standards de code globaux
├── security_guidelines.md      # Règles sécurité universelles
└── documentation_style.md      # Style documentation
```

**B. Project Rules (Règles de projet) :**
```
projet/
├── .kilocode/
│   └── rules/
│       ├── main.md             # Règles principales projet
│       ├── frontend.md         # Règles spécifiques frontend
│       ├── backend.md          # Règles spécifiques backend
│       └── testing.md          # Standards de tests
```

**C. Mode-specific Rules (Règles par mode) :**
```
projet/
├── .kilocode/
│   ├── rules-test/             # Règles mode Test
│   ├── rules-review/           # Règles mode Review
│   └── rules-architect/        # Règles mode Architect
```

**D. Legacy Support (backward compatibility) :**
```
# Formats historiques supportés
.clinerules                     # Cline legacy
.roorules                       # Roo Code legacy  
.kilocoderules                  # KiloCode alpha
.kilocoderules-test             # Mode-specific legacy
```

### 2. Custom Instructions globales 📝

**Configuration via interface :**
```
KiloCode → Settings → Modes → Custom Instructions for All Modes
```

**Instructions spécifiques par mode :**
```
KiloCode → Select Mode → Custom Instructions for [Mode] Mode
```

**Distinction avec Rules :**
- **Custom Instructions** : Préférences utilisateur IDE-wide (tous projets)
- **Rules** : Règles projet/workspace spécifiques

**Exemples d'instructions globales :**
```markdown
# Custom Instructions globales
- Je préfère du code concis et bien documenté
- Explique tes changements de manière brièvement
- Utilise TypeScript strict dans tous les projets
- Génère toujours des tests unitaires
```

### 3. Modes personnalisés et workflows 🎯

**Modes intégrés :**
- **Architect Mode** : Planification et design architectural
- **Coder Mode** : Génération et modification de code
- **Debugger Mode** : Debug et résolution de problèmes
- **Custom Modes** : Modes utilisateur personnalisés

**Workflow avec mode-specific rules :**
```
1. Sélection mode "Test" 
   → Chargement .kilocode/rules-test/
   → Instructions spécifiques tests
   
2. Switch mode "Review"
   → Chargement .kilocode/rules-review/  
   → Instructions spécifiques review code
```

### 4. Interface UI pour gestion des règles 🖥️

**Accès à l'interface :**
```
KiloCode → Icône coin bas-droit → Rules Management
```

**Fonctionnalités UI :**
- **Édition visuelle** : Éditeur Markdown intégré
- **Aperçu règles actives** : Visualisation règles chargées
- **Toggle on/off** : Activation/désactivation par règle
- **Validation syntaxe** : Vérification format Markdown
- **Import/Export** : Migration depuis/vers autres agents

### 5. Auto-approbation et workflows automatiques 🤖

**Configuration auto-approval :**
```
KiloCode → Settings → Auto-approval
```

**Niveaux d'automatisation :**
- **Confirmations manuelles** : Validation utilisateur pour chaque action
- **Auto-approval sélectif** : Actions sûres automatiques
- **Workflow automatique** : Chaînes d'actions prédéfinies

**Exemples de workflows :**
```markdown
# Workflow "Generate Tests"
1. Analyser fonction/classe
2. Générer tests unitaires  
3. Exécuter tests automatiquement
4. Afficher rapport coverage
```

### 6. Outils intégrés et navigation 🧭

**Tools Reference intégré :**
```
KiloCode → Tools Reference → Liste commandes disponibles
```

**Outils disponibles :**
- **File Operations** : Lecture, écriture, navigation projet
- **Test Execution** : Lancement et monitoring tests
- **Git Integration** : Opérations Git automatisées
- **Codebase Indexing** : Analyse et cartographie projet

**Navigation intelligente :**
- Indexation complète du codebase
- Recherche sémantique dans le code
- Détection automatique de la structure projet
- Suggestions contextuelles basées sur l'analyse

---

## 🔍 Découvertes de la communauté

### 1. Migration facilitée entre agents 🔄

**Support legacy exceptionnel :** KiloCode charge automatiquement les règles d'autres agents sans conversion.

**Migration zero-effort découverte :**
```bash
# Depuis Cline
cp .clinerules .kilocode/rules/cline-legacy.md  ✅ Auto-détecté

# Depuis Roo Code  
cp .roorules .kilocode/rules/roo-legacy.md     ✅ Auto-détecté

# Depuis autres agents
cp .cursorrules .kilocode/rules/cursor.md      ✅ Fonctionne
cp CLAUDE.md .kilocode/rules/claude.md         ✅ Fonctionne
```

**Conversion automatique :** KiloCode normalise les différents formats vers son système interne.

### 2. Templates modulaires et organisation 📚

**Stratégie communautaire :** Organisation par domaines avec réutilisation.

**Structure modulaire découverte :**
```
.kilocode/rules/
├── 00-core.md                 # Règles fondamentales
├── 10-language-typescript.md  # Règles TypeScript  
├── 20-framework-react.md      # Règles React
├── 30-testing-jest.md         # Règles Jest
├── 40-deployment.md           # Règles déploiement
└── 99-project-specific.md     # Spécificités projet
```

**Avantages :**
- **Réutilisabilité** : Modules partagés entre projets
- **Maintenance** : Mise à jour centralisée par domaine
- **Lisibilité** : Organisation claire et logique

### 3. Mode-specific rules et cas d'usage créatifs 🎨

**Bug découvert :** Mode-specific rules parfois non chargées ([Issue #1404](https://github.com/Kilo-Org/kilocode/issues/1404))

**Workarounds communautaires :**
```markdown
# Solution temporaire via Custom Instructions par mode
Mode "Test" → Custom Instructions:
"Utilise les standards de tests définis dans rules/testing.md
Focus sur coverage élevé et edge cases"

Mode "Review" → Custom Instructions:  
"Applique check-list qualité code définie dans rules/review.md
Vérifie sécurité, performance, lisibilité"
```

**Usages créatifs découverts :**
- **Profils client** : Mode par client avec règles spécifiques
- **Niveaux d'expérience** : Mode junior/senior avec règles adaptées
- **Phases projet** : Mode prototype/production avec contraintes différentes

### 4. Contribution open-source et améliorations 🛠️

**Avantage open-source :** Communauté contribue directement aux améliorations.

**Contributions notables :**
- **Règles inactives** : Toggle UI pour désactiver règles sans suppression
- **Commentaires dans rules** : Support commentaires Markdown pour documentation
- **Optimisation tokens** : Règles inactives exclues du prompt
- **Validation syntaxe** : Vérification format Markdown en temps réel

**Feedback loop efficace :** Issues GitHub → Développement → Release rapide.

### 5. Templates cross-platform et standardisation 🌐

**Initiative communautaire :** Standardisation règles inter-agents.

**Format universel découvert :**
```markdown
# Règles universelles (compatible tous agents)
## Stack technique
- Frontend: React 18 + TypeScript
- Backend: Node.js + Express  
- Tests: Jest + Testing Library

## Conventions code
- camelCase variables
- PascalCase composants
- UPPER_SNAKE_CASE constantes

# Règles spécifiques KiloCode  
## Modes recommandés
- Mode Architect: Planning architectural
- Mode Test: Génération tests + coverage
- Mode Review: Validation qualité code
```

### 6. Performance et optimisation 🚀

**Optimisations découvertes :**

**Règles légères :**
```markdown
# ❌ Règles trop verbeuses (ralentit IA)
[50 lignes d'exemples de code détaillés]

# ✅ Règles concises et actionnables  
- Utilise functional components React
- Tests Jest avec describe/it/expect
- Async/await over .then()
```

**Gestion mémoire :**
```markdown
# Surveillance usage mémoire VS Code
KiloCode → Output → Monitor performance
# Si lenteur → Réduire taille règles + désactiver règles inutiles
```

---

## 📁 Templates battle-tested

### Template main.md (règles principales)

```markdown
# Context Engineering - [NOM_PROJET]

## 🎯 Configuration KiloCode
**Modes recommandés :**
- **Architect** : Planification et design système
- **Coder** : Développement et implémentation  
- **Test** : Génération tests et coverage
- **Review** : Validation qualité et sécurité

## 📚 Stack technique
**Runtime :** Node.js 18+ + TypeScript 5.0+
**Frontend :** React 18 + Next.js 14 + TailwindCSS
**Backend :** Express + Prisma + PostgreSQL
**Tests :** Jest + Testing Library + Playwright
**Tools :** ESLint + Prettier + Husky

## 🎨 Conventions de code
**Naming :**
- Variables/functions: camelCase (getUserData)
- Components: PascalCase (UserProfile)  
- Constants: UPPER_SNAKE_CASE (API_BASE_URL)
- Files: kebab-case (user-profile.component.tsx)

**Structure :**
```
src/
├── app/           # App Router Next.js
├── components/    # Composants réutilisables  
├── lib/           # Utilitaires et config
├── hooks/         # Custom hooks
├── types/         # Types TypeScript
└── __tests__/     # Tests par fonctionnalité
```

## 🧪 Standards qualité
**Tests obligatoires :**
- Unit tests: 85%+ coverage logique métier
- Integration tests: APIs et DB
- E2E tests: User journeys critiques
- Visual tests: Storybook + Chromatic

**Code quality :**
- TypeScript strict mode + noImplicitAny
- ESLint Airbnb + React hooks + a11y
- Prettier + import sorting
- Pre-commit hooks: lint + test + type-check

## 🚫 Interdictions strictes
- Jamais `any` en TypeScript (utiliser `unknown`)
- Pas de `console.log` production (logger structuré)
- Éviter `useEffect` data fetching (TanStack Query)
- Pas mutations directes (immutabilité)
- Interdiction styles inline (TailwindCSS uniquement)

## 💡 Patterns recommandés par mode
**Mode Architect :**
- Planifier avant coder (ADR pour décisions importantes)
- Diagrammes architecture (Mermaid dans Markdown)
- Separation of concerns stricte

**Mode Coder :**
- TDD: test → code → refactor
- Composition over inheritance
- Error boundaries React pour isolation

**Mode Test :**
- AAA pattern: Arrange → Act → Assert
- Mocking minimal (préférer vrais composants)
- Tests descriptifs: "should do X when Y"

**Mode Review :**
- Checklist sécurité (OWASP Top 10)
- Performance audit (Core Web Vitals)
- Accessibility validation (axe-core)

## 🔧 Configuration KiloCode optimale
**Custom Instructions globales :**
"Code concis et documenté. Explique changements brièvement. TypeScript strict toujours."

**Auto-approval recommandé :**
- Génération tests unitaires: ✅
- Formatting code: ✅  
- Opérations Git destructrices: ❌
- Modifications package.json: ❌
```

### Template mode-specific (rules-test/)

```markdown
# Règles Mode Test - Standards de testing

## 🧪 Philosophie testing
**Test-Driven Development :**
1. Red: Écrire test qui échoue
2. Green: Code minimal pour passer test  
3. Refactor: Améliorer sans casser tests

## 📋 Standards Jest
**Structure tests :**
```typescript
describe('UserService', () => {
  describe('when creating user', () => {
    it('should create user with valid data', () => {
      // Arrange
      const userData = { name: 'John', email: 'john@example.com' };
      
      // Act  
      const result = createUser(userData);
      
      // Assert
      expect(result).toMatchObject(userData);
      expect(result.id).toBeDefined();
    });
  });
});
```

**Coverage targets :**
- Functions: 90%+ (critical business logic)
- Lines: 85%+ (overall codebase)
- Branches: 80%+ (conditional logic)

## 🎭 Mocking strategy
**Mock minimal :**
- External APIs: ✅ Mock requis
- Database: ✅ Mock ou test DB
- React components: ❌ Préférer vrais composants
- Pure functions: ❌ Pas de mock nécessaire

**MSW pour API mocking :**
```typescript
export const handlers = [
  rest.get('/api/users', (req, res, ctx) => {
    return res(ctx.json({ users: mockUsers }));
  }),
];
```

## ⚡ Performance testing
**Benchmarks obligatoires :**
- Render time components: <16ms (60fps)
- API response time: <200ms  
- Bundle size impact: <10KB per feature
```

---

## 💡 Cas d'usage avancés

### Développement multi-modes orchestré

```markdown
# Workflow complet avec mode switching
1. Mode Architect → Planification architecture
2. Mode Coder → Implémentation features  
3. Mode Test → Génération tests + coverage
4. Mode Review → Validation qualité finale
```

### Migration projet existant

```markdown
# Migration depuis autres agents
1. Copier .cursorrules → .kilocode/rules/cursor-legacy.md
2. Adapter rules pour modes KiloCode
3. Tester workflow avec UI rules
4. Optimiser performance + token usage
```

### Collaboration équipe avec rules standardisées

```markdown
# Standards équipe
1. .kilocode/rules/ versionné Git
2. Templates par stack tech partagés
3. Custom Instructions individuelles uniquement
4. Review rules comme code critique
```

---

## ⚠️ Limitations et contournements

| **Limitation** | **Impact** | **Contournement** |
|----------------|------------|------------------|
| Mode-specific rules parfois bugguées | Règles non chargées | Custom Instructions par mode |
| Interface UI parfois lente | Latence édition rules | Édition directe fichiers .md |
| Support legacy peut créer conflits | Règles dupliquées | Audit périodique + cleanup |
| Performance dégradée avec trop de rules | Lenteur IA | Rules modulaires + toggle UI |

---

## 🔗 Ressources et communauté

### Documentation officielle
- **[KiloCode Docs](https://kilocode.ai/docs/)** - Documentation complète
- **[GitHub Repository](https://github.com/Kilo-Org/kilocode)** - Code source et issues

### Communauté open-source
- **[GitHub Issues](https://github.com/Kilo-Org/kilocode/issues)** - Bugs et feature requests
- **[GitHub Discussions](https://github.com/Kilo-Org/kilocode/discussions)** - Discussions communautaires

### Outils et migration
- **[RuleSync](https://github.com/dyoshikawa/rulesync)** - Migration règles entre agents
- **[KiloCode Templates](https://github.com/kilo-community)** 🚧 *TODO* - Templates communautaires

---

## 🎯 Prochaines étapes

1. **[Installation et setup](setup-guide.md)** 🚧 *TODO* - Guide complet installation
2. **[Templates par stack](templates/)** 🚧 *TODO* - Rules prêtes par technologie  
3. **[Modes avancés](advanced-modes.md)** 🚧 *TODO* - Custom modes et workflows
4. **[Migration guide](migration-guide.md)** 🚧 *TODO* - Depuis autres agents vers KiloCode

> 💡 **Astuce finale :** KiloCode excelle par sa flexibilité open-source et son support legacy exceptionnel. Exploitez les modes spécialisés et l'interface UI pour une organisation optimale de vos règles par contexte.
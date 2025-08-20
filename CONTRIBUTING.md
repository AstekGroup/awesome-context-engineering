# 🤝 Guide de Contribution - Awesome Context Engineering

Merci de votre intérêt pour contribuer au guide **Awesome Context Engineering** ! Ce projet est une initiative Astek pour partager les meilleures pratiques en Context Engineering.

## 🎯 Notre Mission

Créer le guide de référence francophone pour maîtriser le Context Engineering, avec un focus sur les techniques pratiques et les frameworks battle-tested plutôt que sur les concepts théoriques basiques.

---

## 🚀 Comment contribuer ?

### 📋 Types de contributions recherchées

#### ✅ **Contributions prioritaires**
- **Templates prêts à l'emploi** : Prompts structurés, contextes projet, checklists
- **Exemples concrets** : Cas d'usage réels avec avant/après, métriques d'amélioration
- **Techniques d'optimisation** : Patterns spécifiques par agent (Claude, Cursor, Copilot, Gemini)
- **Frameworks avancés** : Méthodologies structurées pour industrialiser le Context Engineering
- **Études de cas Astek** : Retours d'expérience projets clients (anonymisés)

#### ⚠️ **À éviter**
- Contenu théorique basique déjà bien documenté ailleurs
- Duplication de documentations officielles existantes
- Concepts généraux sans application pratique immédiate
- Informations confidentielles clients sans anonymisation

### 🎨 Philosophie du contenu

**Réutiliser plutôt que réinventer**
- Privilégiez les liens vers les excellentes ressources existantes
- Concentrez-vous sur la valeur ajoutée unique
- Créez du contenu original là où il apporte une réelle différence

---

## 📝 Standards de qualité

### 🌐 Langue et style

- **Langue principale** : Français 🇫🇷
- **Termes techniques** : Anglais quand universellement adoptés
- **Tone** : Professionnel mais accessible, focus pratique
- **Emojis** : Usage stratégique pour la navigation (🚧 pour TODO, ✅ pour validé)

### 📚 Structure du contenu

#### Format requis
```markdown
# Titre principal

> *Description concise et attractive*

## 🎯 Pour qui ?
[Public cible spécifique]

## 🔑 Concepts clés
[2-3 points essentiels]

## 💡 Exemple pratique
[Code/template avec avant/après]

## 🚀 Mise en pratique
[Steps actionables]
```

#### Organisation des dossiers
```
agents/          # Optimisations par outil
├── claude/      # Claude-specific patterns  
├── cursor/      # Cursor workflow optimization
├── github-copilot/ # GitHub Copilot strategies
└── gemini/      # Gemini CLI techniques

frameworks/      # Méthodologies avancées
├── bmad-method/ # Framework universel
├── superclaude/ # Spécifique Claude
└── cursor-rules/ # Spécifique Cursor

templates/       # Ready-to-use templates
examples/        # Cas d'usage concrets
basics/          # Concepts fondamentaux
```

### ✅ Checklist qualité

Avant de soumettre votre contribution :

- [ ] **Pertinence** : Apporte une valeur unique non disponible ailleurs
- [ ] **Praticité** : Inclut des exemples concrets et actionables  
- [ ] **Qualité** : Orthographe, grammaire, liens fonctionnels vérifiés
- [ ] **Structure** : Suit les conventions du projet (emojis, sections)
- [ ] **Audience** : Adapté aux développeurs/PO/architectes francophones
- [ ] **Anonymisation** : Aucune information confidentielle client

---

## 🔄 Processus de contribution

### 1. 🍴 Fork et setup

```bash
# Fork le repository sur GitHub
git clone https://github.com/VOTRE-USERNAME/awesome-context-engineering.git
cd awesome-context-engineering
```

### 2. 🌿 Créer une branche

```bash
git checkout -b feat/nouvelle-fonctionnalite
# ou
git checkout -b docs/amelioration-documentation
# ou  
git checkout -b fix/correction-lien
```

### 3. ✍️ Contribuer

- Suivez les [standards de qualité](#-standards-de-qualité)
- Testez tous vos liens
- Respectez la structure existante
- Ajoutez votre nom dans la section des contributeurs si souhaité

### 4. 📤 Pull Request

#### Template de PR
```markdown
## 🎯 Type de contribution
[ ] Template prêt à l'emploi
[ ] Exemple concret / étude de cas
[ ] Framework / méthodologie
[ ] Amélioration documentation
[ ] Correction bug/lien
[ ] Autre : ___________

## 📋 Description
[Description claire de votre contribution]

## ✅ Checklist
- [ ] Respecte les standards de qualité
- [ ] Liens fonctionnels vérifiés
- [ ] Contenu anonymisé si nécessaire
- [ ] Tests sur mobile/desktop effectués
- [ ] Valeur ajoutée unique identifiée

## 🧪 Comment tester
[Instructions pour reviewer votre contribution]
```

#### Processus de review
1. **Review automatique** : Vérification des standards (orthographe, liens)
2. **Review pair** : Validation par un autre contributeur Astek
3. **Review mainteneur** : Validation finale et merge

---

## 👥 Équipe et responsabilités

### 🔧 Mainteneurs principaux
- **@tfoutrein** - Initiateur et mainteneur principal
- *[Autres mainteneurs Astek à venir]*

### 🎯 Domaines d'expertise recherchés
- **Claude Optimization** : Patterns SuperClaude, Projects optimization
- **Cursor Mastery** : Rules avancées, workflow automation  
- **Copilot Excellence** : Context files, multi-repos strategies
- **Gemini CLI** : Project context, advanced prompting
- **RAG/AI Architecture** : Systèmes de récupération, agents complexes
- **UX/Content Design** : Amélioration navigation et accessibilité

### 🏆 Reconnaissance des contributions

Les contributeurs majeurs seront :
- Mentionnés dans le README principal
- Invités aux sessions de partage Astek
- Crédités dans les présentations clients (si souhaité)

---

## 🚨 Code de conduite

### Valeurs Astek
- **Bienveillance** : Feedback constructif, entraide, partage de connaissances
- **Excellence** : Standards de qualité élevés, amélioration continue
- **Innovation** : Ouverture aux nouvelles approches, expérimentation encadrée
- **Collaboration** : Travail d'équipe, communication transparente

### Comportements attendus
- Respect des opinions et approches différentes
- Communication professionnelle et bienveillante  
- Focus sur l'amélioration collective des pratiques
- Partage des échecs et apprentissages autant que des succès

### Comportements non tolérés
- Critique destructive ou personnelle
- Partage d'informations confidentielles
- Duplication massive sans valeur ajoutée
- Non-respect des standards qualité après feedback

---

## 🆘 Besoin d'aide ?

### 💬 Où demander de l'aide ?
- **Issues GitHub** : Questions techniques, propositions d'amélioration
- **Discussions** : Brainstorming, retours d'expérience
- **Slack Astek** : Channel `#awesome-context-engineering` (à créer)

### 📚 Ressources pour contribuer
- [Guide Markdown](https://guides.github.com/features/mastering-markdown/)
- [Conventional Commits](https://www.conventionalcommits.org/) 
- [Git Flow Astek](lien-interne-astek) *TODO*

### ❓ FAQ Contributions

**Q : Puis-je partager du code client ?**
R : Uniquement après anonymisation complète et validation projet.

**Q : Comment propose-r une nouvelle section ?**
R : Ouvrez une issue avec le template "Nouvelle section" pour discussion.

**Q : Dois-je maîtriser Git pour contribuer ?**
R : Les bases suffisent. L'équipe peut aider pour les aspects techniques.

**Q : Combien de temps pour une review ?**
R : Objectif 48h ouvrées pour un premier feedback.

---

## 🎉 Merci !

Chaque contribution, même petite, améliore ce guide pour toute la communauté Astek et au-delà. 

**Ensemble, élevons le niveau du Context Engineering en France ! 🇫🇷**

---

*Ce guide de contribution évolue avec le projet. N'hésitez pas à proposer des améliorations !*
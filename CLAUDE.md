# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is **Awesome Context Engineering**, a curated guide in French for mastering Context Engineering and optimizing AI interactions. The project focuses on practical frameworks, agent-specific optimization techniques, and battle-tested templates rather than basic AI concepts.

### Current Highlight
The repository features a **Highlight section** that showcases technologies or frameworks currently emphasized by the Astek community. Currently featuring **AGENTS.md** - a standardized open format for providing AI agents with project-specific instructions.

**Important**: The Highlight section includes a "Dernière mise à jour" (Last updated) date that must be updated whenever the highlighted technology/framework changes.

## Repository Architecture

### Content Structure Philosophy
- **Documentation-centric**: Repository is primarily markdown-based educational content
- **Agent-specific optimization**: Separate sections for Claude, Cursor, GitHub Copilot, Gemini CLI, Windsurf, KiloCode, and Kiro
- **Framework focus**: Organized frameworks (agent-agnostic like AGENTS.md and BMAD-METHOD vs agent-specific like SuperClaude)
- **Template-driven**: Ready-to-use templates for practical implementation
- **French-first**: Content is primarily in French with some English technical terms
- **Highlight-driven**: Featured technologies/frameworks are prominently showcased

### Directory Structure
```
agents/                    # Agent-specific optimization techniques
├── claude/               # Claude-specific patterns and templates
├── cursor/               # Cursor workflow optimization
├── github-copilot/       # GitHub Copilot context strategies
├── gemini/               # Gemini CLI project context techniques
├── windsurf/             # Windsurf context engineering
├── kilocode/             # KiloCode optimization patterns
└── kiro/                 # Kiro steering files and hooks

frameworks/               # Advanced methodologies
├── bmad-method/         # BMAD-METHOD (agent-agnostic framework)
└── superclaude/         # SuperClaude (Claude-specific framework)

templates/               # Ready-to-use templates
examples/                # Real-world use cases
basics/                  # Fundamental concepts
```

## Content Development Guidelines

### Language and Style
- **Primary language**: French
- **Technical terms**: English when universally adopted (e.g., "Context Engineering", "prompt")
- **Tone**: Professional yet accessible, practical focus
- **Emojis**: Used strategically for navigation (🚧 for TODO items, 🚀 for quick start)

### Content Philosophy
- **Reuse over reinvent**: Link to official documentation rather than duplicate
- **Focus on optimization**: Advanced techniques, not basic concepts  
- **Original value**: Create content where unique insights can be provided
- **Battle-tested**: Prioritize proven patterns and templates

### Framework Organization
- **Agent-Agnostic**: Universal methodologies (AGENTS.md ⭐, BMAD-METHOD)
- **Agent-Specific**: Optimizations for particular tools (SuperClaude for Claude)
- **Hierarchical Structure**: Clear separation helps users find relevant frameworks faster
- **Featured Frameworks**: Highlighted frameworks (⭐) represent current community focus

### TODO Item Management
- Current status: Most content marked as 🚧 *TODO* (early development phase)
- TODO items represent planned content, not broken features
- Priority: Focus on frameworks and templates sections first

## Development Commands

Since this is a documentation repository, there are no build, test, or lint commands. Content development involves:

- **Adding content**: Create markdown files following the established structure
- **Link validation**: Ensure internal links work correctly
- **Content review**: Verify examples are practical and accurate

## Git Workflow

- Single branch development (main)
- Conventional commits preferred (`feat:`, `docs:`, `fix:`)
- Focus on incremental content additions

## Special Considerations

- Repository contains extensive placeholder structure (TODO items)
- Content is educational/reference material, not executable code
- French language content requires cultural context awareness
- Integration with SuperClaude Framework requires understanding of advanced AI interaction patterns
- **AGENTS.md compatibility**: This repository follows AGENTS.md principles for AI agent instructions
- **Highlight section**: Pay attention to featured technologies/frameworks in the Highlight section for current priorities
- **Highlight date tracking**: Always update the "Dernière mise à jour" date when changing the highlighted technology/framework

## Key Frameworks to Understand

### AGENTS.md (Currently Highlighted ⭐)
- **Purpose**: Standardized format for AI agent instructions
- **Location**: Featured in Highlight section and agent-agnostic frameworks
- **Importance**: Represents the future of standardized AI interaction
- **Usage**: Compatible with all AI coding tools (Cursor, Gemini CLI, Claude, Aider, etc.)

### SuperClaude
- **Purpose**: Advanced framework specifically for Claude Code optimization
- **Location**: frameworks/superclaude/
- **Importance**: Claude-specific optimization techniques and patterns
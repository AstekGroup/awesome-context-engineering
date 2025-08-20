# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is **Awesome Context Engineering**, a curated guide in French for mastering Context Engineering and optimizing AI interactions. The project focuses on practical frameworks, agent-specific optimization techniques, and battle-tested templates rather than basic AI concepts.

## Repository Architecture

### Content Structure Philosophy
- **Documentation-centric**: Repository is primarily markdown-based educational content
- **Agent-specific optimization**: Separate sections for Claude, Cursor, GitHub Copilot, and Gemini CLI
- **Framework focus**: Original frameworks like SuperClaude and Cursor Rules patterns
- **Template-driven**: Ready-to-use templates for practical implementation
- **French-first**: Content is primarily in French with some English technical terms

### Directory Structure
```
agents/                    # Agent-specific optimization techniques
├── claude/               # Claude-specific patterns and templates
├── cursor/               # Cursor workflow optimization
├── github-copilot/       # GitHub Copilot context strategies
└── gemini/               # Gemini CLI project context techniques

frameworks/               # Advanced methodologies
├── superclaude/         # SuperClaude Framework integration
└── cursor-rules/        # Cursor Rules patterns

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
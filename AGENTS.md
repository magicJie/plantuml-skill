# PROJECT KNOWLEDGE BASE

**Generated:** 2026-02-20
**Commit:** 5580ff7
**Branch:** main

## OVERVIEW

Claude Code skill for generating PlantUML diagrams from text/code and converting `.puml` files to PNG/SVG images. Stack: Python scripts + Java plantuml.jar + Graphviz.

## STRUCTURE

```
plantuml/
├── SKILL.md              # Primary skill definition (PDA architecture, loaded by Claude Code)
├── scripts/              # Python conversion/processing tools
├── references/           # Syntax guides for all 19 diagram types
│   └── troubleshooting/  # 12 error-category guides + decision tree
└── examples/             # Framework-specific .puml templates
    ├── spring-boot/
    ├── fastapi/
    └── python-etl/
```

## WHERE TO LOOK

| Task | Location |
|------|----------|
| Skill entry point | `SKILL.md` (PDA/token-optimized) |
| Diagram syntax for type X | `references/[type]_diagrams.md` |
| All diagram types index | `references/toc.md` |
| Universal syntax elements | `references/common_format.md` |
| Styling / themes | `references/styling_guide.md` |
| Unicode symbols | `references/unicode_symbols.md` |
| Error troubleshooting | `references/troubleshooting/toc.md` → specific guide |
| Convert .puml → image | `scripts/convert_puml.py` |
| Process markdown | `scripts/process_markdown_puml.py` (preferred) |
| Legacy markdown extract | `scripts/extract_and_convert_puml.py` (deprecated) |
| Verify environment | `scripts/check_setup.py` |
| Resilient 4-step workflow | `references/workflows/resilient-execution-guide.md` |
| Framework diagram templates | `examples/[framework]/` |

## CONVENTIONS

- All `.puml` files require `@startuml` / `@enduml` delimiters
- Structured filename convention: `<markdown_name>_<num>_<type>_<title>.puml`
- Comments use `'` (single-line) or `/' ... '/` (multi-line)
- Modern styling: use `<style>` CSS-like blocks, NOT legacy `skinparam`
- Themes via `!theme <name>` at top of diagram

## ANTI-PATTERNS (THIS PROJECT)

- Do NOT use `skinparam` for styling — use `<style>` blocks instead
- Do NOT use `extract_and_convert_puml.py` for new work — use `process_markdown_puml.py`
- Do NOT upload markdown with PlantUML blocks to Confluence/Notion without converting first
- Do NOT skip `@startuml`/`@enduml` delimiters — diagrams will fail silently

## COMMANDS

```bash
# Verify environment (Java, Graphviz, plantuml.jar)
python scripts/check_setup.py

# Convert single .puml file
python scripts/convert_puml.py diagram.puml [--format svg] [--output-dir images/]

# Process markdown (embedded + linked .puml)
python scripts/process_markdown_puml.py article.md [--format svg] [--validate]

# Resilient processor (4-step with error recovery)
python scripts/resilient_processor.py article.md [--format png]

# Direct Java (advanced)
java -jar ~/plantuml.jar diagram.puml
java -jar ~/plantuml.jar --check-syntax diagram.puml
```

## NOTES

- `plantuml.jar` must be at `~/plantuml.jar`, `/usr/local/bin/plantuml.jar`, or `$PLANTUML_JAR`
- Graphviz (`dot`) required for most UML types; NOT required for JSON/YAML/Gantt/MindMap
- `SKILL.md` uses progressive disclosure architecture (tier1_token_budget: 100) — loads sub-guides on demand
- `process_markdown_puml.py` handles both embedded ` ```puml ` blocks AND linked `![](file.puml)` references in one pass

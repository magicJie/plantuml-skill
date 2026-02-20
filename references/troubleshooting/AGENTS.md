# TROUBLESHOOTING GUIDES

12 focused error-category guides + decision tree for PlantUML errors.

## WHERE TO LOOK

Start at `toc.md` — it contains the error decision tree to route to the right guide.

| Guide | Covers |
|-------|--------|
| `toc.md` | Navigation hub + error decision tree |
| `installation_setup_guide.md` | Java/Graphviz/jar not found |
| `general_syntax_guide.md` | Generic syntax errors, delimiter issues |
| `sequence_diagrams_guide.md` | Sequence-specific errors |
| `class_diagrams_guide.md` | Class diagram errors |
| `activity_diagrams_guide.md` | Activity diagram errors |
| `er_diagrams_guide.md` | ER diagram errors |
| `arrows_relationships_guide.md` | Arrow/relationship syntax errors |
| `styling_themes_guide.md` | `<style>` block and theme errors |
| `text_labels_guide.md` | Label/note formatting errors |
| `image_generation_guide.md` | PNG/SVG output failures |
| `performance_guide.md` | Slow rendering, large diagram issues |
| `preprocessor_includes_guide.md` | `!include`, `!define` errors |

## WORKFLOW

1. Get error message from PlantUML output
2. Open `toc.md` → follow decision tree
3. Load specific `[category]_guide.md`
4. Also check `../common_syntax_errors.md` for diagram-type-specific patterns

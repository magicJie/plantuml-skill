# EXAMPLES

Framework-specific `.puml` templates for code-to-diagram conversion.

## WHERE TO LOOK

| Framework | Directory | Diagrams |
|-----------|-----------|----------|
| Spring Boot | `spring-boot/` | deployment, component, sequence |
| FastAPI | `fastapi/` | deployment |
| Python ETL | `python-etl/` | architecture |

## USAGE

1. Identify the target application type
2. Open the matching subdirectory
3. Copy and adapt the `.puml` file to match your architecture
4. Use Unicode symbols from `../references/unicode_symbols.md` for semantic clarity

## NOTES

- Each subdirectory has a `README.md` explaining the diagram patterns used
- Templates use modern `<style>` syntax — do NOT convert to `skinparam`
- `test_linked_puml.md` and `test_resilient.md` are test fixtures, not templates

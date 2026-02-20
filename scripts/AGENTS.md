# SCRIPTS

Python tools for PlantUML conversion and processing.

## WHERE TO LOOK

| Task | File |
|------|------|
| Verify Java/Graphviz/jar setup | `check_setup.py` |
| Convert single `.puml` → image | `convert_puml.py` |
| Process markdown (preferred) | `process_markdown_puml.py` |
| Resilient 4-step processor (PRIMARY) | `resilient_processor.py` |
| Legacy markdown extractor | `extract_and_convert_puml.py` ⚠️ deprecated |

## SCRIPT INTERFACES

```bash
# check_setup.py — no args, validates environment
python scripts/check_setup.py

# convert_puml.py
python scripts/convert_puml.py <file.puml> [--format png|svg] [--output-dir <path>]

# process_markdown_puml.py
python scripts/process_markdown_puml.py <file.md> [--format png|svg] [--output-dir <path>] [--validate]

# resilient_processor.py
python scripts/resilient_processor.py <file.md|file.puml> [--format png|svg] [--validate-only]
```

## CONVENTIONS

- All scripts use `PLANTUML_JAR` env var or fall back to `~/plantuml.jar` / `/usr/local/bin/plantuml.jar`
- `resilient_processor.py` references `../references/` for error guides — must run from repo root or via `python scripts/`
- Output default: same dir as input for `.puml`; `images/` subdir for markdown processing

## ANTI-PATTERNS

- Do NOT use `extract_and_convert_puml.py` — use `process_markdown_puml.py` instead
- Do NOT call scripts from arbitrary working directories — paths are relative to `SKILL_ROOT`

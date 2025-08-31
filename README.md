# codex-config-schema

JSON Schema for Codex CLI `config.toml` (post‑TOML parsed JSON).

Path: `schema/codex-config.schema.json`

Schema URL
- Raw: https://raw.githubusercontent.com/mkusaka/codex-config-schema/main/schema/codex-config.schema.json
- `$id`: https://raw.githubusercontent.com/mkusaka/codex-config-schema/main/schema/codex-config.schema.json

Quick check with `jsonschema` (Python, reads TOML via `tomllib`):

```
python3 -m venv .venv && \
  source .venv/bin/activate && \
  pip install jsonschema && \
  python - <<'PY'
import json
from pathlib import Path
from jsonschema import validate
import tomllib  # Python 3.11+

schema = json.loads(Path('schema/codex-config.schema.json').read_text())
data = tomllib.loads(Path('examples/example.toml').read_text())
validate(instance=data, schema=schema)
print('OK')
PY
```

See `examples/` for a minimal config sample in TOML.

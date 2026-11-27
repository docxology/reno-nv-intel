# Composable Civic Evidence for Reno, Nevada

The ten numbered Markdown files in this directory are the canonical manuscript.
Start with the [abstract](00_abstract.md), then read the [methods](02_methods.md),
[results](03_results.md), and [limitations](05_limitations_and_ethics.md).
The [bibliography](references.bib) and [claim ledger](claim_ledger.json) bind
the paper's references and evidence locations. The
[archived native packet](../../review/0.1.0-draft/) retains the exact historical
PDF, HTML, receipts, and figures.

The shared regional engine reads [its native metadata](config.json). The
[Template reader metadata](config.yaml), [preamble](preamble.md), and
[figure registry](figure_registry.json) support the local PDF and HTML build
with the documentation-standardization Template pin. Both use the same prose.
The manuscript's image links resolve after staging.

## Render and validate the retained edition

Prepare uv, XeLaTeX, and a compatible Pandoc and pandoc-crossref pair using the
[pinned Template run guide](https://github.com/docxology/template/blob/87704feae0a4490ef7dad9c931d268e8c30273c2/docs/RUN_GUIDE.md).
The local reader build used Pandoc 3.1.13 and pandoc-crossref 0.3.17.1.
From the Reno checkout, register a clean copy with Template:

```sh
reno_source=$(pwd)
git clone https://github.com/docxology/template.git ../template-render
cd ../template-render
git checkout --detach 87704feae0a4490ef7dad9c931d268e8c30273c2
uv sync --locked --no-dev --python 3.14
git -C "$reno_source" worktree add --detach "$PWD/projects/working/reno-nv-intel" HEAD
```

From the Template checkout, stage only the archived aggregate variables and
the three published manuscript figures plus the cover. The [reader evidence](template-evidence.json)
also supplies source-backed numeric fields such as the archived HTTP status and
engine limits. The evidence and figure
hashes are checked against the archived receipt, and every numbered source is
checked against the evidence commitment before the Template helper resolves it.

```sh
uv run --no-sync python - <<'PY'
import hashlib
import json
from pathlib import Path
from shutil import copyfile

from infrastructure.rendering.manuscript_injection import write_resolved_manuscript_tree

root = Path("projects/working/reno-nv-intel")
archive = root / "review/0.1.0-draft"
receipt = json.loads((archive / "review-receipt.json").read_bytes())

def receipt_member(name):
    data = (archive / name).read_bytes()
    if hashlib.sha256(data).hexdigest() != receipt["files"][name]:
        raise ValueError(f"Retained packet member differs from its receipt: {name}")
    return data

evidence = json.loads(receipt_member("evidence.json"))
if evidence["inputFingerprint"] != receipt["inputFingerprint"]:
    raise ValueError("Retained input commitments differ")

source = root / "docs/manuscript"
for path in sorted(source.glob("[0-9][0-9]_*.md")):
    relative = path.relative_to(root).as_posix()
    if hashlib.sha256(path.read_bytes()).hexdigest() != evidence["files"][relative]["sha256"]:
        raise ValueError(f"Numbered source differs from the retained evidence: {relative}")

figures = root / "output/figures"
figures.mkdir(parents=True)
for name in ("architecture", "corpus-profile", "evidence-boundaries", "cover"):
    (figures / f"{name}.png").write_bytes(receipt_member(f"figures/{name}.png"))
copyfile(source / "figure_registry.json", figures / "figure_registry.json")

variables = evidence["variables"]
staged = write_resolved_manuscript_tree(root, variables)
config = staged / "config.yaml"
config.write_bytes(b"# Generated manuscript ordering\n" + config.read_bytes())
data = root / "output/data"
data.mkdir()
aggregate = {
    name: int(value) for name, value in variables.items()
    if (name.startswith("CODE_") and value.isdecimal())
    or name in {"SOURCE_COUNT", "MONITOR_COUNT"}
}
(data / "retained-aggregate.json").write_text(json.dumps(aggregate) + "\n")
copyfile(source / "template-evidence.json", data / "reader-evidence.json")
PY

uv run --no-sync python scripts/pipeline/stage_03_render.py --project working/reno-nv-intel
uv run --no-sync python scripts/pipeline/stage_04_validate.py --project working/reno-nv-intel
```

The working checkout receives `output/pdf/reno-nv-intel_combined.pdf`,
`output/web/index.html`, and the validation and provenance reports in
`output/reports/`. The archived native packet records its own historical
Template pin. The additional reader build verifies the retained aggregate
evidence offline.

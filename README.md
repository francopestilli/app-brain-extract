# app-brain-extract

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Skull-strips a T1-weighted image with FSL 6.0.4 bet, with a configurable fractional intensity threshold and optional robust centre estimation or bias-field and neck cleanup.**

run_bet.sh reads config.json and calls bet through brain_extract.py: frac sets -f, robust adds -R and bias_neck_cleanup adds -B. Use it for quick T1w brain extraction before registration or segmentation.

| | |
|---|---|
| 📥 **Inputs** | `neuro/anat/t1w` |
| 📤 **Outputs** | `neuro/anat/t1w` |
| 🐳 **Container** | `brainlife/fsl:6.0.4` |
| ⚙️ **Resources** | 4 GB memory · 1 h walltime |
| 🔗 **Run it** | [doi.org/10.25663/brainlife.app.996](https://doi.org/10.25663/brainlife.app.996) |

#### 📥 Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `t1` | `neuro/anat/t1w` | yes | T1-weighted input volume to skull-strip |

#### 📤 Outputs

| Output | Datatype | Description |
|---|---|---|
| `t1_brain` | `neuro/anat/t1w` | Skull-stripped T1w brain volume (FSL BET output) |

<details>
<summary><b>⚙️ Parameters</b> (3)</summary>

| Parameter | Type | Default | Description |
|---|---|---|---|
| `frac` | number | `0.5` | BET fractional intensity threshold (0-1). Lower values give a larger brain estimate. |
| `robust` | boolean | `false` | Use robust brain centre estimation (-R). Slower but more reliable for unusual head shapes. |
| `bias_neck_cleanup` | boolean | `false` | Bias-field + neck-cleanup pass (-B). Recommended when neck is included in the FOV. |

</details>

<!-- brainlife-app:end -->

Skull-strip a T1w volume using FSL BET

## Inputs

- `t1` (neuro/anat/t1w)

## Outputs

- `t1_brain` (neuro/anat/t1w) -- Skull-stripped T1w brain volume (FSL BET output)

## Usage

Brainlife.io: run via `faber-app-run`/`faber-app-pipeline` (once registered
with `faber-app-create`), or the web UI.

Locally (outside brainlife): copy `config.json.example` to `config.json`,
fill in real file paths, then run `./main` from this directory. `main` pulls
its own container (`singularity exec docker://...`) -- no local install of
the underlying tool needed, only Singularity itself.

Entrypoint: `run_bet.sh`

## Authors

- Gabriele Amorosino <gamorosino@example.com>

#### MIT Copyright (c) 2026 Gabriele Amorosino

# app-brain-extract

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

# shadowbox: Claude rules

**Read `~/projects/NUC_RULES.md` first.** It covers Quatern priority, sim-run/gpu-run, the results policy and publishing.

Phone video of the owner fighting → pose → retarget to the arena's standard G1 → a fighter file that enters
the arena. Plan: PLAN.md (draft until approved). State: HANDOFF.md.

- **Public repo, Apache-2.0** for our code. Body models such as SMPL / SMPL-X are non-commercial, need
  registration, and may not be redistributed. They are never committed, vendored or downloaded by scripts. The
  owner places them in `~/projects/_assets/body_models/` and code references that path. Code that needs them sits
  behind an optional extra (`pip install .[smpl]`) so the core runs without them. Record every model and its
  license in THIRD_PARTY.md.
- **Privacy:** raw videos of the owner, frames, extracted poses, motion clips and fighter files stay in
  git-ignored `data/` and `results/`. Never commit or upload them.
- **Output is fighter files only** (ONNX policy + manifest with provenance, incl. "derived from SMPL-processed
  motion: yes/no"). No arena code here, and the arena never imports this repo.
- **Shared pipeline:** the camera → pose → G1 retarget will be shared with be-the-robot through a planned repo
  `g1-pose` (not created yet; see `~/projects/INDEX.md`). Don't build the shared parts here without asking.
  shadowbox-only stages (SMPL fitting, policy training) stay here.
- GPU work (pose models, training) only through `~/projects/bin/gpu-run`. Video decode/encode single-threaded.

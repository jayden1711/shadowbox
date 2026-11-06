# shadowbox: PLAN (skeleton, not yet reviewed by the owner)

_Status: skeleton only. No code yet. The first session writes the full plan for approval and builds nothing before that._

Goal: phone video of the owner fighting → 3D pose → retarget to the arena's standard G1 → fighter file
(ONNX policy + manifest) that the arena loads like any other fighter.

Fixed constraints (from the owner):
- Target robot = the arena's standard G1 (Menagerie `unitree_g1` @ 98a70c5 + the arena's collider set).
- The arena never imports this repo. The interface is the fighter file only.
- The camera → pose → G1 retarget is shared with be-the-robot through a planned repo `g1-pose` (Apache-2.0,
  no SMPL). Until it exists, propose the boundary in this plan; don't build shared code here.
- SMPL-family body models may be used (non-commercial): optional, never committed, provenance recorded in
  each fighter manifest.
- Videos of the owner, poses, clips and fighter files stay local (`data/`, `results/`).

Open questions for the plan: pose model choice and license; how motion becomes a policy (imitation
training on the NUC GPU); fighter manifest fields; evaluation (does the fighter stay up, does it look like
the owner).

# ADSN Spatial Engine 0.9.11

Compiled Windows engine for IntegraTwin.

- **Depth-fusion dollhouse (new default).** Every solved camera view gets a depth image from Depth Anything V2 Small
  (Apache-2.0, included in the installer), scaled to the camera solve and fused into one surface. Walls, floors and
  ceilings that photo matching left empty now come out. Photo matching (OpenMVS stereo) stays available and is used
  automatically if depth fusion cannot run.
- **Fixed: empty dollhouses.** Cleaning removed every triangle of photo-textured meshes; such builds reported
  "ready" with an empty model. Old empty builds can be repaired in place from IntegraTwin.
- **Build tracking and clean-up.** IntegraTwin shows each build's status, reason and log, and can delete builds or
  clean up failed, cancelled and empty ones, left-over folders and uploaded copies.
- **One-click setup.** COLMAP and OpenMVS download by themselves on first start; IntegraTwin starts the engine
  directly.

Verified on the owner's PC (RTX 5060, DirectML): compiled self-test (bundled depth model on the GPU, surface
extraction); normal upgrade from 0.9.10; repair of an empty 0.9.10 build (53,897 triangles restored); a real
depth-fusion dollhouse from a 15-panorama outdoor tour solve in 45 s (176,227 triangles, levelled). Known limits:
photo texturing (OpenMVS TextureMesh) crashed on that fused mesh, so the model kept vertex colours; 58 of 150 views
had too few camera points to be scaled and were left out. Scale is not calibrated. Not a survey.

Installer: 203,189,353 bytes. SHA256: 074b5918b63ffaabbd257e8e0d7dd9c9534262dbc1896336996f1efe5c63a03d.

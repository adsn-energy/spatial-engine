# ADSN Spatial Engine 0.9.12

Compiled Windows engine for IntegraTwin. Improves the depth-fusion dollhouse introduced in 0.9.11.

- **Photo textures.** OpenMVS TextureMesh crashed in its seam-levelling step on fused meshes, so 0.9.11 dollhouses
  kept plain vertex colours. The engine now retries texturing without seam levelling; faces no photo sees are grey.
- **Sky removed.** Pixels the depth network calls "infinitely far" (and a few pixels around them) are not fused, so
  sky no longer turns into blue walls.
- **More views used.** A view with too few camera points takes its depth scale from the other views of the same
  panorama (they share one optical centre). A surface needs about two agreeing views, which removes streaks.
- **Alignment.** Learned features (ALIKED + LightGlue) are available as an experimental option; SIFT stays the
  default because COLMAP 4.2.1 ran them on the CPU and crashed on the test capture.

Verified on the owner's PC (RTX 5060, DirectML): compiled self-test; upgrade from 0.9.11; a depth-fusion dollhouse
from a real 15-panorama outdoor 360 tour solve in 85 s - photo-textured, 127 of 150 views used, 90,218 triangles,
sky-blue share of the model 0.7 % (6.9 % in 0.9.11). Scale is not calibrated. Not a survey.

Installer: 203,221,441 bytes. SHA256: 1f7def34c477dd5b58fb39c93acc3eb533e31497d1e15338699b30a4800f0fea.

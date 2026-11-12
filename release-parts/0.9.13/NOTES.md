# ADSN Spatial Engine 0.9.13

Compiled Windows engine for IntegraTwin. Adds AI station matching for 360 tours.

- **AI station matching.** After the normal camera solve, panoramas that SIFT left unplaced, or in a side group of
  at most 3 stations, are matched with RoMa (dense learned matcher, MIT licence) on the GPU. It runs in the
  Gaussian Splatting runtime IntegraTwin installs, and is skipped when that runtime is not installed.
  - The weights (RoMa outdoor, MIT; DINOv2 ViT-L/14, Apache-2.0; about 1.6 GB) are downloaded once and checked
    against pinned SHA-256 values.
  - The new solve runs on a copy of the camera database.
- **Two safety rules.**
  1. A re-matched panorama may join only the one solved group it matches best, so AI matches never join two groups
     solved separately.
  2. A new model is kept only if every station it shares with the photo-matching solve sits the same way
     (rotation within 5 degrees, position within 5 %).

  A confident look-alike match on a test tour would otherwise have turned a group round by 177 degrees.
- Turn it off per job with the option `ai_matching: "off"`.

**Verified on the owner's PC (RTX 5060):**
- compiled self-test;
- upgrade from 0.9.12;
- a fresh alignment of a real 25-panorama outdoor 360 tour through the installed engine:
  - 24 of 25 panoramas placed in 2 groups (17 + 8), against 21 in 3 groups from photo matching alone;
  - three panoramas that photo matching could not place are now placed;
  - shared stations agree with the photo-matching solve to 0.16 degrees and 0.41 %;
  - 10 min 22 s, including the one-time weight download.

Scale is not calibrated. Not a survey.

Installer: 203,350,686 bytes. SHA256: d093cb1c6ddfc0dd1bca3042af3ed3a4cd5ee33898bcafe6efebc080ce7128ad.

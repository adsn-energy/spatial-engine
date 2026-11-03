# ADSN Spatial Engine

The ADSN Spatial Engine runs IntegraTwin's 3D Reconstruction (dollhouse), Gaussian Splatting, 360 tour camera
alignment and local AI tasks on your own Windows PC and graphics card. Your photos and models stay on your PC.

## Install

1. **[Download ADSN_Spatial_Engine_Setup.exe](https://github.com/adsn-energy/spatial-engine/releases/latest/download/ADSN_Spatial_Engine_Setup.exe)** (Windows 10/11, 64-bit).
2. Open it, accept the licence agreement and click **Next** until it finishes.
3. In [IntegraTwin](https://integratwin.adsnenergy.com), start any 3D Reconstruction, Gaussian Splatting or
   360 Tour *Build cameras* task. IntegraTwin starts the engine and connects to it automatically.
   The first time, your browser asks whether IntegraTwin may open the engine: tick **Always allow**.

The first dollhouse or camera task offers to download the free 3D tools it uses (COLMAP and OpenMVS, about 1 GB,
from their official releases). An NVIDIA graphics card is recommended.

To remove it: Windows Settings › Apps › ADSN Spatial Engine › Uninstall.

## What this repository contains

Only the compiled installer (in [Releases](https://github.com/adsn-energy/spatial-engine/releases)), the
[licence agreement](EULA.txt) and the [third-party notices](THIRD_PARTY_NOTICES.txt). The engine is proprietary
software of ADSN Energy & Infrastructure; its source code is not published.

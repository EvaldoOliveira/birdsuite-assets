# birdnet-assets

Binary files BirdnetPi++ stations fetch at install time and on a model switch,
served over git/ssh from the local Gitea so no station downloads anything from GitHub.

| Path | Content | Used by |
|---|---|---|
| `wheels/` | `tflite_runtime` wheels (aarch64/x86_64, Python 3.9–3.13) + `SHA256SUMS` | `scripts/install_helpers.sh` (`get_tf_whl`) |
| `models/BirdNET-Plus_V3.0-preview3.1_Global_10K/` | BirdNET+ V3.0 preview 3.1 model pair (audio + geo ONNX FP16), labels, score blacklist + `SHA256SUMS` — from the BirdNET Live app at commit `255acc33` | `scripts/utils/models.py` (`BirdNETPlusV3`) |

Fetch: `scripts/fetch_asset.sh <path-in-repo> <destination>` in the fork (shallow, sparse clone).
The BirdNET models keep their own licence (CC BY-NC-SA 4.0).

# Large-Area Tactile Emotion

Companion repository for **Large-Area Tactile Sensing for Fine-Grained Emotion Estimation and Personalized Robot Interaction**.

## Release status

**Dataset release pending.** This repository currently contains documentation only. Data files, split manifests, model checkpoints, and implementation code have not yet been uploaded. No publication venue, DOI, or release date is asserted.

## Study overview

The manuscript investigates large-area torso tactile sensing together with visual and acoustic observations for target-emotion estimation and robot interaction. The reported dataset contains 1,350 valid trials from 10 participants across 27 target emotion categories.

Target labels follow the emotion-induction video category; they do not independently establish participants' subjective emotional experience.

## Dataset organization

The manuscript describes records organized by participant, session, and complete trial, including synchronized facial images, audio, tactile contact regions, position and force, timestamps, touch-action annotations, and modality-validity indicators. Release formats and access arrangements will be documented when files are made available.

See [DATASET.md](DATASET.md) for the reported protocol and proposed release structure.

## Evaluation protocol

- Complete-trial split: training / validation / test = 810 / 270 / 270 (3:1:1).
- Sliding windows are generated after splitting, within each subset.
- Normalization parameters are estimated from training data only.
- This split does not establish generalization to unseen participants.
- Exact split manifests are pending release.

## Data access and reuse

Data are not currently downloadable from this repository. The scope of released audiovisual and tactile records, access conditions, and licensing will be specified with the release. This repository does not currently grant a data or code license.

## Citation

Bibliographic metadata will be added when available. Until then, refer to the manuscript by its full title above.

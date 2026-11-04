# Large-Area Tactile Emotion

Companion repository for **Large-Area Tactile Sensing for Fine-Grained Emotion Estimation and Personalized Robot Interaction**.

## Release status

**Audio–tactile sample subset prepared; upload pending.** The prepared subset contains 135 trials from one participant (S01), covering 27 target emotion categories with five repetitions per category. The data will be provided as browsable files under `data/S01_audio_tactile/`, rather than only as a compressed archive. This folder has not yet been uploaded.

The complete study dataset contains 1,350 trials; it is distinct from this sample subset. Full-dataset split manifests, model checkpoints, and implementation code have not yet been uploaded. No publication venue, DOI, or release date is asserted.

## Study overview

The manuscript investigates large-area torso tactile sensing together with visual and acoustic observations for target-emotion estimation and robot interaction. The reported dataset contains 1,350 valid trials from 10 participants across 27 target emotion categories.

Target labels follow the emotion-induction video category; they do not independently establish participants' subjective emotional experience.

## Dataset organization

The manuscript describes records organized by participant, session, and complete trial, including synchronized facial images, audio, tactile contact regions, position and force, timestamps, touch-action annotations, and modality-validity indicators. The prepared sample contains the audio and tactile portions only.

See [DATASET.md](DATASET.md) for the reported full-study protocol and proposed structure.

### Audio–tactile sample files

| File within each trial folder | Contents |
| --- | --- |
| `raw_bag/raw_bag_0.db3` | ROS 2 SQLite bag containing raw audio (`/g1/audio/raw`) and tactile input (`/tactile/model_input`) |
| `raw_bag/metadata.yaml` | Topic types, retained message counts, start time, and duration |
| `features.jsonl` | Audio features (768 dimensions) and tactile features (96 dimensions), timestamps, and validity information |
| `feature_config.json` | Audio and tactile feature configuration |
| `meta.json` | Trial labels, selected acquisition metadata, and release information |

The sample root also contains `release_report.json`, documenting export verification and exclusions. JSON, JSONL, YAML, and Markdown files can be inspected as text; SQLite `.db3` files require downloading and a compatible reader. Bag messages use ROS 2 CDR serialization. Audio messages use `std_msgs/msg/UInt8MultiArray`; tactile messages use `std_msgs/msg/Float32MultiArray`.

Audio records retain `rms` and `speech_validity` when present; tactile records retain `sensor_health_checked` when present.

### Visual-data removal

Facial images on `/face/image/raw/compressed` and all visual feature records are excluded from the prepared sample. Visual data were removed during release preparation; this does not mean vision was absent during acquisition. Original audio, audio/tactile feature values, and timestamps are retained. Raw audio may identify speakers, so this subset is not described as fully anonymous.

The export report records 56,271 removed facial-image messages and 3,761 removed visual-feature records. The prepared files occupy approximately 157.56 MiB before compression. Retained raw message payloads and timestamps were checked against their source records. These are export-integrity checks.

## Evaluation protocol

The following split sizes refer to the full 1,350-trial study dataset, not the sample subset.


- Complete-trial split: training / validation / test = 810 / 270 / 270 (3:1:1).
- Sliding windows are generated after splitting, within each subset.
- Normalization parameters are estimated from training data only.
- This split does not establish generalization to unseen participants.
- Exact split manifests are pending release.

## Data access and reuse

The sample folder is pending upload. **For access to the complete dataset, please contact Chaoqi Sheng at [shengchaoqi@zju.edu.cn](mailto:shengchaoqi@zju.edu.cn)** and briefly describe your affiliation and intended research use. Access is subject to participant consent, applicable ethics arrangements, and agreed data-use conditions.

This repository does not currently grant a data or code license. Reuse terms will be specified with the release.

## Citation

Bibliographic metadata will be added when available. Until then, refer to the manuscript by its full title above.

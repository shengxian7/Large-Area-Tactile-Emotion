# Dataset documentation

## Current availability

Documentation only; dataset files and exact split manifests are pending release. The details below summarize the current manuscript and are not a verification of uploaded data.

## Collection and labels

- Platform: Unitree G1 with front/back torso capacitive–piezoresistive tactile sensors, camera, and microphone.
- Participants: 10.
- Target emotion categories: 27.
- Valid complete trials: 1,350.
- Procedure: emotion-induction video followed by multimodal robot interaction.
- Emotion targets: induction-video categories, not independently verified subjective emotional states.
- Additional annotations described in the manuscript: touch actions, timestamps, participant/session information, and modality validity.

The exact ordered class-name list and integer mapping must be exported from the training configuration; they are not supplied here to avoid inventing a mapping.

## Missing observations

A zero signal from a functioning tactile device denotes no contact. Device failure or interrupted communication denotes missing data. Facial visibility and usable vocalization are tracked separately. Silence denotes absence of usable vocal emotion evidence under the manuscript protocol.

## Splits

| Subset | Complete trials |
| --- | ---: |
| Training | 810 |
| Validation | 270 |
| Test | 270 |

Split complete trials before generating windows. Fit preprocessing statistics using training data only. The reported split is not a participant-disjoint evaluation. Exact trial assignments and random seeds remain to be supplied from the original experiment.

## Proposed release layout

The following paths are a proposal, not files currently provided:

- `metadata/trials.csv`: released trial identifiers, pseudonymous participant/session identifiers, target labels, action annotations, and available modalities.
- `metadata/label_mapping.json`: exact training label names and integer mapping.
- `splits/train.txt`, `splits/val.txt`, `splits/test.txt`: original complete-trial assignments.
- `data/`: approved released tactile records and audiovisual data or features, with timestamp and validity information.
- `docs/data_format.md`: array shapes, units, coordinate conventions, synchronization, and preprocessing.
- `results/`: per-trial predictions and evaluation outputs, when released.

## Items to confirm before release

Confirm the exact files and trial counts, units and array shapes, class mapping, original split assignments, preprocessing, access conditions for participant recordings, and the applicable license. Public release scope and any restricted-access arrangements will be documented here.

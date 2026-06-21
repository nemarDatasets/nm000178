# BNCI 2020-001 Reach-and-Grasp Electrode Comparison EEG dataset

## Overview

This dataset comprises EEG recordings from 45 healthy participants performing self-initiated reach-and-grasp motor imagery tasks using three different recording systems: gel-based laboratory equipment (g.tec USBamp/g.Ladybird), water-based mobile EEG (EEG-Versatile), and dry-electrode mobile EEG (EEG-Hero). Participants executed palmar and lateral grasp actions toward objects while EEG signals were recorded at 256 Hz from 58 EEG channels plus 6 EOG channels (64 total channels). The study investigates the feasibility of decoding natural reach-and-grasp neural correlates across different EEG acquisition modalities for brain-computer interface applications.

## Dataset Summary

| Property | Value |
|---|---|
| Subjects | 15 |
| Channels | 11–64 |
| Classes | 3 |
| Trial length | 5 s |
| Sampling frequency | 256 Hz |
| Sessions | 3 |
| Total trials | 7200 |
| Paradigm | MotorImagery |

## Data Collection Methods

EEG data were acquired at 256 Hz sampling rate using 58 EEG channels and 6 EOG channels (64 total) with a 5% grid system montage. Three recording systems were employed: gel-based active electrodes (g.tec USBamp/g.Ladybird, reference: right earlobe, ground: AFz), water-based mobile EEG (EEG-Versatile), and dry-electrode mobile EEG (EEG-Hero). Online filtering included 8th order Chebyshev filter (0.01-100 Hz) and 50 Hz notch filter. Participants performed 80 self-initiated reach-and-grasp trials each for palmar grasp (toward glass) and lateral grasp (toward spoon) with 2-second fixation period, 1-2 second hold, and 4-second inter-trial interval. Offline preprocessing included 4th order Butterworth bandpass filtering (0.3-60 Hz), extended infomax ICA for artifact removal (applied to gel-based and water-based systems; not applied to dry-electrode recordings due to unfavorable channel count), amplitude thresholding (>125 µV), and abnormal joint probability/kurtosis rejection (4 SD threshold).

## How to Access via MOABB

Install MOABB and load this dataset directly:

```python
from moabb.datasets import BNCI2020_001
from moabb.paradigms import MotorImagery
paradigm = MotorImagery()

dataset = BNCI2020_001()
X, y, metadata = paradigm.get_data(dataset)
```

For more details see the [MOABB documentation](https://moabb.neurotechx.com/) and the
[MOABB dataset page](https://moabb.neurotechx.com/docs/generated/moabb.datasets.BNCI2020_001.html).

## Citation

If you use this dataset please cite the primary publication:

> DOI: [10.3389/fnhum.2022.898300](https://doi.org/10.3389/fnhum.2022.898300)

## NEMAR / MOABB Benchmark Collection

This BIDS-formatted dataset was converted from the original data using the
[MOABB](https://moabb.neurotechx.com/) pipeline and re-hosted on
[NEMAR](https://nemar.org/) as part of the MOABB benchmark collection.
The original data and license terms apply — see `dataset_description.json` for details.

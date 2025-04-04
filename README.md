#  AASIST: Audio Anti-Spoofing using Integrated Spectro-Temporal Graph Attention Networks

This repository contains the implementation, fine-tuning, and evaluation of the **AASIST** model for detecting AI-generated or spoofed human speech using the [ASVspoof 2019 LA dataset](https://datashare.ed.ac.uk/handle/10283/3336).  
The model and this submission address the problem of detecting deepfake audio in real conversations and potential real-time settings.

---

##  Part 1: Research & Selection

###  Overview
I reviewed several approaches from the [Audio-Deepfake-Detection GitHub repository](https://github.com/media-sec-lab/Audio-Deepfake-Detection) and selected three promising models for detecting AI-generated human speech.Those are Documented and available in the Model_Report Document in the repository.



##  Part 2: Implementation

###  Selected Approach: **AASIST**

I implemented and fine-tuned the AASIST model using the ASVspoof 2019 LA dataset.

###  Setup

```bash
git clone https://github.com/Harshad712/MOMENTA-HARSHAD
cd MOMENTA-HARSHAD/ASSIST
pip install -r requirements.txt
```

### Data preparation
I trained/validated/evaluated AASIST using the ASVspoof 2019 logical access dataset [4].
```
python ./download_dataset.py
```
(Alternative) Manual preparation is available via 
- ASVspoof2019 dataset: https://datashare.ed.ac.uk/handle/10283/3336
  1. Download `LA.zip` and unzip it
  2. Set your dataset directory in the configuration file

### Training (Light-FineTuning)
The `main.py` includes train/validation/evaluation.

To train AASIST [1]:
```
python main.py --config ./config/AASIST.conf
```
Modified parameters for quick fine-tuning:
- `num_epochs`: 30
- `learning_rate`: 0.0001
- `base_lr`: 0.0001

### Pre-trained models
We provide pre-trained AASIST and AASIST-L.

To evaluate AASIST [1]:
- It shows `EER: 0.83%`, `min t-DCF: 0.0275`
```
python main.py --eval --config ./config/AASIST.conf
```

---

## Part 3: Documentation 
The required Analysis on the ASSIST Model is done and documented in the Model_Analysis Document is provided in the repository.

---

##  Citation

```bibtex
@article{jung2022aasist,
  title={AASIST: Audio Anti-Spoofing using Integrated Spectro-Temporal Graph Attention Networks},
  author={Jung, Jee-weon and Tak, Hemlata and et al.},
  journal={IEEE/ACM Transactions on Audio, Speech, and Language Processing},
  year={2022}
}
```

---

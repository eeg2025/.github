
<!-- # EEG Foundation Challenge: From Cross-Task to Cross-Subject EEG Decoding -->


The 2025 EEG Foundation Challenge: From Cross-Task to Cross-Subject EEG Decoding is a biosignal challenge accepted to the [**NeurIPS 2025 Competition Track**](https://neurips.cc/Conferences/2025/CallForCompetitions). This competition aims to advance the field of EEG decoding by addressing two critical challenges:

1. **Cross-Task Transfer Learning**: Developing models that can effectively transfer knowledge from any cognitive EEG tasks to active task
2. **Subject Invariant Representation**: Creating robust representations that generalize across different subjects while predicting clinical factors

Check out the Challenge paper on arXiv: [10.48550/arXiv.2506.19141](https://arxiv.org/abs/2506.19141)

## Competition Tasks

<div style="padding: 20px; text-align: center;">
  <img alt="introduction" src="https://eeg2025.github.io/assets/img/workflow.png" style="max-width: 100%;" />
  <p style="text-align: left; margin-top: 10px; font-family: sans-serif; font-size: 0.9em">
    <b>Figure 1</b>: HBN-EEG Dataset and Data split. <b>A.</b> EEG is recorded using a 128-channel system during active tasks (i.e., with user input) or passive tasks. <b>B.</b> The psychopathology and demographic factors. <b>C.</b> The dataset split into Train, Test, and Validation. Details in <b><a href="https://eeg2025.github.io/assets/files/proposal.pdf">subsection 1.2 of the proposal.</a></b>
  </p>
</div>

### Challenge 1: Cross-Task Transfer Learning

This supervised learning challenge consists of a regression task. 

Participants will predict behavioral performance metrics (response time via regression and success rate via classification) from an active experimental paradigm (Contrast Change Detection, CCD) using EEG data. 
We suggest that competitors use passive activities as a pretraining and fine-tune into the cognitive task CCD.

We will use our trained model within the competition cluster to make inferences in the CCD set.

Teams can leverage multiple datasets and experimental paradigms to train their models, utilizing unsupervised or self-supervised pretraining to capture latent EEG representations, then fine-tuning for the specific supervised objectives to achieve generalization across subjects and cognitive paradigms. See the [Starter Kit](baseline.md) for more details.

*Note: The initial pretraining design of the SuS task is no longer mandatory because of the high number of participants and the low number of clusters.*

### Challenge 2: Psychopathology Factor Prediction (Subject Invariant Representation)

This supervised regression challenge requires teams to predict four continuous psychopathology scores (p-factor~~, internalizing, externalizing, and attention~~) from EEG recordings across multiple experimental paradigms. 

Teams can employ unsupervised or self-supervised pretraining strategies to learn generalizable neural representations, then adapt these foundation models for the regression targets while maintaining robustness across different subjects and experimental conditions. 

See the [Starter Kit](baseline.md) for more details. *Note: Other factors (internalizing, externalizing, and attention) were removed from the challenge to streamline the execution phase.*


## Dataset

The competition uses the HBN-EEG dataset ([paper](https://www.biorxiv.org/content/10.1101/2024.10.03.615261v2), [blog post](https://neuromechanist.github.io/data/hbn/)), which includes EEG recordings from over 3,000 participants across six distinct cognitive tasks:

### Passive Tasks

- **Resting State (RS)**: Eyes open/closed conditions with fixation cross
- **Surround Suppression (SuS)**: Four flashing peripheral disks with contrasting background
- **Movie Watching (MW)**: Four short films with different themes

### Active Tasks

- **Contrast Change Detection (CCD)**: Identifying dominant contrast in co-centric flickering grated disks
- **Sequence Learning (SL)**: Memorizing and reproducing sequences of flashed circles
- **Symbol Search (SyS)**: Computerized version of WISC-IV subtest

Each participant's data is accompanied by four psychopathology dimensions derived from the Child Behavior Checklist (CBCL) and demographic information, including age, sex, and handedness. Data is in the BIDS (Brain Imaging Data Structure) format.

## Awards

Top-ranking teams will be awarded with the following prizes:

- **Spotlight Talk** for the first team at the [2025 NeurIPS Workshop "Foundation Models for the Brain and Body"](https://brainbodyfm-workshop.github.io) to present their work (December 6-7, 2025)
- **Cash prizes** of 2500$ each for the top 3 teams (Sponsored by Meta)
- **Travel costs** covered for the main author of the top 3 teams (Sponsored by Meta)
- **Registration fees** for the whole NeurIPS 2025 conference covered for the main author of the top 3 teams

## Motivation

EEG decoding faces significant challenges due to signal heterogeneity from various factors like non-stationarity, noise sensitivity, inter-subject morphological differences, varying experimental paradigms, and differences in sensor placement. While recent advances in machine learning have shown promise, there remains a critical need for models that can generalize across different subjects and tasks without expensive recalibration.

This competition aims to address these challenges by:

1. Providing a large-scale, diverse dataset for evaluating model generalization
2. Encouraging the development of robust, transferable EEG decoding methods
3. Establishing benchmarks for cross-task and cross-subject performance
4. Fostering collaboration between machine learning and neuroscience communities

## Sponsors

<div style="padding: 20px; text-align: center;">
  <div style="display: flex; justify-content: space-around; align-items: center; flex-wrap: wrap; margin-bottom: 20px;">
    <img src="https://eeg2025.github.io/assets/logos/meta.png" style="max-width: 50%; margin: 10px;" alt="Meta Logo" />
  </div>
</div>

## Organizing Institutions

<!-- Row 1 -->
|  |  |  |  |
|:--:|:--:|:--:|:--:|
| ![LISN](https://eeg2025.github.io/assets/logos/lisn.png) | ![UC San Diego](https://eeg2025.github.io/assets/logos/ucsd.png) | ![Donders Institute](https://eeg2025.github.io/assets/logos/donders.png) | ![Université Paris-Saclay](https://eeg2025.github.io/assets/logos/ups.png) |
| LISN | UC San Diego | Donders Institute (Radboud Univ.) | Université Paris-Saclay |

<!-- Row 2 -->
|  |  |  |  |
|:--:|:--:|:--:|:--:|
| ![Inria](https://eeg2025.github.io/assets/logos/inria.png) | ![ICM](https://eeg2025.github.io/assets/logos/icm.png) | ![ChaLearn](https://eeg2025.github.io/assets/logos/chalearn.png) | ![Child Mind Institute](https://eeg2025.github.io/assets/logos/mind_intitute.png) |
| Inria | Paris Brain Institute (ICM) | ChaLearn | Child Mind Institute |

<!-- Row 3 -->
|  |  |  |  |
|:--:|:--:|:--:|:--:|
| ![NKI](https://eeg2025.github.io/assets/logos/nki.jpg) | ![Meta](https://eeg2025.github.io/assets/logos/meta.png) | ![Ben-Gurion Univ.](https://eeg2025.github.io/assets/logos/ben_logo.png) | ![UFABC](https://eeg2025.github.io/assets/logos/ufabc.png) |
| Nathan Kline Institute | Meta | Ben-Gurion University of the Negev | UFABC |

<!-- Row 4 -->
|  |  |  |  |
|:--:|:--:|:--:|:--:|
| ![CNEURO](https://eeg2025.github.io/assets/logos/cneuro.jpg) | ![UESTC](https://eeg2025.github.io/assets/logos/UESTC.png) | ![CNRS](https://eeg2025.github.io/assets/logos/cnrs.png) | ![McGill](https://eeg2025.github.io/assets/logos/mcgill.png) |
| Cuban Neuroscience Center (CNEURO) | UESTC | CNRS | McGill University |


## Core Coordinators

|  |  |  |  |  |  |
|:--:|:--:|:--:|:--:|:--:|:--:|
| [![Bruno Aristimunha](https://eeg2025.github.io/assets/people-h180/bruno.png)](https://bruaristimunha.github.io/) | ![Sylvain Chevallier](https://eeg2025.github.io/assets/people-h180/sylvain.jpg) | ![Dung Truong](https://eeg2025.github.io/assets/people-h180/dung.jpeg) | [![Pierre Guetschel](https://eeg2025.github.io/assets/people-h180/pierre.jpeg)](https://neurotechlab.socsci.ru.nl/author/pierre-guetschel/) | ![Seyed Yahya Shirazi](https://eeg2025.github.io/assets/people-h180/seyed.jpeg) | ![Arnaud Delorme](https://eeg2025.github.io/assets/people-h180/arnaud.jpg) |
| **[Bruno Aristimunha](https://bruaristimunha.github.io/)** | **[Sylvain Chevallier](https://sylvchev.github.io/)** | **Dung Truong** | **[Pierre Guetschel](https://neurotechlab.socsci.ru.nl/author/pierre-guetschel/)** | **[Seyed Yahya Shirazi](https://neuromechanist.github.io/)** | **[Arnaud Delorme](https://arnauddelorme.com/)** |
| INRIA, Univ. Paris-Saclay | LISN, INRIA TAU, CNRS, A&O Univ. Paris-Saclay | ex-SCCN, UC San Diego, USA | Donders Institute, Radboud Univ. | UC San Diego | CNRS, IONS, UCSD |


## Coordinators

|     |     |     |     |
|:---:|:---:|:---:|:---:|
| ![Alexandre R. Franco](https://eeg2025.github.io/assets/people-h180/alexandre_franco.png) | ![Amit Majumdar](https://eeg2025.github.io/assets/people-h180/amit_majumdar.jpg) | ![Aviv Dotan](https://eeg2025.github.io/assets/people-h180/aviv.jpg) | ![Alan Evans](https://eeg2025.github.io/assets/people-h180/evans_alan.png) |
| **Alexandre R. Franco** | **Amit Majumdar** | **Aviv Dotan** | **Alan Evans** |
| Child Mind Institute, USA | UC San Diego, USA | Ben-Gurion University of the Negev, Israel | McGill University, Canada |


|  |  |  |  |  |
|:--:|:--:|:--:|:--:|:--:|
| ![Alexandre Gramfort](https://eeg2025.github.io/assets/people-h180/gramfort.jpg) | ![Isabelle Guyon](https://eeg2025.github.io/assets/people-h180/isabelle.jpg) | ![Jean-Remi King](https://eeg2025.github.io/assets/people-h180/king.png) | ![Marie-Constance Corsi](https://eeg2025.github.io/assets/people-h180/marie_constance_corsi.jpg) | ![Michael P. Milham](https://eeg2025.github.io/assets/people-h180/milham.jpg) |
| **Alexandre Gramfort** | **Isabelle Guyon** | **Jean-Remi King** | **Marie-Constance Corsi** | **Michael P. Milham** |
| Reality Labs, Meta, France | Google DeepMind; ChaLearn, USA | FAIR Brain & AI, Meta, France | Inria NERV; Paris Brain Institute (ICM), France | Child Mind Institute, USA |

|  |  |  |  |
|:--:|:--:|:--:|:--:|
| ![Oren Shriki](https://eeg2025.github.io/assets/people-h180/oren.jpg) | ![Pedro A. Valdés-Sosa](https://eeg2025.github.io/assets/people-h180/pedro_valdes_sosa.jpg) | ![Scott Makeig](https://eeg2025.github.io/assets/people-h180/scott_makeig.jpg) | ![Terrence J. Sejnowski](https://eeg2025.github.io/assets/people-h180/terrence_sejnowski.jpg) |
| **Oren Shriki** | **Pedro A. Valdés-Sosa** | **Scott Makeig** | **Terrence J. Sejnowski** | 
| Ben-Gurion University of the Negev, Israel | Cuban Neuroscience Center (CNEURO); Joint China-Cuba Lab (UESTC) | SCCN; Institute for Neural Computation, UC San Diego, USA | UC San Diego; Salk Institute, USA |


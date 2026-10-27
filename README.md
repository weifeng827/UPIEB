# UPIEB:A Dataset and Benchmark for Underwater Polarization Image Enhancement
UPIEB is a dataset and benchmark for evaluating underwater polarization image enhancement across controlled water-tank experiments and natural underwater environments. It provides paired and unpaired polarization data to support supervised learning, full-reference evaluation, and validation without paired reference images. It also includes polarization images with salient-object masks to evaluate the downstream effects of image enhancement and support underwater salient object detection.
# Background
Underwater images suffer from scattering and wavelength-dependent absorption, which reduce contrast, obscure fine details, and introduce color distortion. Polarization imaging provides additional information about the polarization states of light, offering cues for distinguishing target signals from backscattered light.
Evaluating underwater polarization image enhancement requires data that cover different degradation conditions and support complementary evaluation settings. Paired observations enable quantitative comparisons against clear-water references, while unpaired observations help examine performance in environments where reference images are difficult to obtain. Salient-object annotations further enable assessment of whether enhancement improves target detectability, complementing image quality evaluation.
UPIEB brings these settings together to support reproducible evaluation of underwater polarization image enhancement and its effects on downstream visual tasks.
# Dataset Overview
UPIEB currently contains four subsets. Each subset provides images captured at four linear polarization angles: 0°, 45°, 90°, and 135°.

<img width="795" height="354" alt="image" src="https://github.com/user-attachments/assets/ad133ae6-b324-4ae4-805b-c8ec839ae4c7" />

# Data Acquisition
The supervised paired subset, Water Tank0, was collected in a water tank. Images were first captured under clear-water conditions and used as ground-truth (GT) references. Milk was then added in successive 1 mL increments, with a new set of polarization images captured after each addition. Each acquisition contains images at four linear polarization angles: 0°, 45°, 90°, and 135°.
This procedure provides a sequence of increasingly turbid observations for each scene, together with its initial clear-water reference. The acquisition levels indicate cumulative milk additions within a sequence; they do not represent equivalent measured turbidity across different scenes or acquisition sessions.
# Link
https://pan.baidu.com/s/5rgNNX2OX7UCp6iRjo07mwA 
# Associated Benchmark Paper
Our benchmark paper, “UPIEB: A Dataset and Benchmark for Underwater Polarization Image Enhancement,” is currently under review. It describes the dataset construction, evaluation protocols, and comparative assessment of underwater polarization image enhancement methods. We plan to make a preprint available on arXiv soon.
The dataset and documentation remain under active development. The preprint link and citation information will be added to this repository when available.
# Water Tank0: Paired Water-Tank Data
Water Tank0 contains polarization observations of the same scene under clear-water and progressively more turbid conditions. Images are organized by scene and turbidity level, with four polarization-angle images in each acquisition group.
The folder named 0 contains the clear-water reference images, where available. Subsequent numbered folders contain observations under increasing turbidity within the same scene. These numbers indicate the acquisition order and relative turbidity progression within each scene; they do not represent a shared numerical turbidity scale across scenes.
This subset supports supervised learning and quantitative evaluation against clear-water references. Samples without a complete reference group should be excluded from paired evaluation.
# Water Tank1: Unpaired Water-Tank Validation Data
Water Tank1 contains water-tank polarization images without paired clear-water references. It is intended for validating enhancement methods under additional underwater degradation conditions using qualitative comparisons and no-reference evaluation.
# Natural: Natural Underwater Validation Data
Natural contains polarization images collected in natural underwater environments. It complements the controlled water-tank data and supports evaluation of generalization to real underwater imaging conditions.
Paired clear-water references are not provided for this subset.
# PSOD: Underwater Polarization Salient Object Detection Data
PSOD contains underwater polarization images and corresponding salient-object masks. It provides four polarization-angle images, color-coded angle of polarization (AoP) and degree of polarization (DoP) representations, and masks stored in the gtmask folder.
This subset supports two evaluation settings:
- Downstream evaluation of image enhancement: Compare salient object detection performance before and after enhancement to assess whether image restoration improves target detectability and foreground delineation. These results complement image quality metrics by measuring task-specific benefits.
- Standalone underwater salient object detection: Use the polarization images, derived representations, and masks to develop and evaluate underwater salient object detection methods.
The masks provide ground truth for salient object detection; they are not clear-water image references for full-reference restoration evaluation.
# Dataset Status and Planned Extensions
UPIEB is under active construction and expansion. The current release includes the paired Water Tank0 subset and the unpaired Water Tank1 and Natural validation subsets.
# Future releases will include:
- Resolution evaluation data: Polarization images of resolution test charts for assessing spatial detail preservation and recovery.
- Color fidelity evaluation data: Polarization images of standard color charts for assessing color distortion and restoration accuracy.
- Underwater photogrammetry images will be added to help check if the underwater image restoration works in terms of geometric dimensions.
# Dataset documentation and evaluation protocols will be updated as these extensions become available.
# Citation
Please cite our preliminary work if you find it helpful to your research. Our latest results are currently being submitted for publication. ❤️

```text
@ARTICLE{11267091,
  author={Kong, Weifeng and Huo, Guanying and Peng, Chao and Su, Yong and Cheng, Zhen},
  journal={IEEE Transactions on Computational Imaging}, 
  title={Low-Rank Decomposition and Polarization-Driven Transmittance Synergy for Underwater Descattering With Cross-Domain Generalization}, 
  year={2025},
  volume={11},
  number={},
  pages={1668-1681},
  doi={10.1109/TCI.2025.3636757}
}
```

# Practical Evaluation of Adversarial Robustness via Adaptive Auto Attack
Code for the 2022 CVPR paper, *"Practical Evaluation of Adversarial Robustness via Adaptive Auto Attack"*: [Paper here](https://arxiv.org/abs/2203.05154).
We provide code for evaluating the adversarial robustness of defense models using a parameter-free Adaptive Auto Attack (A³) method.
This project demonstrates the demo from the paper's GitHub, which runs A³ against the TRADES MNIST defense model.
The original code supports MNIST, CIFAR-10, CIFAR-100, and ImageNet across both Linf and L2 perturbation norms, with over 50 defense models available in the main file. Each attack can be run by uncommenting one of the lines in the main.
# Step by Step Guide
<ol>
  <li>Install the project as described in the Software Installation Section (see below).</li>
  <li>Download the test datasets from the Google Drive link listed in the Datasets Section, decompress them, and place them in the "data/" directory.</li>
  <li>Download the TRADES MNIST defense model from the Baidu online disk link listed in the Models Section, and place it in the "model_weights/" directory.</li>
  <li>Run Adaptive_Auto_Attack_main.py. The demo will run A³ against TRADES MNIST.</li>
</ol>
# Software Installation
This project uses a pyproject.toml file for dependency management. To install, run the following from the project root:

```
pip install -e .
```

This will install all required dependencies (pytorch, torchvision, numpy, tqdm, pandas, easydict, Pillow) as specified in pyproject.toml. Python 3.9 or higher is required.
# Datasets
The demo runs on MNIST. The full project supports MNIST, CIFAR-10, CIFAR-100, and a subset of ImageNet.
The test datasets can be downloaded [here](https://drive.google.com/drive/folders/1rM0pRKB2GWY1CZ8wzpymhmWKiON0wYLV?usp=sharing).
# Models
The demo runs against the TRADES MNIST defense model. The full project supports over 50 defense models across multiple datasets and norms (see Adaptive_Auto_Attack_main.py for the complete list).
The models can be downloaded from Baidu online disk [here](https://pan.baidu.com/s/1_pKv2OBGplSvoNNYdYBJgA) with extraction code: `arej`.
For the demo, only the TRADES MNIST model weights are needed.
# System Requirements
A CUDA-capable GPU is required, since the code uses `torch.device("cuda")` and sets `CUDA_VISIBLE_DEVICES = '0'` at startup. The TRADES MNIST demo uses a batch size of 512 and runs comfortably on a single GPU with modest memory. Larger defense models on CIFAR or ImageNet may require more memory, in which case the batch size should be reduced.
# Contact
For questions or concerns regarding this project, please refer to the original paper authors or open an issue on the project repository.

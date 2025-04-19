# CV-BD-Attacks

**CV-BD-Attacks** is a comprehensive research toolkit for studying **backdoor attacks in computer vision models**, particularly within the context of **federated learning** and decentralized training. The repository integrates multiple backdoor injection strategies, deep learning architectures, and evaluation tools to analyze the robustness and vulnerability of vision models under adversarial scenarios. This project serves as a foundational framework for researchers, practitioners, and educators exploring the **intersection of adversarial machine learning, computer vision (CV), and federated systems**.

## 📌 Project Objectives
The primary objectives of CV-BD-Attacks include:
-  **Simulating real-world backdoor attack scenarios** on CV models within federated and centralized settings.
- **Evaluating the impact** of different model architectures (ResNet, VGG, MLP, Transformer, etc.) under poisoned training data.
-  **Supporting plug-and-play experiments** with dataset loaders, custom backdoor triggers, and training pipelines.
- **Providing comparative analysis tools** to study the behavior of poisoned vs. clean models using Hessians, gradients, accuracy deltas, and more.

## 🗂️ Repository Structure
```CV-BD-Attacks/ 
│ ├── models/ # Model architectures for CV tasks 
│ ├── resnet.py # ResNet variants 
│ ├── vgg.py / vgg_modified # VGG variants 
│ ├── lenet.py, wrn.py # Other CNN baselines 
│ ├── TransformerModel.py # Transformer model 
│ └── simple.py, MLP.py # Lightweight architectures 
│ ├── utils/ # Utility modules 
│ ├── FL_Backdoor.py # Federated learning backdoor attack simulation 
├── Hessian_cv.py # Hessian computation and analysis 
├── helper.py # Model training & backdoor trigger helpers 
├── image_helper.py # Image-specific transformation functions 
├── main_training.py # Main training loop for CV models 
├── run_backdoor_cv_task.sh # Shell script to run an end-to-end task 
├── test_funcs.py # Evaluation and test metrics 
├── text_load.py # Dataset/text loader utilities 
├── train_funcs.py # Training function components 
├── write_script.py # Logging and script automation 
└── README.md # Project documentation
```

## ⚙️ Installation & Setup
### 1. Clone the Repository

```bash
git clone https://github.com/Miraj-Rahman-AI/CV-BD-Attacks.git
cd CV-BD-Attacks
```

## ✅ Supported Features

### 🖼️ Model Architectures
- ✅ **VGG** (multiple variants)
- ✅ **ResNet** (original and lightweight)
- ✅ **LeNet**, **WRN**, **MLP**
- ✅ **Vision Transformers**
- ✅ **Custom lightweight CNNs**

### 🎯 Attack Capabilities
- Trigger pattern injection (square, adaptive patch, pixel-level)
- Label flipping and class-specific poisoning
- Client-targeted poisoning (for federated settings)
- Loss/gradient-based behavior logging

### 🧰 Evaluation Tools
- Clean vs. Poisoned Accuracy
- Hessian Eigenvalue Distribution
- Weight Norms & Layer Activation Stats
- Task-specific plots (matplotlib-based)


## 🎓 Ideal For

- 📖 Academic research on federated backdoor attacks in CV  
- 🔍 Understanding deep model vulnerabilities in vision tasks  
- 🧪 Prototyping custom backdoor and defense strategies  
- 👨‍🏫 Teaching advanced machine learning security concepts  


## 📈 Sample Results (Backdoor Attacks)

| **Attack Type**       | **Injected Trigger**     | **Target Class** | **Clean Acc.** | **Backdoor Acc.** |
|------------------------|---------------------------|-------------------|----------------|-------------------|
| Static Patch Trigger   | White Square (3×3)        | Class 0 → 7       | 89.6%          | 94.1%             |
| Federated Injection    | Client 2 Poisoned         | Class 1 → 9       | 88.2%          | 91.7%             |
| Label Flip + Patch     | Trigger + Wrong Label     | Class 3 → 5       | 87.5%          | 92.8%             |


## 📚 References

This project is influenced by and builds upon key papers in the field:

- Bagdasaryan et al., *["How to Backdoor Federated Learning"](https://proceedings.neurips.cc/paper_files/paper/2020/file/f4b9ec30ad9f68f89b29639786cb62ef-Paper.pdf)*, NeurIPS 2020  
- Gu et al., *["BadNets: Identifying Vulnerabilities in Deep Learning"](https://arxiv.org/abs/1708.06733)*, 2017  
- Baruch et al., *["A Little Is Enough: Circumventing Defenses for Distributed Learning"](https://arxiv.org/abs/1902.06156)*, 2019  
- Zhao et al., *["Backdoor Attacks on CNNs via Targeted Sample Injection"](https://arxiv.org/abs/2202.10684)*, ECCV 2022


# BraTS 2024 Inpainting Challenge (Local Synthesis)

![image](https://github.com/user-attachments/assets/12161475-45ab-4995-9f4d-2803fdf81285)


This repository is meant as a tutorial for challenge participants. 

If you have not visited the [BraTS 2024 Inpainting Website]([https://www.synapse.org/#!Synapse:syn51156910/wiki/622357](https://www.synapse.org/Synapse:syn53708249/wiki/627498)) yet, you should do so. Also, consider reading [the challenge manuscript](https://arxiv.org/abs/2305.08992) for more context, as the GitHub tutorial is somewhat technical in nature.

This repository is divided into three subtopics with a separate README file each.
- **Dataset**: *dataset/README.md*  
    Gives an overview of the challenge training dataset. Also includes the algorithm we used to generate the dataset.
- **Baseline Model**: *baseline/README.md*
    Explains the creation of the baseline model. Also includes performance evaluations. You might want to use this chapter as a starting point for your own (better) model!
- **Evaluation**: *evaluation/README.md*
    Shows how our evaluation script works on the Synapse server using our baseline model as an example. During the validation phase, you will need to [upload predictions](https://www.synapse.org/Synapse:syn51156910/wiki/622885) to the Synapse server.
- **Submission**: *submission/README.md*
    Using our baseline model as an example guides you through the [synapse submission process](https://www.synapse.org/Synapse:syn53708249/wiki/627758).\* This is relevant for the final submission, where you will upload your whole model to Synapse.\*

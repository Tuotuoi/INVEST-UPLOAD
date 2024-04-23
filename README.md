# INVEST
INVEST training code

# Contents

- [**INVEST-UPLOAD**]()
  - [**INVEST.ipynb**]() - INVEST complete training code, open with Jupyter Notebook.
  - [**README.md**]- Introduce the contents of the file.
  - [**environment.yml**]- conda environment.
  - [**requirement.txt**]- pip environment.
  - [**losscsv.csv**] - The loss values generated during last training.
  - [**/data**] - Training data
    - [**4577.protein.links.v11.5.txt**]() - Due to server upload restrictions, within this file, we only provide download links for publicly available data.
    - [**new_protein.links.v11.0.txt**]() - Due to server upload restrictions, within this file, we only provide download links for publicly available data.
- [**Images**] - Image results about three important Gene_ID.

# How to Run?
- Prepare Python 3.7+ and Jupyter Notebook.
- The required Python environment and Conda environment for this model have been placed in [**requirement.txt**] and [**environment.yml**]. TRY `conda env create -f environment.yml
` and `pip insatll -r requirement.txt`
- Open INVEST.ipynb with Jupyter Notebook, and train in each cell in sequence from top to bottom.
- Add expression dataset and pre-trained network dataset for fine-tuning in the data folder.
- INVEST will automatically compute the number of genes in the expression dataset and the number of genes matching the pre-trained network. Based on these values, it will extract the TF-Target pairs from the pre-trained network.
- The training of INVEST is divided into two steps.
  - Firstly, train on the unlabeled expression data. After 200 iterations, the model will be automatically saved to the models folder (due to file size limitations, the author did not upload this model file).
  -  Secondly, fine-tune the above model on the pre-trained network, and perform another 2000 iterations for classification. Output the corresponding AUROC and AUPRC results.

# CID — Cow Images Dataset for Regression & Classification

A curated dataset of cattle images and metadata intended for computer vision and machine learning tasks such as weight estimation (regression) and breed classification. This repository provides links to the image archives and the primary CSV metadata file used in our experiments.

## Overview

Cattle livestock trading and management are growing rapidly. Accurate, automated tools for estimating weight and identifying breed from images can help producers, researchers, and agritech solutions make better decisions at scale. CID (Cow Images Dataset) was created to support research in these areas and to provide a reproducible dataset for benchmarking.

Key features:
- High-quality images of cows suitable for computer vision tasks.
- A CSV metadata file with labels and measurements for supervised learning.
- Separate archive of YouTube-sourced images for additional variability.

## Datasets

Download the dataset archives and metadata:

- Images archive: https://cid-21.s3.amazonaws.com/images.tar.gz
- YouTube images archive: https://cid-21.s3.amazonaws.com/yt_images.tar.gz
- Metadata CSV: https://cid-21.s3.amazonaws.com/dataset.csv

Dataset creation repository: https://github.com/bhuiyanmobasshir94/Cow-weight-and-Breed-Prediction

## Quick start

1. Download and extract the image archives:
```bash
wget https://cid-21.s3.amazonaws.com/images.tar.gz
tar -xzf images.tar.gz

wget https://cid-21.s3.amazonaws.com/yt_images.tar.gz
tar -xzf yt_images.tar.gz
```

2. Download the metadata CSV:
```bash
wget https://cid-21.s3.amazonaws.com/dataset.csv
```

3. Example: preview the CSV with Python (pandas)
```python
import pandas as pd

df = pd.read_csv("dataset.csv")
print(df.head())
print(df.info())
```

4. Example: load images for training (PyTorch example outline)
```python
from torchvision import transforms
from torchvision.datasets import ImageFolder
from torch.utils.data import DataLoader

transform = transforms.Compose([
    transforms.Resize((224, 224)),
    transforms.ToTensor(),
])

dataset = ImageFolder(root="images", transform=transform)
loader = DataLoader(dataset, batch_size=32, shuffle=True)
```

Adjust preprocessing and model architecture to suit regression or classification tasks.

## Citation

If you use this dataset in your research, please cite the dataset and the publication:

DOI: https://doi.org/10.1145/3542954.3543018

BibTeX:
```bibtex
@proceedings{10.1145/3542954,
  title = {ICCA '22: Proceedings of the 2nd International Conference on Computing Advancements},
  year = {2022},
  isbn = {9781450397346},
  publisher = {Association for Computing Machinery},
  address = {New York, NY, USA},
  location = {Dhaka, Bangladesh}
}
```

## Maintenance & Contact

Maintainer: bhuiyanmobasshir94  
Repository: https://github.com/bhuiyanmobasshir94/CID

If you find issues with the dataset (missing files, broken links, label errors), please open an issue in this repository with details and example files when possible.

## Acknowledgements

This dataset was assembled as part of the Cow-weight-and-Breed-Prediction project: https://github.com/bhuiyanmobasshir94/Cow-weight-and-Breed-Prediction

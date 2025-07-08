# 🌦️ Weather Image Classification using CNN and Transfer Learning

This project focuses on classifying weather conditions from images using **Convolutional Neural Networks (CNNs)** and **Transfer Learning**.  
It supports 8 weather classes:
- `cloudy`, `foggy`, `lightning`, `rainbow`, `rainy`, `rime`, `sandstorm`, `sunrise`
---
## 📁 Dataset

The dataset consists of images categorized into 8 folders, each representing a weather condition.  
Steps taken:
- Converted all images to `.jpg` and RGB format
- Dataset split into `train`, `validation`, and `test` (80/10/10)
---
## 🔧 Preprocessing

- All images resized to `240x240`
- Normalization applied (`/255.0` scaling or MobileNet preprocessing)
- One-hot encoding used for multiclass classification
- Data loaded using both manual loaders and `image_dataset_from_directory`
---
## 🧠 Models Implemented
### 1. CNN from Scratch
- Built with 4 convolutional blocks
- Batch normalization, max pooling, dropout
- Flatten and dense layers for classification
- Performance reached ~50% accuracy on validation

### 2. Transfer Learning: **MobileNet**
- Pretrained `MobileNet` used as a base
- **Fine-tuned**:  
  - **Top 60 layers frozen**  
  - **Remaining layers unfrozen and trained**
- Added `GlobalAveragePooling2D`, `Dense`, and `Dropout` layers
- Achieved ~94% validation accuracy
---
## 🏁 Training Details

- Optimizer: Adam
- Loss: Categorical Crossentropy
- Metrics: Accuracy
- Callbacks used:
  - `EarlyStopping`
  - `ReduceLROnPlateau`
---
## 📈 Results

- MobileNet model performed significantly better than the custom CNN
- Training and validation graphs show stable learning with minimal overfitting
- Visualized predictions with color-coded correct/incorrect results
---
## 📷 Sample Output

- Model prediction visualization shows predicted vs true labels
- Correct predictions shown in green, incorrect in red
---

## ▶️ How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/weather-image-classification.git
   cd weather-image-classification

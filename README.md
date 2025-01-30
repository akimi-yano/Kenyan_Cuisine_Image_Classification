# Kenyan Cuisine Image Classification

### Project Summary:

This project creates a machine learning model that classifies images for Kenyan cuisines.

The notebook: `[name of the file here]` was used to train a food classification challenge held in Kaggle conducted by OpenCV University.

[Image HERE]

---

### Dataset Description:

The dataset consisted of `8174` images in **13 Kenyan food type** classes. Sample images of **KenyanFood13 dataset** and the number of images in each of the classes are shown below:

[IMAGE HERE] 

Out of these `8174` image samples, `6536` samples were provided as a training set; while the remaining `1638` comprised of the hidden test data to be used during evaluation.

This train data was further split into a `80-20` train-validation split to perform training and evaluation.

---

### Machine Learning Model Architecture:

I used pretrained model `swin_base_patch4_window7_224` and adjusted the output layer to match with the project's requirement which is **13**.

---

### Data Augmentation:

For the training dataset, I applied the following data augmentation and resising and rescaling to avoid overfitting:

```
train_transform = transforms.Compose([
    transforms.Resize((224, 224)),
    transforms.RandomHorizontalFlip(),
    transforms.RandomRotation(20),
    transforms.ColorJitter(0.3, 0.3, 0.3),
    transforms.ToTensor(),
    transforms.Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225]),
])
```

---

### Training Hyperparameters:

* Epochs: `50`
  
* Optimizer: `SGD`

* Initial Learning Rate: `0.0001`

* LR scheduler: `lr_scheduler`

* Batch size: `8`

---

### Loss and Metric Plots:

[IMAGE HERE]

---

### Accuracy on Test Dataset for Kaggle Submission

The configurations discussed above, yielded a score of **0.80801** on the Kaggle's Leaderboard.

[IMAGE HERE]


  


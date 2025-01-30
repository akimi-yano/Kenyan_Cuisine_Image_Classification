# Kenyan Cuisine Image Classification

### Project Summary:

This project creates a machine learning model that classifies Kenyan cuisines' images into 13 different categories: {0: 'pilau', 1: 'nyamachoma', 2: 'masalachips', 3: 'mandazi', 4: 'ugali', 5: 'sukumawiki', 6: 'mukimo', 7: 'githeri', 8: 'matoke', 9: 'kukuchoma', 10: 'chapati', 11: 'kachumbari', 12: 'bhaji'}.

This notebook: `Kenyan_Cuisine_Classification.ipynb` was used to train a food classification challenge held in Kaggle conducted by OpenCV University.

---

### Dataset Description:

The dataset consisted of `8174` images in **13 Kenyan food type** classes. Sample images of **KenyanFood13 dataset** and the number of images in each of the classes are shown below:

![](./visuals/KenyanFood13.png?raw=true)

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

[TODO: ADD IMAGE HERE]

---

### Inferences:

[TODO: ADD IMAGE HERE]

---

### Accuracy on Test Dataset for Kaggle Submission

The configurations discussed above, yielded a score of **0.80801** on the Kaggle's Leaderboard.

![](./visuals/kenyan_cuisine_classification_kaggle_leaderboard.png?raw=true)

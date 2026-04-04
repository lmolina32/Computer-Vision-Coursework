# Task 1
- Items brought to class: scissors, headphones, and umbrella 
- Question: All the items brought to class where correctly classified, I had the hardest time detecting the umbrella. 
## Confusion Matrix For training 
![img](/practical4/imgs/confusion_matrix_task1_training.png)
## Confusion Matrix For validation  
![img](/practical4/imgs/confusion_matrix_task1_validation.png)
## Accuracies 
![img](/practical4/imgs/task1_accuracies.png)
## Notes
The Linear SVM correctly classified all features in the traning, but was misclassifying scissors with headphones in the validation dataset. 

# Task 2 
The classes choosen are: 
```python
my_object_list = ['umbrella','headphone','scissors', "Leopards", "Motorbikes", "airplanes", "bonsai", "crayfish",  "dollar_bill", "kangaroo"]
```
## Confusion Matrix For training 
![img](/practical4/imgs/confusion_matrix_task2_training.png)
## Confusion Matrix For validation  
![img](/practical4/imgs/confusion_matrix_task2_valdiation.png)
## accuracies 
![img](/practical4/imgs/task2_accuracies.png)
## Notes:
For fc2 and linear kernel on the 10 classes my results were 100% for both the testing and the training data. I think this is a sign of overfitting of our model. This was supported by presenting my items to the camera. The model couldn't accurately detect the umbrella object and kept misclassifying the object as an ariplane or bonsai. 

# Task 3 

## Linear + fc1 
### Confusion matrix for training
![img](/practical4/imgs/confusion_matrix_task3_training_fc1_linear.png)
### Confusion matrix for validatiaon 
![img](/practical4/imgs/confusion_matrix_task3_validation_fc1_linear.png)
### Accuracies 
![img](/practical4/imgs/task3_accuracies_fc1_linear.png)
## RBF + fc1 
### Confusion matrix for training
![img](/practical4/imgs/confusion_matrix_task3_training_fc1_rbf.png)
### Confusion matrix for validatiaon 
![img](/practical4/imgs/confusion_matrix_task3_validation_fc1_rbf.png)
### Accuracies 
![img](/practical4/imgs/task3_accuracies_fc1_rbf.png)

## Poly + fc1 
### Confusion matrix for training
![img](/practical4/imgs/confusion_matrix_task3_training_fc1_poly.png)
### Confusion matrix for validatiaon 
![img](/practical4/imgs/confusion_matrix_task3_validation_fc1_poly.png)
### Accuracies 
![img](/practical4/imgs/task3_accuracies_fc1_poly.png)


## Linear + fc2 
### Confusion matrix for training
![img](/practical4/imgs/confusion_matrix_task3_training_fc2_linear.png)
### Confusion matrix for validatiaon 
![img](/practical4/imgs/confusion_matrix_task3_validation_fc2_linear.png)
### Accuracies 
![img](/practical4/imgs/task3_accuracies_fc2_linear.png)

## RBF + fc2 
### Confusion matrix for training
![img](/practical4/imgs/confusion_matrix_task3_training_fc2_rbf.png)
### Confusion matrix for validatiaon 
![img](/practical4/imgs/confusion_matrix_task3_validation_fc2_rbf.png)
### Accuracies 
![img](/practical4/imgs/task3_accuracies_fc2_rbf.png)


## Poly + fc2 
### Confusion matrix for training
![img](/practical4/imgs/confusion_matrix_task3_training_fc2_poly.png)
### Confusion matrix for validatiaon 
![img](/practical4/imgs/confusion_matrix_task3_validation_fc2_poly.png)
### Accuracies 
![img](/practical4/imgs/task3_accuracies_fc2_poly.png)

## Notes
- The models with 100% accuracy in training and testing where 
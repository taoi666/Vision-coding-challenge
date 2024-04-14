## Car Part Perspective Evaluation Model

#### Project Overview
This project develops a deep learning model to evaluate the perspective of car parts from images. The model predicts scores reflecting the visibility and alignment of specific car parts, such as the hood and the back door, which are crucial for assessing vehicle damage in insurance claims. This README outlines the project setup, data preparation, training procedure, and how to use the model for inference.

#### Getting Started
Prerequisites
- Python 3.8 or above
- PyTorch
- Torchvision
- Pandas
- Numpy
- Matplotlib
- PIL
- scikit-learn

#### Installation
1. Clone the repository to your local machine:
```
git clone https://github.com/taoi666/Vision-coding-challenge.git
```
2. Install the required Python packages:
```
pip install torch torchvision pandas numpy matplotlib pillow scikit-learn
```

## Dataset
The dataset consists of images of vehicles with corresponding scores for the perspective quality of two car parts: the hood and the back door. Each image is labeled with scores ranging from 0.0 to 1.0, where 1.0 represents a perfectly visible and aligned car part, and 0.0 indicates that the part is not visible.

## Model
The model is based on the ResNet18 architecture, pre-trained on ImageNet, and fine-tuned to predict the two perspective scores from car images. It employs a regression approach, outputting continuous values between 0.0 and 1.0 for each car part.

## Evaluation

Model performance is evaluated using the Mean Squared Error (MSE) metric on the test dataset. Additionally, the model's predictions for the best and worst perspective evaluations are visualized to provide insights into its performance.

In addition to MSE, the Pearson correlation coefficient and p-value are calculated between the predicted and actual scores for each perspective evaluation. The p-value represents the probability of observing the data if the null hypothesis (no correlation) were true. A lower p-value indicates stronger evidence against the null hypothesis, suggesting a significant correlation between the predicted and actual scores.

## Conclusion

The Pearson correlation coefficient between the predicted and actual scores for Hood perspective evaluation is 0.982, indicating a strong positive correlation. The associated p-value is 0.0, suggesting that this correlation is statistically significant, and there is strong evidence against the null hypothesis of no correlation.

Similarly, for the Backdoor Left perspective evaluation, the Pearson correlation coefficient is 0.931, indicating a strong positive correlation. The p-value is also 0.0, indicating a statistically significant correlation between the predicted and actual scores for this perspective.

Overall, these results demonstrate that the model's predictions are highly correlated with the actual scores for both Hood and Backdoor Left perspectives, providing confidence in the model's performance.

## 📘 FashionMNIST-CAM: Class Activation Mapping with CNNs

This project demonstrates how to implement **Class Activation Maps (CAMs)** using a simple Convolutional Neural Network (CNN) trained on the Fashion MNIST dataset. CAMs provide visual insight into which regions of an image the CNN focuses on when making a classification decision.

---

### 📂 Dataset: Fashion MNIST

Fashion MNIST is a dataset of 70,000 grayscale images (28×28 pixels) of clothing items, with 10 distinct classes:

| Label | Class Name  |
| ----- | ----------- |
| 0     | T-shirt/top |
| 1     | Trouser     |
| 2     | Pullover    |
| 3     | Dress       |
| 4     | Coat        |
| 5     | Sandal      |
| 6     | Shirt       |
| 7     | Sneaker     |
| 8     | Bag         |
| 9     | Ankle boot  |

---

### 🧠 Methodology & CAM Explanation

**Class Activation Maps (CAMs)** are used to highlight the most important regions of an image that influence a CNN’s prediction. This is achieved by:

1. **Using a CNN with a Global Average Pooling (GAP) layer** before the final Dense (softmax) layer.
2. During classification, each class in the Dense layer has a unique set of weights connecting to the last convolutional feature maps.
3. To generate a CAM:

   * For a specific class `c`, the corresponding weights from the Dense layer are multiplied with the output of the final convolutional feature maps.
   * The result is a **heatmap** that shows the areas in the image most influential for predicting that class.

For example:

* A **"Sandal"** CAM may highlight the sole shape.
* A **"Bag"** CAM may focus on the rectangular structure.
* A **"Shirt"** CAM might emphasize the collar or sleeve region.

This makes CAMs a great tool for **model interpretability**.

---

### 🛠️ Approach

1. **Preprocess Data**: Normalize pixel values, reshape to include channel dimension.
2. **Build Model**: Use a CNN with GAP layer and softmax output.
3. **Train**: Use categorical cross-entropy loss.
4. **Visualize CAMs**: Generate class-specific heatmaps overlayed on original images.

---

### 🎯 Output

* Original fashion image.
* Class Activation Map overlaid as a heatmap.
* Model prediction label.

---

### 💡 Contribution

* Demonstrates **explainable AI** on a well-known dataset.
* Teaches how to build and interpret CAMs.
* Helps visualize how CNNs distinguish between similar-looking classes (e.g., Shirt vs. T-shirt).

---

### 📈 Applications

* Model debugging and transparency.
* Educational purposes in CNN interpretability.
* Enhancing AI trust through visual explanations.


# 🌱 EcoVision AI

### AI-Powered Waste Classification & Recycling Assistant

EcoVision is an interactive **computer vision and machine learning application** that automatically identifies waste categories from images and provides recycling recommendations.

The project uses **TensorFlow, Keras, MobileNetV2 Transfer Learning, and Gradio** to provide a complete end-to-end waste classification system that can be trained and deployed directly from **Google Colab**.

---

## 🚀 Project Overview

Improper waste segregation is a major challenge in modern waste management. Different materials such as plastic, paper, glass, metal, cardboard, and organic waste require different disposal or recycling processes.

EcoVision uses **deep learning-based image classification** to recognize waste from photographs.

The system allows users to:

- Upload a custom waste dataset
- Automatically detect waste categories
- Train a deep learning classifier
- Upload waste images
- Predict the waste category
- View prediction confidence
- View top predictions
- Receive recycling recommendations
- Analyze model performance
- View prediction history
- Download the trained model

---

## ✨ Features

### 📦 Custom Dataset Support

EcoVision accepts a ZIP dataset organized by folders.

Example:

```text
waste_dataset.zip
│
├── cardboard/
│   ├── image1.jpg
│   ├── image2.jpg
│   └── ...
│
├── glass/
│
├── metal/
│
├── paper/
│
├── plastic/
│
└── trash/
```

The application automatically detects the class folders and calculates dataset statistics.

---

### 🧠 Deep Learning Classification

EcoVision uses **MobileNetV2 Transfer Learning**.

The pretrained MobileNetV2 network acts as a feature extractor while a custom classification head learns the waste categories in the user's dataset.

Architecture:

```text
Input Image
     ↓
Image Augmentation
     ↓
MobileNetV2
     ↓
Global Average Pooling
     ↓
Dropout
     ↓
Dense Layer
     ↓
Dropout
     ↓
Softmax Classification
     ↓
Waste Category
```

---

### 🔄 Image Augmentation

The training pipeline applies several augmentation techniques:

- Horizontal flipping
- Random rotation
- Random zoom
- Random contrast

This helps the model learn from variations in image orientation and appearance.

---

### 🔍 Waste Image Prediction

Users can upload an image through the interactive interface.

EcoVision returns:

- Predicted waste category
- Confidence percentage
- Confidence level
- Top-5 predictions
- Prediction probability chart
- Recycling recommendation

Example:

```text
Prediction:
PLASTIC

Confidence:
92.43%

Confidence Level:
VERY HIGH
```

---

### ♻️ Recycling Recommendations

EcoVision provides category-based recycling guidance.

Example categories include:

| Category | Recommendation |
|---|---|
| 📦 Cardboard | Place flattened cardboard in the appropriate recycling stream |
| 🍾 Glass | Separate glass and follow local recycling guidelines |
| 🥫 Metal | Place appropriate metal containers in metal recycling |
| 📄 Paper | Keep paper dry and reasonably clean |
| ♻️ Plastic | Check plastic type and local recycling rules |
| 🗑️ Trash | Check local waste-management guidelines |
| 🌿 Organic | Consider composting or organic-waste collection |
| 🔋 Battery | Use an appropriate battery/e-waste collection point |
| 💻 E-Waste | Use an authorized e-waste collection facility |

> Recycling rules vary by location. EcoVision's recommendations are informational and should be checked against local waste-management regulations.

---

## 📊 Interactive Dashboard

The application includes a dashboard showing:

- Total dataset images
- Number of waste categories
- Number of predictions
- Average prediction confidence
- Model status
- CPU/GPU status

The dashboard also displays the complete EcoVision workflow.

---

## 📈 Model Analytics

EcoVision provides several model evaluation tools.

### Training Accuracy

The application generates a graph comparing:

- Training accuracy
- Validation accuracy

### Training Loss

The application generates a graph comparing:

- Training loss
- Validation loss

### Classification Report

The application generates:

- Precision
- Recall
- F1-score
- Support
- Overall classification statistics

### Confusion Matrix

A confusion matrix is generated to visualize:

- Correct classifications
- Misclassifications
- Class-level performance

---

## 🧾 Prediction History

Every prediction made during the current application session can be recorded.

The history contains:

```text
Time
Prediction
Confidence
```

Users can:

- Refresh prediction history
- Clear prediction history
- Review previous predictions

---

## ⚙️ Model Management

The application supports:

- Saving trained models
- Loading previously trained models
- Viewing model architecture
- Downloading the trained `.keras` model

The model is stored as:

```text
ecovision_model.keras
```

Class names are stored separately in:

```text
class_names.json
```

Training history is stored in:

```text
training_history.json
```

---

# 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| **Python** | Core programming language |
| **TensorFlow** | Deep learning framework |
| **Keras** | Neural network development |
| **MobileNetV2** | Transfer-learning backbone |
| **NumPy** | Numerical computation |
| **Pandas** | Dataset analysis |
| **Matplotlib** | Visualization |
| **Seaborn** | Confusion matrix visualization |
| **Scikit-learn** | Model evaluation |
| **Pillow** | Image processing |
| **Gradio** | Interactive web interface |
| **Google Colab** | Development and execution environment |

---

# 📁 Project Structure

Although the project can be executed from a **single Google Colab cell**, the application automatically creates the following structure:

```text
/content/ecovision/
│
├── dataset/
│
├── models/
│   ├── ecovision_model.keras
│   ├── class_names.json
│   └── training_history.json
│
├── outputs/
│   ├── dataset_distribution.png
│   ├── accuracy.png
│   ├── loss.png
│   ├── prediction_probabilities.png
│   └── confusion_matrix.png
│
└── dataset_root.txt
```

---

# 📋 Requirements

You can run EcoVision directly in **Google Colab**.

### Python

Python 3.x

### Main Dependencies

```text
tensorflow
keras
gradio
numpy
pandas
matplotlib
seaborn
scikit-learn
pillow
```

The provided Colab code automatically installs the required additional packages.

---

# 🚀 Getting Started

## 1. Open Google Colab

Create a new notebook in Google Colab.

For faster training, enable GPU acceleration:

```text
Runtime
   ↓
Change runtime type
   ↓
Hardware accelerator
   ↓
GPU
```

---

## 2. Paste the Code

Copy the complete EcoVision code into **one Colab cell**.

Run the cell.

The application automatically:

1. Installs dependencies
2. Imports libraries
3. Creates project directories
4. Detects GPU availability
5. Builds the Gradio interface
6. Launches the application

---

## 3. Upload Dataset

Open:

```text
📦 Dataset
```

Upload your ZIP dataset.

Example:

```text
waste_dataset.zip
```

Then click:

```text
📂 Load Dataset
```

---

## 4. Prepare Dataset

Navigate to:

```text
🧠 Train Model
```

Click:

```text
🔧 Prepare Dataset
```

EcoVision automatically creates:

```text
80% Training Data
20% Validation Data
```

---

## 5. Train the Model

Select the number of epochs.

For example:

```text
8 epochs
```

Then click:

```text
🚀 Start Training
```

The application will display:

- Training progress
- Validation accuracy
- Validation loss
- Accuracy graph
- Loss graph

---

## 6. Classify Waste

Go to:

```text
🔍 Classify Waste
```

Upload a waste image.

Click:

```text
🔍 Analyze Waste
```

EcoVision will generate the prediction.

---

# 🧪 Example Workflow

```text
Upload Dataset
      ↓
Detect Waste Categories
      ↓
Analyze Dataset
      ↓
Prepare Training/Validation Data
      ↓
Apply Image Augmentation
      ↓
MobileNetV2 Feature Extraction
      ↓
Train Classification Head
      ↓
Validate Model
      ↓
Upload New Waste Image
      ↓
Generate Prediction
      ↓
Calculate Confidence
      ↓
Display Recycling Recommendation
```

---

# 📊 Model Evaluation

EcoVision evaluates the model using multiple metrics.

### Accuracy

Measures the percentage of correctly classified validation images.

### Precision

Measures how many predicted instances of a category were actually that category.

### Recall

Measures how many actual instances of a category were correctly identified.

### F1-Score

Combines precision and recall into a single metric.

### Confusion Matrix

Shows how predictions are distributed between actual and predicted categories.

---

# 🧠 Why MobileNetV2?

MobileNetV2 was selected because it provides a good balance between:

- Model size
- Computational efficiency
- Image classification capability
- Transfer learning performance

This makes it suitable for an educational and prototype waste-classification application that can run within Google Colab.

The pretrained ImageNet weights allow the model to reuse general visual features rather than learning every visual feature from scratch.

---

# 🎯 Use Cases

EcoVision can be used for:

### 🏠 Smart Home Waste Sorting

Assist users in identifying household waste categories.

### 🏫 Educational Applications

Demonstrate practical applications of:

- Computer vision
- Deep learning
- Transfer learning
- Image classification

### ♻️ Recycling Assistance

Provide preliminary information about the appropriate waste stream.

### 🏙️ Smart Waste Management

Serve as a prototype component for larger intelligent waste-management systems.

### 📱 Future Mobile Applications

The trained model could potentially be integrated into a mobile application for real-time waste recognition.

---

# 🔮 Future Improvements

Possible future versions could include:

- 📱 Android/iOS application
- 📷 Real-time camera classification
- 🌐 Cloud deployment
- 🗺️ Recycling-center locator
- 📍 Location-based recycling rules
- 🗑️ Smart-bin integration
- 🔔 Waste collection notifications
- 🧠 More advanced CNN architectures
- 🔥 Grad-CAM explainability
- 📦 Object detection for multiple waste items
- 🎥 Real-time video classification
- 🌎 Multilingual recycling guidance
- 📊 Admin analytics dashboard
- 🗄️ Database integration
- 🔐 User authentication
- ☁️ AWS deployment

---

# ⚠️ Limitations

EcoVision's performance depends heavily on the quality and diversity of the training dataset.

Potential limitations include:

- Poor-quality training images
- Class imbalance
- Similar-looking waste categories
- Poor lighting
- Occluded objects
- Unusual object angles
- Background interference
- Insufficient training data

A high confidence score does **not necessarily mean the prediction is correct**.

The system should therefore be treated as an AI-assisted classification tool rather than a guaranteed waste-disposal authority.

---

# 🔐 Privacy

Images uploaded to the application are processed within the Google Colab runtime.

Users should avoid uploading images containing unnecessary personal or sensitive information.

The Colab runtime is temporary, so files may disappear when the runtime is reset or disconnected.

---

# 📌 Important Dataset Considerations

For better results:

- Use multiple images per category.
- Include different orientations.
- Include different backgrounds.
- Include different lighting conditions.
- Avoid mislabeled images.
- Keep classes reasonably balanced.
- Include real-world examples rather than only studio photographs.

For example:

```text
Plastic
├── bottle_front.jpg
├── bottle_side.jpg
├── bottle_crushed.jpg
├── bottle_outdoor.jpg
└── bottle_indoor.jpg
```

is generally more useful than having hundreds of nearly identical photographs.

---

# 🧑‍💻 Project Highlights

EcoVision demonstrates practical implementation of:

```text
Python
   ↓
Data Processing
   ↓
Computer Vision
   ↓
Transfer Learning
   ↓
Deep Learning
   ↓
Model Evaluation
   ↓
Interactive UI
   ↓
AI Prediction
   ↓
Real-World Recommendation
```

This makes it suitable as a **portfolio, GitHub, academic, and machine-learning project**.

---

# 📜 License

This project can be released under the **MIT License**.

You may add an `LICENSE` file to the repository if you plan to distribute the project publicly.

---

# 👨‍💻 Author

**Dheeraj Chilla**

Computer Science & Engineering  
Interested in:

- Artificial Intelligence
- Machine Learning
- Data Science
- Computer Vision
- Full-Stack Development
- AI-powered Applications

---

# ⭐ If You Like This Project

If EcoVision was useful, consider:

- ⭐ Starring the repository
- 🍴 Forking the project
- 🐛 Reporting issues
- 💡 Suggesting improvements
- 🤝 Contributing new features

---

## 🌱 EcoVision AI

> **See Waste. Understand Waste. Manage Waste Smarter.**

# 🤖 Module 34: Scikit-Learn, TensorFlow & PyTorch AI/ML Master Sheet (30 Formulas)

Complete reference for 30 essential Machine Learning and Deep Learning code templates in Scikit-Learn, PyTorch, and TensorFlow / Keras categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner Scikit-Learn ML Templates (1 - 10)

```python
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, confusion_matrix

# 1. Train-Test Split Dataset (80% Train, 20% Test)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# 2. Standardize Features (StandardScaler)
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

# 3. Train Logistic Regression Classifier
model = LogisticRegression()
model.fit(X_train_scaled, y_train)

# 4. Predict Labels on Test Data
y_pred = model.predict(X_test_scaled)

# 5. Evaluate Model Accuracy
acc = accuracy_score(y_test, y_pred)

# 6. Generate Confusion Matrix
cm = confusion_matrix(y_test, y_pred)

# 7. Train Random Forest Classifier
from sklearn.ensemble import RandomForestClassifier
rf = RandomForestClassifier(n_estimators=100)
rf.fit(X_train, y_train)

# 8. Train Linear Regression Model
from sklearn.linear_model import LinearRegression
lr = LinearRegression()
lr.fit(X_train, y_train)

# 9. Label Encoder for Categorical Target Variable
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
y_encoded = le.fit_transform(y_labels)

# 10. Compute Mean Squared Error (MSE)
from sklearn.metrics import mean_squared_error
mse = mean_squared_error(y_test, y_pred)
```

---

## 🟡 Level 2: Medium / Intermediate PyTorch Deep Learning Templates (11 - 20)

```python
import torch
import torch.nn as nn
import torch.optim as optim

# 11. Check GPU / CUDA Availability in PyTorch
device = torch.device("cuda" if torch.cuda.is_available() else "cpu")

# 12. Create PyTorch Tensors from Python Lists or NumPy Arrays
x_tensor = torch.tensor([[1.0, 2.0], [3.0, 4.0]], device=device)

# 13. Define Neural Network Architecture in PyTorch
class NeuralNet(nn.Module):
    def __init__(self, input_dim, hidden_dim, output_dim):
        super(NeuralNet, self).__init__()
        self.fc1 = nn.Linear(input_dim, hidden_dim)
        self.relu = nn.ReLU()
        self.fc2 = nn.Linear(hidden_dim, output_dim)
        
    def forward(self, x):
        out = self.fc1(x)
        out = self.relu(out)
        out = self.fc2(out)
        return out

# 14. Initialize Model, Loss Function, and Optimizer
model_pt = NeuralNet(input_dim=10, hidden_dim=64, output_dim=2).to(device)
criterion = nn.CrossEntropyLoss()
optimizer = optim.Adam(model_pt.parameters(), lr=0.001)

# 15. PyTorch Single Training Step (Zero Grad, Forward, Loss, Backward, Step)
optimizer.zero_grad()
outputs = model_pt(inputs.to(device))
loss = criterion(outputs, targets.to(device))
loss.backward()
optimizer.step()

# 16. Switch PyTorch Model to Evaluation Mode (Disables Dropout/BatchNorm)
model_pt.eval()
with torch.no_grad():
    predictions = model_pt(X_test_tensor)

# 17. Save PyTorch Model Weights to Disk
torch.save(model_pt.state_dict(), 'model_weights.pth')

# 18. Load PyTorch Model Weights from Disk
model_pt.load_state_dict(torch.load('model_weights.pth'))

# 19. Convert PyTorch Tensor back to NumPy Array
array_out = predictions.cpu().numpy()

# 20. Reshape / Flatten Tensor in PyTorch
flattened = x_tensor.view(-1, 4)
```

---

## 🔴 Level 3: Hard / Advanced TensorFlow & Keras Deep Learning Templates (21 - 30)

```python
import tensorflow as tf
from tensorflow import keras

# 21. Check GPU Devices in TensorFlow
gpus = tf.config.list_physical_devices('GPU')

# 22. Build Sequential Keras Neural Network Model
model_tf = keras.Sequential([
    keras.layers.Dense(128, activation='relu', input_shape=(10,)),
    keras.layers.Dropout(0.2),
    keras.layers.Dense(64, activation='relu'),
    keras.layers.Dense(1, activation='sigmoid')
])

# 23. Compile Keras Model (Optimizer, Loss, Metrics)
model_tf.compile(
    optimizer='adam',
    loss='binary_crossentropy',
    metrics=['accuracy']
)

# 24. Train Keras Model (Fit)
history = model_tf.fit(
    X_train, y_train,
    epochs=20,
    batch_size=32,
    validation_split=0.2
)

# 25. Evaluate Keras Model on Test Dataset
test_loss, test_acc = model_tf.evaluate(X_test, y_test)

# 26. Keras EarlyStopping Callback (Prevents Overfitting)
early_stop = keras.callbacks.EarlyStopping(monitor='val_loss', patience=3)
model_tf.fit(X_train, y_train, epochs=100, callbacks=[early_stop])

# 27. Build Convolutional Neural Network (CNN) Layer
cnn_layer = keras.layers.Conv2D(32, (3, 3), activation='relu', input_shape=(28, 28, 1))

# 28. Save Keras Complete Model to Disk (.h5 / SavedModel)
model_tf.save('my_model.h5')

# 29. Load Keras Model from Disk
loaded_model = keras.models.load_model('my_model.h5')

# 30. Model Summary Printout
model_tf.summary()
```

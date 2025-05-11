
# 🧠 Stress Detection Using Deep Learning: WESAD Dataset and Wearable Devices

## 📊 Dataset Description

* *Number of Participants*: 14 valid participants (out of 15, one excluded due to sensor issues).Dataset [wesad](https://archive.ics.uci.edu/dataset/465/wesad+wearable+stress+and+affect+detection)

* *Devices Used*:

  * **RespiBAN**: Chest-worn sensor, sampling frequency: 700 Hz.
  * **Empatica E4**: Wrist-worn device, with various sampling frequencies.

### Signals Collected from RespiBAN:

* **Accelerometer (ACC)**: Measures movement and orientation.
* **Respiration (RESP)**: Captures breathing patterns.
* **Temperature (TEMP)**: Monitors body temperature.
* **Impedance**: Assesses respiratory activity.
* **Electrocardiogram (ECG)**: Records the electrical activity of the heart.

### Signals Collected from Empatica E4:

* **Accelerometer (ACC)**: Captures movement and orientation data at 32 Hz.
* **Blood Volume Pulse (BVP)**: Measures heart rate and vascular activity at 64 Hz.
* **Electrodermal Activity (EDA)**: Monitors skin conductance at 4 Hz.
* **Temperature (TEMP)**: Measures skin temperature at 4 Hz.

### Dataset Labels:

* **1**: Baseline (resting state)
* **2**: Stress (period of induced stress)
* **3**: Amusement (period of laughter or joy)
* **4**: Meditation (relaxed, meditative state)
* **5, 6, 7**: Ignored (not relevant for analysis)

For analysis, labels were mapped into a binary format:

* **0** → Normal (Baseline, Amusement, and Meditation)
* **1** → Stress

## 🔍 Exploratory Data Analysis (EDA)

### 1. Feature Selection:

* Key features selected for the model:

  * *ECG*
  * *EDA*
  * *EMG* (if available)
  * *TEMP*
  * *RESP*
  * *Accelerometer axes (ACC\_X, ACC\_Y, ACC\_Z)*

### 2. Data Preprocessing:

 - Creating Time-Series Windows
 - Data Normalization
 - Train-Test Split
 - Class Imbalance Handling using (SMOTE)

## ⚙ Model Architecture

* *Model Type*: 1D Convolutional Neural Network (CNN).
* *Architecture*:

  * Three convolutional blocks with filters, kernel sizes, batch normalization, max pooling, and dropout for regularization.
  * Flattened output passed through two dense layers (32 and 16 neurons), with dropout applied.
  * *Final Layer: One neuron with **sigmoid* activation for binary classification (Normal vs. Stress).

## 🚀 Model Compilation and Training

* *Optimizer*: Adam (learning rate: 0.001)
* *Loss function*: Binary cross-entropy
* *Evaluation metric*: Accuracy
* *Training*: 10 epochs, batch size of 32
* *Validation*: 10% of the data used for validation to monitor performance and detect overfitting.

## 📈 Results and Evaluation

* The model was evaluated using metrics such as *accuracy, **precision, **recall, and **F1-score*.
* The results show that the model is effective at classifying stress and normal states, even with the imbalanced dataset.

# 🧠 Authors 
* Esraa Taha Mohamed
* Gehad Mahmoud Ahmed
* Nada Mamdouh Abdelomniem
* Roaa Mohamed Abdelzaim 
## Contact

For any inquiries, feel free to reach out:
- Name: Esraa Taha Mohammed
- Email: esraataha085@gmail.com

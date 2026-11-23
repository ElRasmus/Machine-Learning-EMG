**Decisions**

**7 Features**
- Choice: We plan to use the mean EMG envelope amplitude in each time window and express it as a percentage of the range between rest and maximum contraction measured during calibration.
- Reason: In our three prototype tests, the resting envelope was 0.12–0.14 V, while the mean amplitude during contraction was 0.71–0.86 V. The maximum also varied between tests, which is why we want to use the calibrated range.
- We don't know yet if the average amplitude is enough, or if a feature about frequency would add anything.

**8 Model**
- Choice — We chose Claude to help us compare two options for detecting muscle contractions: MyoTurtle’s current activation threshold and logistic regression, also we plan to train a logistic regression model in TinyML to predict rest or contraction from the average EMG envelope amplitude in each time window.
- Reason — We have two classes, and our prototype measurements showed higher average amplitudes during contraction than at rest. We chose Claude to help us analyze cases where the model makes a mistake.
- We don´t know which method detects weak contractions more reliably after the electrodes are reapplied? We will use only the training sessions to make this decision.

**9 Route**  
- Choice — We will train the model on a computer and deploy it on the ESP32 using TinyML. Each measurement and its prediction will be saved in Azure Database with a timestamp and session ID.
- Reason — The ESP32 already reads the EMG envelope and controls the LEDs, so MyoTurtle can use the prediction during the game without waiting for a Wi-Fi response.
- We don´t know how much time does the ESP32 need to classify each window, and is it fast enough to give feedback when the user contracts their hand?

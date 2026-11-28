# Machine-Learning-EMG

Machine learning module project. Data and code files are stored here.

## 1. Data acquisition

10 contractions, 3 sets per session, 3 sessions, 1 person. Disposable Ag surface electrodes. Three electrodes are placed on the forearm: two over the flexor digitorum superficialis muscle and one reference electrode at the elbow, over the olecranon. New electrodes were used for each session. The electrode distance was 2 centimeters. The signal is not the raw EMG: it is the smoothed analog envelope of the signal that the electrodes pick up, read by the ESP32 on the analog output. Sampling frequency: 1000 Hz.

## 2. Task

Close the dominant hand and hold for 2 seconds. Two classes: contraction and rest.

## 3. Trial and cue timing

A cue timer is played during each session. First the person contracts for 2 seconds and then rests for 1 seconds. After 10 repetitions, a set is completed. A session includes 3 sets with 2 hours minutes of rest between each set.

## 4. Sessions

3 sessions on 1 day. New electrodes in every session. Date: 11/23/2026.

## 5. Cleaning

The device has several analog stages that reduce noise: a band-pass filter from 20 to 397 Hz, a notch filter that reduces 60 Hz by more than 40 dB, and a full-wave rectifier with a linear envelope. Details and sources are in PROTOCOL.md. A recording is rejected if any sample reaches the limit of the converter, if samples are missing or the length does not match the expected duration, or if the signal is flat at a constant value, for example because an electrode is disconnected. Results are in QUALITY-REPORT.md. Recordings rejected: PENDING of 10.

## 6. Fair split

Sessions 1 to 3 train the model. Then a 4th session to test it. No session is in both. The test sessions are opened once, at the end.

## Team

| Member code | Name | GitHub user | Role | AI tool |
|---|---|---|---|---|
| A00842708 | Mariana Canizalez Rodriguez | MarianaCanizalez | Data adquisition website and code | Claude in VSCode |
| PENDING | Rasmus Leonardo Herrada Santos | PENDING | PENDING | PENDING |
| A00841431 | Juan Fernando Núñez Oseguera | JuanNunez731 | TEST SUBJECT | PENDING |
| A00842879 | Jorge Enríquez Córdova | jenriqzcorr | Training First Model | ChatGPT, Collab |

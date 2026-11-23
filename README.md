# Machine-Learning-EMG

Machine learning module project. Data and code files are stored here.

## 1. Data acquisition

10 recordings, 250 trials, 10 sessions, 1 person. Disposable Ag surface electrodes. Three electrodes are placed on the forearm: two over the flexor digitorum superficialis muscle and one reference electrode at the elbow, over the olecranon. New electrodes were used for each session. The electrode distance was (PENDING). The signal is not the raw EMG: it is the smoothed analog envelope of the sensor, read by the ESP32. Sampling frequency: PENDING Hz.

## 2. Task

Close the dominant hand and hold for 2 seconds. Two classes: contraction and rest.

## 3. Trial and cue timing

A cue video is played during each session. First the person contracts for 2 seconds and then rests for 4 seconds. After 5 repetitions, a set is completed. A session includes 5 sets with 5 minutes of rest between each set.

## 4. Sessions

10 sessions on 2 days. New electrodes in every session. Dates:PENDING.

## 5. Cleaning

The device has several analog stages that reduce noise: a band-pass filter from 20 to 397 Hz, a notch filter that reduces 60 Hz by more than 40 dB, and a full-wave rectifier with a linear envelope. Details and sources are in PROTOCOL.md. A recording is rejected if any sample reaches the limit of the converter, if samples are missing or the length does not match the expected duration, or if the signal is flat at a constant value, for example because an electrode is disconnected. Results are in QUALITY-REPORT.md. Recordings rejected: PENDING of 10.

## 6. Fair split

Sessions 1 to 7 train the model. Sessions 8 to 10 test it. No session is in both. The test sessions are opened once, at the end.

## Team

- Mariana Canizalez Rodriguez. Member code: A00842708. GitHub user: MarianaCanizalez. Role: PENDING. AI tool: Claude in VSCode
- Rasmus Leonardo Herrada Santos. Member code: PENDING. GitHub user: PENDING. Role: PENDING. AI tool: PENDING.
- Juan Fernando Núñez Oseguera. Member code: PENDING. GitHub user: PENDING. Role: PENDING. AI tool: PENDING.
- Jorge Enríquez Córdova. Member code: PENDING. GitHub user: PENDING. Role: PENDING. AI tool: PENDING.

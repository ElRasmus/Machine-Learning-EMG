# Protocol

## Method

One person is recorded. The person closes the dominant hand and holds the contraction for 2 s (class: move), then relaxes for 4 s (class: rest). One repetition of 2 s contraction and 4 s rest is one trial. Five trials make one set. A cue video tells the person when to contract and when to relax.

One session is one electrode placement. New electrodes are used in each session. Surface disposable Ag electrodes are placed on the forearm over the flexor digitorum superficialis muscle, two as the active pair and one reference electrode at the elbow. Each recording file contains one session.

## Signal chain and filters

1. Instrumentation amplifier (AD620). Gain 10x, then 680x, for a total gain of 6800.
   Source: Merletti R, Cerone GL. Tutorial. Surface EMG detection, conditioning and pre-processing: best practices. J Electromyogr Kinesiol 2020;54:102440.

2. Band-pass filter, Sallen-Key, order 10, from 20 Hz to 397 Hz.
   High-pass edge at 20 Hz. Sources: De Luca CJ, Gilmore LD, Kuznetsov M, Roy SH. Filtering the surface EMG signal: movement artifact and baseline noise contamination. J Biomech 2010;43(8):1573-1579. McManus L, De Vito G, Lowery MM. Analysis and biophysics of surface EMG for physiotherapists and kinesiologists. Front Neurol 2020;11:576729.
   Low-pass edge at 397 Hz. Source: De Luca CJ et al. J Biomech 2010;43(8):1573-1579.

3. Notch filter, order 2, at 60 Hz, with more than 40 dB of attenuation.
   Sources: McManus L, De Vito G, Lowery MM. Front Neurol 2020;11:576729. Merletti R, Cerone GL. J Electromyogr Kinesiol 2020;54:102440.

4. Full-wave rectifier and linear envelope. The analog output is read by the ESP32 on GPIO 34.
   Source: McManus L, De Vito G, Lowery MM. Front Neurol 2020;11:576729.

The ESP32 reads the analog envelope with its 12-bit ADC, averages 16 readings per sample and applies a smoothing of 0.8 times the previous value plus 0.2 times the new value. The loop period is 10 ms. The recorded signal is the envelope, not the raw EMG.

## Agreement

- Mariana Canizalez Rodriguez: I read the method and I agree.
- Rasmus Leonardo Herrada Santos: I read the method and I agree.
- Juan Fernando Núñez Oseguera: I read the method and I agree.
- Jorge Enríquez Córdova: I read the method and I agree.

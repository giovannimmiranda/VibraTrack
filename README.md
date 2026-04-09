# VibraTrack

VibraTrack is a real-time monitoring system designed to detect and estimate occupational exposure to hand-arm vibration (HAV) from power tools, helping to mitigate the risk of Hand-Arm Vibration Syndrome (HAVS). The system utilizes a hand-mounted wearable sensor and a mobile application to provide continuous feedback on vibration intensity and duration.

## System Overview

- Hardware Integration: Interfaces with a dorsal hand-mounted Movesense sensor via Bluetooth Low Energy (BLE) to capture triaxial acceleration.
- High-Resolution Sampling: Streams raw data at 833 Hz to ensure the capture of high-frequency tool vibrations.
- On-Device DSP Pipeline: Implements a real-time signal processing pipeline consisting of a 20–400 Hz band-pass filter using cascaded second-order IIR (biquad) sections.
- Activity Classification: Uses a rule-based classifier that evaluates RMS magnitude and spectral centroid features to distinguish tool usage (WORK) from human motion artifacts (REST).
- Exposure Metrics: Accumulates vibration energy to calculate cumulative exposure time and an $A(8)$-like value normalized to an 8-hour reference duration.

## Technical Stack

- Mobile App: Developed for iOS using Swift, SwiftUI, and UIKit, leveraging the MovesenseMds framework for sensor communication.
- Analysis & Validation: Utilized Python for offline signal inspection, spectral analysis (FFT/Welch PSD), and data augmentation to validate system robustness.

## Key Results
The prototype successfully separates vibrations from tools such as grinders, drills, and sanders from standard movements like walking. Validation testing showed 100% specificity in rejecting motion artifacts, ensuring that exposure accumulation is driven strictly by tool engagement.



Note: This repository is currently under construction as source files are being migrated from development environments. For a deep dive into the system's architecture, signal processing pipeline, and validation results, the full project report is available in the repository.

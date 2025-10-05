# Fully Connected Neural Network for Peak Detection
<img width="1620" height="425" alt="image" src="https://github.com/user-attachments/assets/1fe17988-7f0c-4b3d-badb-965df84e315b" />

The project investigates a signal represented as a sum of harmonic functions with added noise. For convenience, the signal is discretized into a set of 1000 points. A peak is defined as a point where the value significantly exceeds those of neighboring points. Experiments show that the `scipy.signal.find_peaks` function does not always accurately classify peaks, so a fully connected neural network is used for peak detection, as was proposed by V. D. Neverov.

## Project Structure
- `peak_detection.ipynb` — Jupyter notebook containing code for generating signals, building the dataset, creating and training the neural network, and visualising peaks.
- [signals_dataset.npz](https://mega.nz/file/P64ghRSD#vPIbyPSXhMC7EAI87WXTJ43hx0synSVvNN6r-EP2BIw) — pre-generated dataset of synthetic signals and corresponding peak masks.
- [signal_model.keras](https://mega.nz/file/TuAGHYYY#uRt_abCcxEvAzpSto0-RtznCOzu6Qc7PQ-A7nJemzhQ) — saved neural network model.
- [signal_model_weights.h5](https://mega.nz/file/y7pHkRQa#ouYWxpkJlBgz9-bFldJpGVUtfcdsP4f4yW3g8TiirUk) — saved weights of the neural network.

## Features
- Generates synthetic signals of length 1000 with multiple sinusoidal components and random noise.
- Constructs a mask array indicating positions of peaks.
- Saves the dataset in `.npz` format for reuse without regeneration.
- Implements a fully connected neural network that outputs a continuous array of length 1000 with values from 0 to 1 representing peak probabilities.
- Uses MSE as the training and evaluation metric.
- Provides visualization of true and predicted peaks.

## Estimating the MSE
The model was trained for 60 epochs and did not overfit, achieving a final MSE of 0.002730 for signals of 1000 points with an average of 17.5 peaks.

# Pitch Estimation Network

This repository contains the notebooks and documentation for a neural pitch estimation project inspired by a PiENet-style architecture.

The project focuses on estimating the fundamental frequency, also called pitch or F0, from microphone speech recordings. The system uses frame-based audio processing and a neural network that predicts pitch classes, including a separate unvoiced class for frames where no clear pitch is present.

## Project Overview

Pitch estimation is an important task in speech and audio processing. It is used in areas such as speech analysis, speaker characterization, voice conversion, prosody analysis, and other speech technology applications.

In this project, a PiENet-like neural network is trained to estimate pitch from speech recordings. The model works on short audio frames and predicts a pitch class for each frame. The implementation is organized into two main notebooks:

1. A training notebook, used to prepare the data, train the model, and save the checkpoint.
2. An evaluation notebook, used to load the saved checkpoint and reproduce the evaluation metrics and pitch contour plots.

## Repository Structure

```text
Pitch-Estimation-Network/
│
├── notebooks/
│   ├── Training_PitchEstimationNW.ipynb
│   └── Eval_PitchEstimationNW.ipynb
│
├── docs/
│   └── PitchEstimation_Documentation.pdf
│
├── README.md
├── requirements.txt
└── .gitignore
```

## Notebooks

### Training Notebook

```text
notebooks/Zaicanu_Antrenare_PitchEstimationNW.ipynb
```

This notebook contains the training pipeline for the pitch estimation network.

It includes:

- loading the PTDB-TUG dataset;
- pairing microphone audio files with reference pitch files;
- preprocessing the audio signals;
- converting audio into frames;
- constructing pitch classification targets;
- defining the PiENet-like neural network architecture;
- applying data augmentation;
- training the model;
- saving the best checkpoint.

### Evaluation Notebook

```text
notebooks/Zaicanu_Eval_PitchEstimationNW.ipynb
```

This notebook is used to evaluate the trained model.

It includes:

- loading the saved model checkpoint;
- reconstructing the preprocessing configuration;
- preparing the validation and test data;
- computing pitch estimation metrics;
- comparing predicted pitch with the reference pitch;
- plotting pitch contour visualizations.

## Documentation

The full project report is available in:

```text
docs/Zaicanu_PitchEstimation.pdf
```

The report includes:

- abstract;
- introduction;
- state of the art;
- theoretical background;
- implementation details;
- network architecture;
- training setup;
- evaluation metrics;
- experimental results;
- conclusion.

## Dataset

The project uses the PTDB-TUG pitch tracking dataset.

The dataset is not included in this repository because it can be large and should be downloaded separately.

To run the notebooks, the dataset should be available locally or in Google Drive, depending on how the paths are configured inside the notebooks.

## Model Description

The implemented model is a PiENet-like neural network for pitch estimation.

The model processes framed microphone speech and predicts one output class for each frame. The output classes include:

- one unvoiced class;
- multiple voiced pitch classes distributed on a logarithmic frequency scale.

The network uses a WaveNet-inspired structure with gated dilated convolutional blocks. This allows the model to use temporal context while keeping the architecture relatively lightweight.

## Evaluation Metrics

The evaluation notebook computes pitch estimation metrics such as:

- voicing decision error;
- voiced-frame pitch error measured in cents;
- accuracy within 50 cents.

The predicted pitch contours are also plotted against the reference pitch values to visually inspect the model performance.

## Requirements

The main Python libraries used in this project are listed in `requirements.txt`.

To install the required dependencies, run:

```bash
pip install -r requirements.txt
```

## Technologies Used

- Python
- Jupyter Notebook
- Google Colab
- PyTorch
- NumPy
- SciPy
- Matplotlib
- Audio signal processing
- Neural networks
- Pitch estimation

## How to Use

1. Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/Pitch-Estimation-Network.git
```

2. Open the project folder:

```bash
cd Pitch-Estimation-Network
```

3. Install the required libraries:

```bash
pip install -r requirements.txt
```

4. Open the notebooks from the `notebooks/` folder.

5. Run the training notebook first if you want to train the model:

```text
Zaicanu_Antrenare_PitchEstimationNW.ipynb
```

6. Run the evaluation notebook to load the checkpoint and evaluate the model:

```text
Zaicanu_Eval_PitchEstimationNW.ipynb
```

## Notes

The dataset and model checkpoints are not included in this repository.

Large files such as datasets, trained models, and temporary outputs should not be uploaded directly to GitHub. They should be stored separately, for example in Google Drive, and referenced from the notebooks.

## Author

Zaicanu Raluca-Maria

## License

This project is intended for academic and educational purposes.

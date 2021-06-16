# Realitime Sudoku Solver


This project will let you use your Computers Webcam (or your Phones Camera) as an Augmented Reality Camera for solving Sudoku puzzles.

To perform the OCR I use Python, Keras(Tensorflow), OpenCV, Numpy.

# This project consists of two folders:

- app - the JavaScript application that runs in the browser using a phone's camera or webcam
- tensorflow - the training and test code for the neural network used for the OCR

# Building the App

To build the application you will need to have node and yarn installed.

## Setup

```
cd app
yarn
yarn start
```

If you want to run the app locally then you will need to use something like `ngrok` to proxy `https` connections from your phone to your local server (most phones will not allow access to the camera unless the page is served over https).

Running in your desktop browser should work so long as you use the `localhost` connection as this bypasses the `https` requirement.

## Building

```
yarn build
```

# Training the neural network

The application invluces a pretrained network so you only need to do this if you want to train the network on new images.

## Setup

```
cd tensorflow
python3 -m venv venv
. ./venv/bin/activate
pip install -r requirements.txt
```

You may need to upgrade `pip` to the latest version if you have errors during the `pip install` phase.

```
pip install --upgrade pip
```

You will need to go into the `tensorflow/fonts` folder and unzip the fonts files. You'll then need to run the `list.sh` script to update the list of fonts.

```
sh list.sh
```

## Running the notebooks

```
jupyter notebook .
```

There are three notebooks - `train.ipynb`, `test-model.ipynb` and `generate_training_data.ipynb`

`train.ipynb` containts the training code. This is a very simple model so should be trainable on a CPU.

`test-model.ipynb` contains some code for showing which images the network is failing on.

`generate_training_data.ipynb` contains code for creating the training and test set data.

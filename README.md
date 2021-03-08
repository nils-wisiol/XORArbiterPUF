# XORArbiterPUF Simulator

This Simulation is the implementation for the paper **A Machine Learning-based Security Vulnerability Study on XOR PUFs for Resource-Constraint Internet of Things** [Here](https://ieeexplore.ieee.org/abstract/document/8473439). Please follow the following instructions to properly run the code on your machine. 

**NOTE: Because the code was originally developed using an old version of scikit-learn 0.19 in 2018, it is now modified, commented, and tested to ensure compatibility with the current scikit-learn version 0.24.0. You might need to play with neural network parameters to achieve better results. If you find this code helpful in your research, please consider the citation stated at the end of this page**


## Prerequisites
This project can be run using Anaconda or pip.

### Using Anaconda
* Install anaconda 3 for python packages on your laptop. Ensure to make it your main python interpreter by typing in the terminal (which python).

* After installing Anaconda 3, install the following packages: 

	- install term color from ( https://anaconda.org/omnia/termcolor )
	- install pypuf from ( https://pypi.org/project/pypuf/ )

* Navigate (sikit-learn/neural_network) directory in anaconda3. For instance, in Mac OSX it is usually located in this path ```/anaconda3/lib/python3.6/site-packages/sklearn/neural_network/```, and then replace ```_multilayer_perceptron.py``` with the modified one in this repository. If it will ask for your permission so accept and replace.

### Using Pip
* Clone this repository
* Inside the repository, create a virtual environment using `python3 -m venv venv`
* Activate it `source venv/bin/activate`
* Install term color and pypuf `python3 -m pip install "pypuf>=0.0.9" termcolor`

## How to run 

* This simulation can be run via command line.

```python main.py```

* You can pass all arguments via command line and you can modify them in ```get_args()``` method in the main.py. For instance, the following is an example of how to run 4-XOR of 64-bit stages using CRPs=400000 and chunk size=10000:

```python main.py --streams 7 --stages 64 --challenges 400000 --chunk 10000```

* You can also state your neural network model parameters from command line: for instance if you want 3 hidden layers and minibatch= 1000, use --layers 3 --minibatch 1000. You can define your custom argument from ( get_args()) method in the main.py.

* The tests can be run using pytest (install it using `python3 -m pip install pytest`)

```python3 -m pytest generator/__init__.py```

## How to cite 
```
@inproceedings{Aseeri2018,
  doi = {10.1109/iciot.2018.00014},
  url = {https://doi.org/10.1109/iciot.2018.00014},
  year = {2018},
  month = jul,
  publisher = {{IEEE}},
  author = {Ahmad O. Aseeri and Yu Zhuang and Mohammed Saeed Alkatheiri},
  title = {A Machine Learning-Based Security Vulnerability Study on {XOR} {PUFs} for Resource-Constraint Internet of Things},
  booktitle = {2018 {IEEE} International Congress on Internet of Things ({ICIOT})}
}
```

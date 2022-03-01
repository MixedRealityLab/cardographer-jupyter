# Cardographer Jupyter explorations

Some explorations with Jupyter for analysing Cardographer usage data.

## Getting started with Jupyter

### Python & Jupyter

If you already use python then hopefully you know how you want
to use python virtual environments, etc., so I'll leave that to 
you. If you don't already use python then...

It may be that Anaconda is the best place to start as it includes
[pandas](https://pandas.pydata.org/) and numpy, which should be
useful for data analysis - see
[pandas install notes](https://pandas.pydata.org/docs/getting_started/install.html).

In theory Anaconda should be easier, but will need more space (1GB?)
[Anaconda installation](https://docs.continuum.io/anaconda/install/).
Alternatively something using 
[miniconda](https://docs.conda.io/en/latest/miniconda.html) will be
smaller but more complicated to set up.

Install 
[miniconda](https://docs.conda.io/en/latest/miniconda.html).
Then, in a terminal, 
```
conda create -n jupyter
source activate jupyter
conda install pandas
```
Install jupyter:
```
conda install -c conda-forge notebook
conda install -c conda-forge nb_conda_kernels
conda install -c conda-forge jupyter_contrib_nbextensions
# modules we are specifically using...
conda install -c conda-forge openpyxl matplotlib librosa
conda install pip
```

### Run jupyter

Note, each time you open a new terminal you will need to switch
to the 'jupyter' environment before you can do the other bits...
```
source activate jupyter
```
Then run Jupyter:
```
jupyter notebook
```
A browser should open showing a view of your home directory.
Navigate to this directory.

Open, e.g. [mixedreality_analysis1](mixedreality_analysis1). 

### Creating a new python notebook

From the `New` dropdown select `Python 3 (ipykernel)`.
Rename the document (note, this is the filename).

## The Data

There is some example data in `data/`.
The initial example uses the "Detail" export, but not the "split",
so all frames in one session appear in the same column.

The first column is card ID.

The other column names are (currently) Cardographer web platform
session ID. Appending that string to the URL
[https://cardographer.cs.nott.ac.uk/platform/user/session/](https://cardographer.cs.nott.ac.uk/platform/user/session/
may give you information about the session (if you have permission).

## Working the data

See [mixedreality_analysis1](mixedreality_analysis1). 

So far this loads the data as a Pandas dataframe, parses the JSON
values and flattens the detail export array to give a list of 
frame titles and box names that the card is used in.

There are then a set of basic analyses which count how many groups
use each card in the six main boxes on the board.

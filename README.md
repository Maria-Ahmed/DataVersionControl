# Data Version Control
This AI-Makerspace workshop introduces Data Version Control (DVC), a paradigm same as git but for datasets. The directory contains all the necessary files that you are going to need to practice this workshop on your own. 

### Chief Reasons to Use DVC

1- Save and reproduce all of your data experiments
2- Debugging and testing
3- Compliance and auditing
4- Align software and data science teams



### Pre-Reqs
- Python3
- DVC (you can install it from here <a href='https://dvc.org/doc/install'>`here`</a>.



### Dataset
The `Global Warming Temperature` dataset used during the workshop is taken from Kaggle and can be found <a href='https://www.kaggle.com/datasets/sudalairajkumar/daily-temperature-of-major-cities'>`here`</a>.


### Components:

`dvc init`

`dvc add weather-data/2006-04-10.csv`

`dvc run -n filter -d filter.py -d weather-data/2006-04-10.csv -p filter.value -o output/filter python filter.py`

`dvc run -n training -p training.num_rows -d training.py -d output/filter -d weather-data/2006-04-10.csv -o output/training python training.py output/filter`

`dvc dag`



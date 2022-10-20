# Data Version Control
This AI-Makerspace workshop introduces Data Version Control (DVC), a paradigm same as git but for datasets. The directory contains all the necessary files that you are going to need to practice this workshop on your own. 

### Chief Reasons to Use DVC

<ol>
  <li>Save and reproduce all of your data experiments</li>
  <li>Debugging and testing</li>
  <li>Compliance and auditing</li>
  <li>Align software and data science teams</li>
</ol>

### Goal
Discover the need to use DVC and explore it's features in connection with GIT for a data pipeline.  


### Pre-Reqs
- Git
- Python3
- DVC (you can install it from <a href='https://dvc.org/doc/install'>`here`</a>.

### Project Structure
```bash
Global Mean Temperature Using DVC Project
├── .dvcignore 
├── dvc.lock
├── dvc.yaml
├── filter.py
└── params.yaml
├── training.py
```

### Dataset
At AI MakerSpace, we thoroughly believes in `Sustainable Development Goals`. This is why to show our empathetic inclination towards Climate Change goals, we will be incorporating *Global Temperature Data* to align with DVC basics.
The `Global Warming Temperature` dataset used during the workshop is taken from Kaggle and can be found <a href='https://www.kaggle.com/datasets/sudalairajkumar/daily-temperature-of-major-cities'>`here`</a>.


### Commands:

Convert an existing, unversioned project to a Git repository.
```bash 
git init 
```
Initialize a new local DVC repository.
 ```bash 
dvc init
```
Makes DVC aware of the target data and start versioning it.
 ```bash 
dvc add kaggle-merged-data/GlobalLand-MainTemperatures.csv
```

`dvc run -n filter -d filter.py -d kaggle-merged-data/GlobalLand-MainTemperatures.csv -p filter.value -o output/filter python filter.py`

`dvc run -n training -p training.num_rows -d training.py -d output/filter -d kaggle-merged-data/GlobalLand-MainTemperatures.csv -o output/training python training.py output/filter`: Helper for creating or updating pipeline stages.

`dvc dag`: Visualize pipelines as one or more stage dependency graphs.

`dvc repro`: Reproduces the whole pipeline in case of changes detected.

`dvc remote add -d`: Add remote storage for DVC projects.

`dvc push`:  Uploads and Downloads data to and from remote storage .

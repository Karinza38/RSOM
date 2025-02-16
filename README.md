 Rectifying Self Organizing Map (RSOM)
===============================

📎 **Paper 1:** Gölge, E., & Duygulu, P. 2013. Rectifying Self Organizing Maps for Automatic Concept Learning from Web Images

📎 **Paper 2:** Gölge, E., & Duygulu, P.. ConceptMap:Mining noisy web data for concept learning , The European Conference on Computer Vision (ECCV) 2014.

RSOM is an algorithm as an extension of well-known Self Organizing Map (SOM). It mimics SOM clustering and additionally detects outliers in the given dataset in the cluster level or instance level.
It is mainly used with image tasks but works as good with any other type of data.

## Installation

```
git clone https://github.com/erogol/RSOM.git
cd RSOM
python setup.py install
```

or

```
pip install git+https://github.com/erogol/RSOM.git
```

## Usage

Check ```sample_run.py``` for more.

```python
from rsom import RSOM

# Load Iris dataset
data = load_digits().data
data = torch.from_numpy(data).float()
print(data.shape)

# Initialize SOM
som = RSOM(data, alpha_max=0.05, num_units=49)

# Train SOM
som.train_batch(num_epoch=1000, verbose=True)

# Get salient instances and units
salient_insts = som.salient_insts()
salient_units = som.salient_units()
```



## Citation

```
@misc{golge2013rectifyingselforganizingmaps,
      title={Rectifying Self Organizing Maps for Automatic Concept Learning from Web Images},
      author={Eren Golge and Pinar Duygulu},
      year={2013},
      eprint={1312.4384},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/1312.4384},
}
```

## Example Visuals

Visuals are generated using ```sample_run.py``` and digits dataset.

<img src="https://github.com/erogol/RSOM/blob/master/visuals/2d_projection.png" width="600">

<img src="https://github.com/erogol/RSOM/blob/master/visuals/som_latice.png" width="600">

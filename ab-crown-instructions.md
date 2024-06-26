# $\alpha \beta$-CROWN Demo

## Installation

To install alpha-beta-crown, execute the following commands:

```sh
git clone --recursive https://github.com/Verified-Intelligence/alpha-beta-CROWN.git
```

Set up the conda environment:

```sh
cd alpha-beta-CROWN
conda env create -f complete_verifier/environment.yaml --name alpha-beta-crown
conda activate alpha-beta-crown
```

## Customization

Add the following model definition to `complete_verifier/model_defs.py`

```python
def mnist64fc():
    return nn.Sequential(
    nn.Flatten(),
    nn.Linear(784, 64),
    nn.ReLU(),
    nn.Linear(64, 64),
    nn.ReLU(),
    nn.Linear(64, 64),
    nn.ReLU(),
    nn.Linear(64, 64),
    nn.ReLU(),
    nn.Linear(64, 10),
)
```

## Execution

Run the following command:

```sh
python3 complete_verifier/abcrown.py --config ../custom_config.yaml
```

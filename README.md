# fake\_health\_claims\_data
Matthew Epland, PhD  
[phy.duke.edu/~mbe9](http://www.phy.duke.edu/~mbe9)  

Generate fake healthcare claims data. Currently only has a few service line-like fields, may be extended in the future.

## Cloning the Repository
ssh  
```bash
git clone git@github.com:mepland/fake_health_claims_data.git
```

https  
```bash
git clone https://github.com/mepland/fake_health_claims_data.git
```

## Installing Dependencies
It is recommended to work in a [python virtual environment](https://realpython.com/python-virtual-environments-a-primer/) to avoid clashes with other installed software. If you do not wish to use a virtual environment you can usually just run the first few cells of the notebook in question - useful when running on cloud-based virtual machines.
```bash
python -m venv ~/.venvs/fake_health_claims_data
source ~/.venvs/fake_health_claims_data/bin/activate
pip install -r requirements.txt
```

## Running Notebooks

```bash
jupyter lab fake_service_lines.ipynb
```

# Reading Outputs into Pandas from URL
```python
import pandas as pd
import io
import requests

url = 'https://github.com/mepland/fake_health_claims_data/raw/master/output/randomly_generated_service_lines.csv'
s = requests.get(url).content
dfp = pd.read_csv(io.StringIO(s.decode('utf-8')))

dfp.head(10)
```

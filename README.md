# Hashing-based Non-Maximum Suppression

## Installation
```
git clone https://github.com/microsoft/hnms.git
python setup.py install
```
The code has been tested with ubuntu16.4, python 3.6, cuda 10.1, pytorch 1.4 (1.5 as
well).

## Usage
```
import torch
from hnms import MultiHNMS

hnms = MultiHNMS(num=1, alpha=0.7)

# center x, center y, width, height
xywh = [[10, 20, 10, 20], [10, 20, 10, 20], [30, 6, 4, 5]]
conf = [0.9, 0.8, 0.9]
xywh = torch.tensor(xywh).float()
conf = torch.tensor(conf)
keep = hnms(xywh, conf)
print(keep)
```

## Reference
```
@article{DBLP:journals/corr/abs-2005-11426,
  author    = {Jianfeng Wang and
               Xi Yin and
               Lijuan Wang and
               Lei Zhang},
  title     = {Hashing-based Non-Maximum Suppression for Crowded Object Detection},
  journal   = {CoRR},
  volume    = {abs/2005.11426},
  year      = {2020},
  url       = {https://arxiv.org/abs/2005.11426},
  archivePrefix = {arXiv},
  eprint    = {2005.11426},
}
```


# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

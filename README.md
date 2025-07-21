# AgEagleVPRDataset

## overview
The datasets provided by the AgEagle are suitable for the aerial-based VPR task. We collect the corresponding satellite map and make them in a standard format for the VPR task evaluation.

The original datasets are publicly downloaded from the AgEagle website at [this link](https://ageagle.com/resources/?filter_by=data-set). 

Currently, there are several datasets suitable for the aerial-based VPR task, as illustrated below:

| Name | Num.Qr | Num.Db | Charac. | Status | 
|---------|---------|---------|---------|---------|
| University_campus   | 443  | 3036  | Various Orientation  | Completed |
| Industrial_estate   | 277  | 1665  | Thermal Image   | Completed |
| Village_switzerland   | 297  | 2300  | Farmland Scene   | Completed |


## how to use
The structure of provided dataset is the same as the other aerial-based geo-localization benchmark. The dataset is organized in a directory tree as such:

```
.
└── AgEagleVPR
    └── SubScene-One
        ├── map_database
        │   ├── @SubScene-One@longitude@latitude@patch_size.tif
        │   ├── .......    
        │   └── @SubScene-One@longitude@latitude@patch_size.tif
        │
        └── query_images
            ├── @query_index@longitude@latitude@.png
            ├── .......    
            └── @query_index@longitude@latitude@.png
```

The retrieval positive radius is set to 200 meters and the distance can be calculated by the coordinates of the image.

## baseline
We also simply tested the performance of the SOTA method on this dataset as the baseline. The selected method is SALAD and we retrained this model with a self-collected training dataset.

The retrieval recalls are given in the table below:

| Name | Method | R@1 | R@5 | R@10 |
|---------|---------|---------|---------|---------|
| University_campus   | SALAD(retrained)   | 51.02 | 72.69 | 81.04 |
| Industrial_estate   | SALAD(retrained)   | 84.48 | 93.14 | 94.95 |
| Village_switzerland   | SALAD(retrained)   | 75.42 | 94.95 | 97.98 |

## acknowledgements
Part of the AgEagle dataset is used in our previous work. And if you find this dataset useful for your research, please consider citing the paper:
```
@article{he2024leveraging,
  title={Leveraging map retrieval and alignment for robust UAV visual geo-localization},
  author={He, Mengfan and Liu, Jiacheng and Gu, Pengfei and Meng, Ziyang},
  journal={IEEE Transactions on Instrumentation and Measurement},
  volume={73},
  pages={1--13},
  year={2024},
  publisher={IEEE}
}
```

# Korean-English Church Sermon Translation Dataset

This repository contains the custom parallel dataset used in the Machine Learning final project **"Improving Korean-to-English Church Sermon Translation Quality Using a Transformer Model."**

Project team:

- Sunggeun Jung
- James Hills

## Dataset file

- [`sermon_300.xlsx`](sermon_300.xlsx)
- Worksheet used by the project: `Selected_300`
- Total size: 300 Korean-English sentence pairs
- Source groups: seven Korean church sermons
- Main fields: dataset ID, sermon title, original segment ID, Korean source, English reference translation, review status, and notes

## Experimental split

The project uses a complete-sermon split instead of randomly mixing sentences. This reduces leakage from closely related sentences in the same sermon.

| Split | Sentence pairs | Sermons |
|---|---:|---:|
| Training | 242 | 5 |
| Validation | 25 | 1 |
| Test | 33 | 1 |
| **Total** | **300** | **7** |

- Validation sermon: `하나님의 백성으로 산다는 것은`
- Test sermon: `더욱 명확히 기억하라`

## Use with the project code

Download `sermon_300.xlsx` and place it at:

```text
data/sermon_300.xlsx
```

Then create the train, validation, and test CSV files from the project root:

```powershell
python scripts\split_sermon.py
```

The dataset itself is kept outside the final code submission package. This public repository provides the dataset location required for reproducibility.

## Notes

The English sentences are reference translations, not model-generated outputs. No separate reuse license is granted by this repository; contact the project team before redistributing or reusing the data outside course review and reproducibility.

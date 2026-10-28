# House Price Prediction — Git and DVC

## Aim
To demonstrate Git version control for project files and DVC version control for a house price dataset, including modifying the dataset and restoring a previous version.

## Dataset
This project uses the House Prices: Advanced Regression Techniques dataset.

- `data/train.csv`: Training dataset managed by DVC.
- `data/train.csv.dvc`: DVC metadata file tracked by Git.
- `test.csv`: Test dataset.
- `sample_submission.csv`: Sample submission file.
- `data_description.txt`: Description of dataset columns.

## Tools Used
- Python
- Git
- DVC
- Visual Studio Code
- Windows PowerShell

## Practical Steps
1. Initialize Git and DVC in the project repository.
2. Add the original training dataset to DVC tracking.
3. Commit the DVC metadata file to Git.
4. Modify the first house's `SalePrice` to `123456` and record Version 2.
5. Restore the original DVC metadata from Git.
6. Run `dvc checkout` to recover the original dataset.
7. Verify that the first house's original `SalePrice` is `208500`.

## Important Commands

Initialize Git and DVC:
```powershell
git init
python -m dvc init
```

Track the dataset:
```powershell
python -m dvc add data/train.csv
git add data/train.csv.dvc .gitignore
git commit -m "Track original house price dataset with DVC"
```

Record a dataset change:
```powershell
python -m dvc add data/train.csv
git add data/train.csv.dvc
git commit -m "Update house price dataset to version 2"
```

Restore the original dataset metadata and data:
```powershell
git checkout 8408dea -- data/train.csv.dvc
python -m dvc checkout data/train.csv
```

Verify DVC status:
```powershell
python -m dvc status
```

## Result
Git was used to maintain project and dataset-metadata history, while DVC managed dataset versions. The modified dataset was recorded as a second version, and the original dataset was successfully restored and verified.

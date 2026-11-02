# Pascal VOC to YOLO

**English** | [繁體中文](README.zh-TW.md)

Two small Python scripts for preparing a YOLO (for example YOLOv7) dataset from Pascal VOC annotations. Only the Python standard library is used.

- `PascalVOCtoYolo.py` converts Pascal VOC XML annotations into YOLO `.txt` labels: one line per box with the class index, then the box center x and y, width, and height, normalized to 0–1. Objects whose class is not in `classes` are skipped.
- `ImgDataToYoloDatasets.py` shuffles the `.jpg` images in a folder and splits them 80/20. The 80% list is written to `train.txt` and the 20% list to `val.txt`.

## Usage

1. Edit the folder paths at the top of each script (`xml_folder`, `txt_folder`, `dataset_folder`) and the class list `classes` (same order as in your dataset YAML).
2. Run:
   ```bash
   python PascalVOCtoYolo.py
   python ImgDataToYoloDatasets.py
   ```

## Dataset used

[Monkey, Cat and Dog detection](https://www.kaggle.com/datasets/tarunbisht11/yolo-animal-detection-small) on Kaggle (classes: cat, monkey, dog).

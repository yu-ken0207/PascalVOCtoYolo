# Pascal VOC 轉 YOLO

[English](README.md) | **繁體中文**

兩支小型 Python 程式，把 Pascal VOC 標註整理成 YOLO（例如 YOLOv7）可用的資料集。只用到 Python 標準函式庫。

- `PascalVOCtoYolo.py` 把 Pascal VOC 的 XML 標註轉成 YOLO 的 `.txt` 標籤：每個框一行，依序是類別編號、框中心的 x 和 y、寬、高，數值都換算成 0–1。類別不在 `classes` 裡的物件會跳過。
- `ImgDataToYoloDatasets.py` 把資料夾裡的 `.jpg` 圖片打亂後按八二比例切分，八成的清單寫進 `train.txt`，兩成寫進 `val.txt`。

## 使用方式

1. 修改兩支程式開頭的資料夾路徑（`xml_folder`、`txt_folder`、`dataset_folder`）和類別清單 `classes`（順序要跟資料集的 YAML 設定檔一致）。
2. 執行：
   ```bash
   python PascalVOCtoYolo.py
   python ImgDataToYoloDatasets.py
   ```

## 使用的資料集

Kaggle 上的 [Monkey, Cat and Dog detection](https://www.kaggle.com/datasets/tarunbisht11/yolo-animal-detection-small)（類別：cat、monkey、dog）。

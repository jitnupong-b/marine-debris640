# MARINE-DEBRIS640 Dataset

This repository provides the **MARINE-DEBRIS640** dataset for floating waste
detection in rivers and canals in Thailand. The data are formatted for object detection
tasks (e.g., YOLO) and are split into train/validation/test subsets.

## Repository Structure

- `train/`  
  Images and labels used for training.

- `valid/`  
  Images and labels used for validation.

- `test/`  
  Images and labels reserved for final evaluation.

- `data.yaml`  
  Dataset configuration file (e.g., for YOLO), including paths and class
  definitions.

- `LICENSE`  
  MIT License for the code in this repository.

- `LICENSE-DATA`  
  CC BY 4.0 License for the dataset files.

- `README.md`  
  This documentation.

## Dataset Description

- **Task:** Floating / marine debris detection in waterways  
- **Format:** Object detection (YOLO-style images + label files)  
- **Splits:** `train`, `valid`, `test` directories  
- **Images:** `N_train`: 3600, `N_valid`: 112, `N_test`: 69 
- **Resolution:** 640×640
- **Classes:** defined in data.yaml `can`, `foam`, `plastic bottle`, `plastic`, `unknow`

## Data Collection

- Types of locations: urban canals, large rivers in Chonburi, Thailand 
- Time period of data collection: during daytime (09.00 - 18.00)
- Capture devices: action cameras and mobile phones  
- Any preprocessing steps: resizing to 640×640, cropping, color correction, filtering


## Annotation

Summarize the annotation process:

- Bounding boxes for debris were annotated using RoboFlow.  
- Each image was reviewed by at least one additional annotator.

## Train/Validation/Test Split

- The dataset is split into train/valid/test by images.  
- No image appears in more than one split.

## Usage

```bash
# Example: training with Ultralytics YOLO
yolo detect train \
  data=./data.yaml \
  model=yolov8n.pt \
  epochs=100 \
  imgsz=640

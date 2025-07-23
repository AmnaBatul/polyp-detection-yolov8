# Polyp Detection using YOLOv8 on Kvasir-SEG Dataset

This project performs real time polyp detection in endoscopic images using the **YOLOv8 object detection model**. It uses the **Kvasir-SEG** dataset for training and performs external inference on **CVC-ClinicDB** to test generalization.

## Implementation Details:

### Datset
* Primary Dataset – [Kvasir-SEG](https://www.kaggle.com/datasets/debeshjha1/kvasirseg)
A medical image dataset for polyp segmentation, including:
* RGB images of polyps (images/)
* Ground truth masks (annotated_images/)
* Bounding box annotations (bbox/*.csv)
The bounding box annotations were processed and converted into YOLO format.

* External Evaluation – [CVC-ClinicDB](https://www.kaggle.com/datasets/balraj98/cvcclinicdb)
  Used for inference only to assess model generalization.

### Model Architecture
The project uses **YOLOv8m** for single class object detection (polyp).

### Preprocessing
* Bounding box CSVs parsed and converted to YOLO format.
* Bounding box coordinates normalized.
* Dataset split: 80% Train / 20% Validation
* Images and annotations organized into YOLO’s expected directory structure.

### Training Configuration
* Model: YOLOv8m
* Input Size: 640x640
* Epochs: 200
* Early Stopping: Patience 30
* Batch Size: 16
* Augmentations:
  * Horizontal/Vertical Flip
  * Random Rotation
  * Hue/Saturation/Value jitter
  * Scaling and Translation
* YOLO Config: Custom polyp.yaml

### Evaluation Metrics
The model was evaluated on validation data using the following metrics:
* Precision
* Recall
* mAP@0.5
* mAP@0.5:0.95

## Results

| Metric       | Value |
|--------------|-------|
| Precision    | 0.933 |
| Recall       | 0.877 |
| mAP@0.5      | 0.936 |
| mAP@0.5:0.95 | 0.761 |

##### Contact
If you have any questions, feedback, or collaboration ideas, feel free to reach out:
* 📧 Email: amnabatul2@gmail.com 
* 🌐 GitHub: [AmnaBatul](https://github.com/AmnaBatul)

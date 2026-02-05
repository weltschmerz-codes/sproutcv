# SproutCV

SproutCV is a local desktop tool for automated measurement of sprout lengths from images.  
It uses computer vision techniques to detect and skeletonize sprouts, calculates their lengths in pixels and millimeters using a calibration CSV, and provides visualizations for easy verification.  

While currently designed as a local desktop application, SproutCV may serve as an open-source research tool for plant phenotyping and related studies in future iterations.

---

## Features

- Detects sprouts in images and measures their lengths automatically
- Handles batch processing of multiple images with calibration data
- Provides visual outputs:
  - Skeletonized sprouts
  - Annotated images with sprout lengths
- GUI supports drag-and-drop or file browsing for images and calibration CSV
- Modular design:
  - **GUI**: Desktop interface
  - **Core**: Sprout measurement and analysis logic
  - **IO**: File handling and data saving
  - **Utils**: Graph and image utilities

---

## Installation

### Requirements

- Python 3.10+
- OpenCV (`opencv-python`)
- NumPy
- Pandas
- NetworkX
- scikit-image
- Shapely
- Tkinter (usually included in Python)
- `tkinterdnd2` for drag-and-drop support

Install dependencies with:

```bash
pip install opencv-python numpy pandas networkx scikit-image shapely tkinterdnd2
```

---

## Input and Output Files

### Input
Calibration CSV Format
| file_name | pixel | distance |
|-----------|-------|----------|
| image1    | 120   | 50.0     |
| image2    | 110   | 50.0     |

- file_name – Image name without extension.
- pixel – Pixel length of calibration object.
- distance – Real-world length (mm) corresponding to the pixel value.
Pixel measurement can be done through image processing programs like ImageJ.

### Output
For each image, SproutCV generates:
- skeletons_<image_name>.jpg – Skeletonized sprouts
- length_measurement_<image_name>.jpg – Annotated image with sprout lengths
- sprout_lengths_<image_name>.csv – Sprout lengths in pixels and mm
Results are saved in a folder named after the image.




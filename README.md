# Object Detection and Counting with OpenCV

This project uses OpenCV to detect coin-shaped objects in an image with grayscale conversion, Gaussian blur, Otsu thresholding, morphological opening, and contour filtering.

## Repository contents

```text
opencv-object-counting-/
├── Object_Detection_and_Counting_with_OpenCV.ipynb
├── images/
│   └── sample.jpg
├── results/
│   └── output.png
├── LICENSE
├── .gitignore
└── README.md
```

- `images/sample.jpg` is the input coin image.
- `results/output.png` is the annotated result saved from the executed Colab notebook.
- The notebook source is [`Object_Detection_and_Counting_with_OpenCV.ipynb`](Object_Detection_and_Counting_with_OpenCV.ipynb).

## Requirements

The notebook runs in Google Colab and uses OpenCV, NumPy, and Matplotlib. These packages are available in the standard Colab Python runtime. To run locally, install them with:

```bash
pip install opencv-python numpy matplotlib
```

## Run the notebook

1. Open the notebook in Google Colab or Jupyter.
2. Run the cells from top to bottom.
3. When prompted, upload `images/sample.jpg`.
4. Review the intermediate grayscale, blurred, thresholded, and cleaned images, then inspect the final annotated output.

The saved Colab run reports **27 detected contours above the configured area threshold**. This is the notebook's threshold-based count for this input; it can vary if the image or processing parameters change.

## Method

1. Load the image and convert it from BGR to RGB for display.
2. Convert it to grayscale and apply a Gaussian blur.
3. Use inverse Otsu thresholding to create a binary mask.
4. Apply morphological opening to remove small noise.
5. Find external contours and count contours with area greater than 200 pixels.
6. Draw a green bounding box and label for each counted contour.

## Notes

This is a basic contour-based demonstration. The detected contour count depends on image quality, lighting, thresholding, and the selected minimum area; it should not be treated as a calibrated coin recognition result.

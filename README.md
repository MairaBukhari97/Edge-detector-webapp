# Edge Detection Visualizer

A Streamlit web app for experimenting with classical edge detection algorithms (Sobel, Laplacian and Canny). Upload an image, pick an algorithm, and watch the output change as you move the sliders.

## Project Description

This app lets you try a few classic edge detection methods on your own images and see how the settings change the result. It is meant for anyone learning computer vision, whether you are a student, a developer or a researcher who wants to understand how parameters like thresholds and kernel size affect the output.

**Algorithms included:**

- **Canny:** Blurs the image with a Gaussian filter, computes gradient magnitudes, then uses a lower and upper threshold to decide which edges to keep.
- **Sobel:** Measures how brightness changes along the X axis, the Y axis, or both, so you can pick out horizontal or vertical edges.
- **Laplacian:** Measures how quickly brightness changes overall, so it picks up edges in every direction at once.

## Features

- Loads `.jpg`, `.jpeg`, `.png` and `.bmp` images
- Runs Canny, Sobel or Laplacian edge detection
- Updates live as you change parameters, or waits for you to press Apply if you would rather tune everything first
- Shows the original and the result side by side
- Lists the current algorithm and settings below the images
- Rejects even kernel sizes, since OpenCV needs odd values

## Setup and Installation

You need Python 3.8 or newer.

### 1. Clone the repository

```bash
git clone https://github.com/MairaBukhari97/Edge-detector.git
cd Edge-detector
```

### 2. Create a virtual environment

**Windows**

```bash
python -m venv venv
venv\Scripts\activate
```

**macOS / Linux**

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the application

```bash
streamlit run edge_detection.py
```

Open the URL printed in the terminal, usually http://localhost:8501.

## Usage

1. Upload an image from the sidebar (browse or drag and drop).
2. Choose an algorithm.
3. Adjust the sliders. The preview updates as you go, unless real-time mode is off, in which case press Apply.
4. Compare the original and processed images side by side.

## The Algorithms

### Canny

A multi-stage detector. It blurs the image, computes gradients, thins the edges, then uses two thresholds to keep strong edges and any weak edges connected to them. It gives clean, thin lines and is usually the best first choice.

- **Parameters:** lower threshold, upper threshold, Gaussian blur kernel size, sigma
- **Good for:** photos, natural scenes, and extracting object outlines

### Sobel

Computes the first-order gradient along the X axis, the Y axis, or both. It is fast and simple, and it is useful when you care about edge direction.

- **Parameters:** kernel size, direction (X, Y or both)
- **Good for:** text, textures, industrial surfaces, and anything with strong horizontal or vertical structure

### Laplacian

Uses the second derivative of intensity, so it responds to changes in every direction at once. It picks up fine detail well but amplifies noise, so it often looks better on a smoothed image.

- **Parameters:** kernel size
- **Good for:** fine detail, thin edges, microscopy or medical images, and artistic effects
## Example Output

<p align="center">
  <img src="screenshots/Canny.JPG" alt="Canny Edge Detection Result" width="90%"><br>
  <strong>Figure 1:</strong> Canny Edge Detection
</p>

<p align="center">
  <img src="screenshots/Sobel.JPG" alt="Sobel Edge Detection Result" width="90%"><br>
  <strong>Figure 2:</strong> Sobel Edge Detection
</p>

<p align="center">
  <img src="screenshots/Laplacian.JPG" alt="Laplacian Edge Detection Result" width="90%"><br>
  <strong>Figure 3:</strong> Laplacian Edge Detection
</p>

---



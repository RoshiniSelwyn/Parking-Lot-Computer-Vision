# 🚗 Smart-Park-CV: Real-Time Parking Spot Detection

A Computer Vision system that detects available parking spots in real-time video feeds using OpenCV.

## 🌟 Features
- **Custom ROI Selector:** Manually define parking spots on any camera angle.
- **Real-time Detection:** Processes video frames to calculate occupancy instantly.
- **Adaptive Processing:** Uses Gaussian Blur and Adaptive Thresholding to handle varying lighting conditions.
- **Visual Dashboard:** Displays live counter of available spots (e.g., "Free: 12/50").

## 🛠️ Tech Stack
- **Python 3.x**
- **OpenCV** (Image Processing)
- **Pickle** (Coordinate persistence)
- **CVZone** (UI overlay utilities)

## ⚙️ How It Works
1. **Selection:** The `parking_picker.py` script lets you draw polygons over parking spots. These coordinates are saved to a `.pickle` file.
2. **Processing:** The `main.py` script:
   - Converts the video frame to grayscale.
   - Applies **Adaptive Thresholding** to create a binary image (Black & White).
   - Crops the image to the defined regions (ROI).
   - Counts the "white" pixels in each region.
   - **Logic:** High pixel count = High Texture (Car present). Low pixel count = Smooth (Empty road).

## 🚀 Usage

### 1. Define the Spots
Run the picker tool to set up your environment:
```bash
python parking_picker.py
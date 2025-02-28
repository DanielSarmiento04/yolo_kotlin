# YOLOv11 Object Detection for Android

A Kotlin-based Android implementation of YOLOv11 object detection using ONNX Runtime and OpenCV. This application demonstrates real-time object detection on Android devices with high performance and accuracy.

## Features

- YOLOv11 object detection on Android
- ONNX Runtime integration for efficient inference
- OpenCV for image processing
- Jetpack Compose UI
- Support for both CPU and GPU (CUDA) acceleration
- Visualization of detection results with bounding boxes and labels

## Requirements

- Android Studio Flamingo (2022.2.1) or newer
- Android SDK 24+ (Android 7.0 Nougat or higher)
- OpenCV for Android 4.6.0+
- ONNX Runtime 1.14.0+
- Kotlin 1.8.0+
- Jetpack Compose 1.4.0+

## Project Structure

- `YOLO11Detector.kt` - Core detector class implementing YOLOv11 model inference
- `MainActivity.kt` - Android activity with Compose UI implementation
- `Detection.kt` - Data classes for detections and bounding boxes
- `Config.kt` - Configuration settings for the detector

## Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/yolo_kotlin.git
   cd yolo_kotlin
   ```

2. Open the project in Android Studio

3. Download the YOLOv11 ONNX model:
   - Place your trained YOLOv11 ONNX model file named `best.onnx` in the `app/src/main/assets/` directory
   - Add a `classes.txt` file with class names (one per line) in the same directory
   - (Optional) Add test images in the assets folder

4. Build and run the application on your Android device or emulator

## Usage

The application demonstrates object detection on a sample image included in the assets folder. The main interface shows:

1. The processed image with bounding boxes around detected objects
2. Class labels and confidence scores for each detection
3. Inference time information
4. The total count of detected objects

## Customizing the Detector

You can adjust detection parameters in `Config.kt`:

```kotlin
// Default confidence threshold
const val DEFAULT_CONFIDENCE_THRESHOLD = 0.25f

// Default IoU threshold for NMS
const val DEFAULT_IOU_THRESHOLD = 0.45f
```

## How It Works

1. The ONNX model is loaded using ONNX Runtime
2. Images are preprocessed with letterboxing to maintain aspect ratio
3. The model runs inference on the preprocessed image
4. Postprocessing applies non-maximum suppression (NMS) to filter duplicate detections
5. Results are displayed with colored bounding boxes and labels

## Performance Notes

- CPU is used by default for compatibility with all Android devices
- GPU acceleration via CUDA can be enabled for compatible devices
- Threading is optimized based on available processors

## License

[Include your license information here]

## Acknowledgments

- YOLOv11 model architecture by [appropriate credit]
- ONNX Runtime for efficient model inference
- OpenCV for image processing capabilities
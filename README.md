

# COVID-19 Chest X-Ray Detector: A Real-time Android Application 
This repository contains the project file needed to compile the Android application for a Realtime Smartphone based COVID-19 chest X-Ray detector. You can download the project folder to your PC and than load it to your Android Studio or you can fork it directly to your Android Studio by the link provided in Code section. This Android project contains Tensorflow CNN model trained on thousands of X-Ray data from well curated and trusted repositories.It is trained to detect COVID-19 Chest X-Ray from Normal and Normal Viral Pneumonia infected Chest X-Ray images.

This Mobile Application version of the COVID-19 detection system is a lightweight inference system designed to be used in a rural area where internet connection is not reliable or not available at all. Server dependent application architecture is not an ideal solution in this circumstances. That’s why we came up with a solution where AI engine will run locally in the Mobile device and will do real time X-Ray image prediction with its on device hardware. However, prediction result will greatly very with device’s camera quality and processor power since the AI engine runs locally. We suggest to use a device equipped with a camera not less than 8MP and a SOC processor of ARM architecture issued not earlier than 2017.

This is a Research project and is not intended to use in real life scenario.Further studies and experimentation required for practical application.
## Getting Started

### Prerequisites
- [Android Studio (latest)](https://developer.android.com/studio/index.html)
- Android device

### Quickstart

1. Clone the repository and open the project in Android Studio
2. Build and run the project on your Android device


## Resources
- Link to [TensorFlow documentation](https://www.tensorflow.org/mobile/)
- Link to [Custom Vision Service Documentation](https://docs.microsoft.com/en-us/azure/cognitive-services/custom-vision-service/home)

Contact me razib.mustafiz[at]gmail.com for further assistance.

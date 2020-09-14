---
page_type: sample
languages:
- java
products:
- azure
description: "This application demonstrates a trained model exported from the Custom Vision Service in the TensorFlow format and add it to an Android application for real-time COVID-19 detection from Chest X-Ray."
urlFragment: cognitive-services-android-customvision
---

# COVID-19 Chest X-Ray Detector Real-time Android Application 
This repository contains the project file needed to compile the Android application for a Realtime Smartphone based COVID-19 chest X-Ray detector. You can download the project folder to your PC and than load it to your Android Studio or you can fork it directly to your Android Studio by the link provided in Code section. This Android project contains Tensorflow CNN model trained on thousands of X-Ray data from well curated and trusted repositories.It is trained to detect COVID-19 Chest X-Ray from Normal and Normal Viral Pneumonia infected Chest X-Ray images.

This Mobile Application version of the COVID-19 detection system is a lightweight inference system designed to be used in a rural area where internet connection is not reliable or not available at all. Server dependent application architecture is not an ideal solution in this circumstances. That’s why we came up with a solution where AI engine will run locally in the Mobile device and will do real time X-Ray image prediction with its on device camera hardware. However, prediction result will greatly very with device’s camera and processor quality since the AI engine runs locally. We suggest to use a device equipped with a camera not less than 8MP and a SOC processor of ARM architecture issued not earlier than 2017.

This is a Research project and is not intended to use in real life scenario.Further studies and experimentation required for practical application.
## Getting Started

### Prerequisites
- [Android Studio (latest)](https://developer.android.com/studio/index.html)
- Android device
- An account at [Custom Vision Service](https://www.customvision.ai) 
### Quickstart

1. Clone the repository and open the project in Android Studio
2. Build and run the sample on your Android device
### Replacing the sample model with your own classifier 
The model provided with the sample recognizes some fruits. To replace it with your own model exported from the [Custom Vision Service](https://www.customvision.ai) do the following, and then build and launch the application:
  1. [Create and train](https://docs.microsoft.com/en-us/azure/cognitive-services/custom-vision-service/getting-started-build-a-classifier) a classifer with the Custom Vision Service. You must choose a "compact" domain such as **General (compact)** to be able to export your classifier. If you have an existing classifier you want to export instead, convert the domain in "settings" by clicking on the gear icon at the top right. In setting, choose a "compact" model, Save, and Train your project.  
  2. Export your model by going to the Performance tab. Select an iteration trained with a compact domain, an "Export" button will appear. Click on *Export* then *TensorFlow* then *Export.* Click the *Download* button when it appears. A *.zip* file will download that contains TensorFlow model (.pb) and Labels (.txt)
  3. Drop your *model.pb* and *labels.txt* file into your Android project's Assets folder. 
  4. Build and run.

*This sample is tested on Pixel devices*

### Compatibility
For Tensorflow models exported **before May 1, 2018** you will need to subtract the mean values according to the table below based on your project's domain in Custom Vision. These models don't have the normalization baked in.

|  Project's Domain  | Mean Values (RGB) |
|--------------------|-------------------|
|  General (compact) |  (123, 117, 104)  |
|  Landmark (compact)|  (123, 117, 104)  |
|  Retail (compact)  |  (0, 0, 0)        |

The subtraction can be done by changing the values in the else path for hasNormalizationLayer just after resizedBitmap.getPixels in the **classifyImage** method (in *MSCognitiveServicesClassifier.java*) to do the subtraction::

```java
    {
        // This is an older model without mean normalization layer and needs to do mean subtraction.
        IMAGE_MEAN_R = 124.f;
        IMAGE_MEAN_G = 117.f;
        IMAGE_MEAN_B = 105.f;
    }
```

## Resources
- Link to [TensorFlow documentation](https://www.tensorflow.org/mobile/)
- Link to [Custom Vision Service Documentation](https://docs.microsoft.com/en-us/azure/cognitive-services/custom-vision-service/home)

# COVID-19-X-Ray-Detector

<h1 align="center">🚨 Android OpenCV + C++ + OpenGL ES — Real-Time Processing Project 🚨</h1>
<h3 align="center">Software Engineering Intern (R&D) — Technical Assessment</h3>

---

# ❗ <span style="color:red">PROBLEM STATEMENT</span>

You are required to build a minimal real-time Android application that:

- Captures camera frames  
- Sends them to **C++ (OpenCV)** through **JNI**  
- Applies simple processing (**Canny / Grayscale**)  
- Renders the result using **OpenGL ES 2.0**  
- Provides a small **TypeScript web viewer** that shows a processed frame  
- Uses proper Git structure

The challenge tests:
- Native C++ integration  
- OpenCV processing  
- OpenGL rendering  
- Android Camera handling  
- Web development basics  

---

# ⚠️ <span style="color:red">WHAT WAS DIFFICULT / THE REAL CHALLENGES</span>

### ❌ 1. Connecting Camera → JNI Efficiently  
Handling `SurfaceTexture` frames and converting them into a byte array for C++ was challenging.

### ❌ 2. Managing OpenCV in C++  
OpenCV Android NDK setup is tricky:
- Placing lib files correctly  
- CMake linking  
- Handling cv::Mat conversions (NV21 → RGBA)

### ❌ 3. Rendering Processed Frames With OpenGL ES  
Uploading live processed images as textures requires a full GL pipeline.

### ❌ 4. Combining Android + C++ + Web  
Cross-stack integration required careful architecture.

---

# ✅ <span style="color:green">HOW THE FINAL SOLUTION SOLVES THESE PROBLEMS</span>

### ✔ Camera2 + TextureView  
Smooth stream of frames with minimal latency.

### ✔ JNI Bridge  
Converts raw camera bytes → native C++ safely.

### ✔ OpenCV C++ Processing  
Canny edge detection / grayscale applied in real time.

### ✔ OpenGL ES Renderer  
Displays frames as textures at **15–30 FPS**.

### ✔ TypeScript Web Viewer  
Loads processed sample frame and displays simple stats.

---


---

## ⚡ Features Included (According to Assessment)

- 📸 **Real-time Camera Feed** using TextureView / SurfaceTexture  
- 🔁 **JNI Frame Pipeline** Java → C++ → Java  
- 🧩 **OpenCV C++ Processing** (Canny / Grayscale)  
- 🎨 **OpenGL ES 2.0 Rendering** of processed frames  
- 🌐 **TypeScript Web Viewer** for displaying a processed image  
- ⚙️ Clean modular architecture (Camera / JNI / C++ / GL / Web)  
- 🚀 Smooth 10–20 FPS performance on mid-range devices  

---

## 🛠️ Technologies Used

| Component | Technology |
|----------|------------|
| Native Processing | C++ + OpenCV (NDK) |
| Rendering | OpenGL ES 2.0 |
| Android Layer | Camera2 API + Java/Kotlin |
| JNI Bridge | Java ↔ C++ |
| Web Client | TypeScript + HTML |
| Build Tools | CMake, NDK, Gradle |

---

## 🚀 How to Run (Android)

1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/Android-OpenCV-GL-Assessment.git
   2. Open the project in **Android Studio**
3. Make sure the following SDK components are installed:
   - ✔ Android SDK 21+
   - ✔ NDK (Native Development Kit)
   - ✔ CMake
   - ✔ LLDB
4. Connect a physical Android device (USB debugging enabled)
5. Build & run the app:
   - Click **Run ▶**
   - Allow camera permissions
6. You should now see:
   - Raw camera feed
   - Processed (Canny/Grayscale) output rendered via OpenGL ES



🌐 How to Run (Web Viewer)

1. Go to the **web/** folder
2. Install dependencies:
   ```sh
   npm install
   tsc viewer.ts

 ``` Edge Detection Pipeline (Step-by-Step)

  1. Camera2 sends YUV frame to Java
2. Java passes byte array to JNI (native)
3. C++ converts NV21 → RGBA
4. OpenCV applies:
   - Grayscale OR
   - Canny Edge Detection
5. Processed frame is uploaded as OpenGL texture
6. OpenGL renders it to screen in real-time

🧪 Sample C++ Code (OpenCV Processing)

cv::Mat yuv(height + height/2, width, CV_8UC1, frameData);
cv::Mat rgba;

cv::cvtColor(yuv, rgba, cv::COLOR_YUV2RGBA_NV21); 
cv::Canny(rgba, rgba, 50, 150);

// rgba now contains processed frame for OpenGL

🔴 Place OpenCV native libs inside:

app/src/main/jniLibs/arm64-v8a/
app/src/main/jniLibs/armeabi-v7a/

🔴 Enable OpenGL ES 2.0:

<uses-feature android:glEsVersion="0x00020000" android:required="true" />

🔴 Performance:
- Disable logs inside frame loop
- Prefer RGBA over ARGB_8888 for faster uploads
```

# 📸 Demo

### **🧠 Image Classification**
![images](images/imc1.jpg)

---

### **✏️ Mnist Classification**
![images](images/mnist1.jpg)

---

### **🎯 Object Detection**
![images](images/obj1.jpg)

---

### **🎨 Color Transfer**
![images](images/colort1.jpg)

---

### **📷 OpenGLES Camera2 Pipeline**
![images](images/opgl1.jpg)

---

### **🪄 ARCore — Virtual Object Placement**
![images](images/arcore.gif)

---

## 🧱 Project Structure

```
Android-Vision/
│
├── app/
│   ├── java/
│   │   ├── activities/
│   │   ├── opencv/
│   │   ├── tflite/
│   │   ├── opengles/
│   │   └── arcore/
│   ├── jniLibs/
│   ├── res/
│   └── AndroidManifest.xml
│
├── models/
│   ├── mnist.tflite
│   ├── imagenet.tflite
│   └── object_detection.tflite
│
├── images/
│   ├── imc1.jpg
│   ├── mnist1.jpg
│   ├── obj1.jpg
│   ├── colort1.jpg
│   ├── opgl1.jpg
│   └── arcore.gif
│
└── README.md
```

---

## ⚡ Features Included

- ✨ Real-time CV processing  
- 🧠 Multiple ML demos  
- 📱 Native + GPU optimizations  
- 🎥 Live camera inference  
- 🛰️ ARCore world tracking  
- 🎨 Advanced color transformation  
- 🧩 Modular components for extension  

---

## 🛠️ Technologies Used

| Component | Technology |
|----------|------------|
| ML       | TensorFlow Lite |
| CV       | OpenCV (C++ / Java) |
| Graphics | OpenGL ES 2.0/3.0 |
| AR       | ARCore |
| Live Camera | Camera2 API |
| Language | Java/Kotlin + C++ |

---

## 🚀 How to Run

1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/Android-Vision.git
   ```
2. Open in Android Studio  
3. Sync Gradle  
4. Connect physical Android device  
5. Click **Run ▶**



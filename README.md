# 🎯 Face Attendance System

A **real-time automated attendance system** built using **Python, OpenCV, and Face Recognition** that detects faces through a webcam, identifies registered users, and logs attendance with timestamps.

This project helps eliminate manual attendance errors and provides a fast, secure, and scalable solution for classrooms, labs, and workplaces.

---

## ✨ Features

- 🎥 Real-time face detection using webcam
- 🧠 Face recognition using facial encodings
- 🕒 Automatic attendance marking with timestamp
- 🚫 Duplicate prevention with cooldown logic
- 👤 Unknown face detection support
- 💾 CSV/database attendance logging
- 🌙 Improved low-light preprocessing support
- 🖥️ Clean live camera UI with labels

---

## 🛠️ Tech Stack

- **Python**
- **OpenCV**
- **face_recognition**
- **NumPy**
- **Pandas**
- **CSV / Excel logging**

---

## 📂 Project Structure

```bash
face-attendance-system/
│── images/                 # Registered face images
│── attendance/            # Attendance CSV logs
│── main.py                # Main application file
│── encode_faces.py        # Face encoding generation
│── requirements.txt       # Dependencies
│── README.md
```

---

## ⚙️ Installation

> Recommended Python version: **Python 3.9 – 3.11**
>
> Some dependencies like `dlib` and `face_recognition` may require additional setup on Python 3.12+.

### 1) Clone the repository

```bash
git clone https://github.com/your-username/FaceAttendance_usingOpenCV.git
cd FaceAttendance_usingOpenCV
```

### 2) Create virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
```

For Windows:

```bash
.venv\Scripts\activate
```

### 3) Install dependencies

Upgrade pip first:

```bash
pip install --upgrade pip
```

Install all required packages:

```bash
pip install -r requirements.txt
```

If `face_recognition_models` fails:

```bash
pip install git+https://github.com/ageitgey/face_recognition_models
```

If `dlib` installation fails:

#### Windows

Install CMake first:

- https://cmake.org/download/

Then run:

```bash
pip install cmake
pip install dlib
```

#### Linux (Ubuntu/Debian)

```bash
sudo apt-get install build-essential cmake
sudo apt-get install python3-dev
pip install dlib
```

#### macOS

```bash
brew install cmake
pip install dlib
```

---

## 🧯 Troubleshooting

### Webcam not opening

Make sure:

- No other application is using the webcam
- Camera permissions are enabled
- Correct webcam drivers are installed

#### Windows Webcam Permissions

Go to:

```bash
Settings → Privacy & Security → Camera
```

Enable:

- Camera Access
- Let desktop apps access your camera

---

### `ModuleNotFoundError`

Install missing packages manually:

```bash
pip install opencv-python face_recognition numpy pandas
```

---

### `dlib` build errors

Try upgrading pip and wheel:

```bash
pip install --upgrade pip setuptools wheel
```

Then reinstall:

```bash
pip install dlib
```

---

### Low FPS or lag

- Reduce webcam resolution
- Close heavy background apps
- Use better lighting conditions

---

## ▶️ Usage

Run the project:

```bash
python main.py
```

### Flow

1. Webcam starts live feed
2. Face is detected frame-by-frame
3. Face encoding is matched with stored database
4. If matched → attendance logged
5. If not matched → shown as **Unknown**

---

## 🧠 How It Works

### Face Detection

Uses OpenCV webcam frames and locates faces in real time.

### Face Encoding

Each registered user image is converted into a **128-dimensional facial embedding**.

### Face Matching

Live embeddings are compared against stored encodings using distance similarity.

### Attendance Logging

Once matched:

- Name
- Date
- Time
- Status

are stored in CSV.

---

## 🐞 Known Issues

- Duplicate attendance if cooldown is disabled
- Accuracy may reduce in poor lighting
- Side-angle faces may reduce match confidence
- Webcam permission issues on some systems

---

## 🚀 Future Enhancements

- 📱 Web dashboard for attendance reports
- ☁️ MongoDB / Firebase integration
- 📧 Email daily attendance reports
- 🏫 Multi-classroom support
- 🧍 Liveness detection to prevent spoofing
- 📊 Analytics dashboard with charts

---

## 📸 Demo Use Cases

- College classroom attendance
- Office employee check-in
- Lab access monitoring
- Event participant verification

---

## 👨‍💻 Author

**Goutham Batthula**
Python Developer | Computer Vision | Full Stack Enthusiast

---

## 📜 License

This project is open-source and available under the **MIT License**.

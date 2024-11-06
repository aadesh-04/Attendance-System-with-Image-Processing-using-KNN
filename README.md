# Face Recognition Attendance System Using K-Nearest Neighbors (KNN)

This project is a Face Recognition-based Attendance System developed using OpenCV for image processing and K-Nearest Neighbors (KNN) for classification. It enables an automated method of taking attendance by recognizing and verifying faces and marking attendance in a CSV file.

## Features
- **Face Registration**: Adds a new student’s face to the database.
- **Face Recognition and Attendance Marking**: Recognizes registered faces and marks attendance automatically.
- **CSV Log File**: Attendance records are saved in a CSV file with the date and timestamp.
- **Voice Feedback**: Provides voice feedback upon successful attendance marking.

---

## Installation
1. **Clone the repository**:
   ```bash
   git clone <your-repository-link>
   cd <repository-directory>
Install Required Libraries:

bash
Copy code
pip install opencv-python-headless
pip install numpy
pip install scikit-learn
pip install pywin32
Download Haar Cascade: Download the haarcascade_frontalface_default.xml file from OpenCV’s GitHub repository and save it in the data/ folder.

Create Folders: Ensure you have a data/ folder for storing face data and a Attendance/ folder for CSV files if not already created.

bash
Copy code
mkdir data
mkdir Attendance
How to Use
Step 1: Register a New Face
Run the face_registration.py file:
bash
Copy code
python face_registration.py
Enter the student's name when prompted.
The system will capture and store the student’s face data by taking snapshots.
Step 2: Mark Attendance
Run the mark_attendance.py file:
bash
Copy code
python mark_attendance.py
The system will detect faces in real-time through your webcam and use KNN to identify them.
When a registered face is recognized, the system will:
Mark attendance with a timestamp in a CSV file named Attendance_<date>.csv.
Provide voice feedback indicating attendance has been taken.
Code Explanation
face_registration.py
Captures Face Data: Detects the face using Haar Cascade and captures multiple images, resizing them for consistency.
Data Serialization: Saves the faces and names in faces_data.pkl and names.pkl respectively for later use in attendance marking.
mark_attendance.py
Loads Data: Loads registered faces and names from the serialized data files.
Real-Time Face Recognition: Detects faces in the video feed, applies KNN to recognize them, and marks attendance in a CSV file.
Voice Feedback: Announces when attendance is successfully recorded.
File Structure
plaintext
Copy code
Attendance-System/
│
├── data/
│   ├── names.pkl              # Serialized file for storing names
│   └── faces_data.pkl         # Serialized file for storing face data
│
├── Attendance/
│   └── Attendance_<date>.csv  # CSV file with attendance records
│
├── face_registration.py       # Script to register a new face
├── mark_attendance.py         # Script to mark attendance using face recognition
├── haarcascade_frontalface_default.xml # Haar Cascade for face detection
└── README.md                  # Project documentation
Libraries Used
OpenCV: For video capturing and face detection.
NumPy: For efficient data handling and array manipulation.
scikit-learn: For implementing K-Nearest Neighbors (KNN) classification.
pickle: For saving and loading the face data and names.
pywin32: For text-to-speech functionality on Windows (optional).
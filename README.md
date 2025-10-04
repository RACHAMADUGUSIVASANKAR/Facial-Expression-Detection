# Facial Expression Detection

This project detects **yawning** and **smiling** in real-time using your webcam. It uses **dlib** for facial landmarks and **OpenCV** for image processing and Haar cascades.

---

## Folder Structure

```

FacialExpressionDetection/
│
├─ haarcascade_frontalface_default.xml
├─ haarcascade_smile.xml
│
├─ venv311/          # Python virtual environment (Python 3.11)
│
├─ yawnDetector.py   # Detects yawning using dlib facial landmarks
├─ smileDetector.py  # Detects smiles using Haar cascades
├─ shape_predictor_68_face_landmarks.dat  # dlib pre-trained model
├─ README.md
└─ .gitignore

````

---

## Requirements

- Python 3.11 (recommended)
- Virtual environment `venv311`  
- Packages (install inside venv):
  ```bash
  python -m pip install --upgrade pip
  python -m pip install numpy opencv-python dlib-bin


**Note:** Use `dlib-bin` for Windows to avoid compilation errors.

---
## Key Components
1. **yawnDetector.py**
   -	Type: Python script
   -	Purpose: Detects yawns in real-time using a webcam.
   -	How it works:
          *	Uses dlib to detect facial landmarks.
          *	Calculates the distance between top and bottom lip points to detect mouth opening.
          *	Tracks the number of yawns and displays it on the video.
   -	Dependencies: dlib-bin, numpy, opencv-python
   -	**Notes:**
         *	Make sure your shape_predictor_68_face_landmarks.dat file is in the same folder (or update the path).
         *	You’ve fixed issues like installing dlib-bin and handling Python 3.11 virtual env.


2. **smileDetector.py**
   - Type: Python script
   - Purpose: Detects smiles in real-time using a webcam.
   - How it works:
       *	Uses OpenCV Haar cascades (haarcascade_frontalface_default.xml and haarcascade_smile.xml) to detect faces and smiles.
       *	Draws rectangles around detected faces and smiles, displaying a message on the video.
   - Dependencies: opencv-python]

3. **shape_predictor_68_face_landmarks.dat**
     - Type: Data file for dlib
     - Purpose: Pre-trained model that identifies 68 facial landmarks for a detected face(eyes, mouth, nose, jaw, etc.).
     - Used by: yawnDetector.py
     - Where to get it:
          * Official dlib source: http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2
          *	Steps:
               1.	Download the .bz2 file.
               2.	Extract it (using WinRAR, 7-Zip, or similar). You’ll get shape_predictor_68_face_landmarks.dat.
               3.	Place it in your project folder (or anywhere and update the PATH in yawnDetector.py).
     - **Notes:** Must be present in the folder or path updated correctly.

4. **haarcascade_frontalface_default.xml & haarcascade_smile.xml**
   - Type: XML files (OpenCV Haar cascade classifiers)
   - These XML files are provided by OpenCV to detect faces and smiles.
   - Purpose:
       *	haarcascade_frontalface_default.xml → detects faces.
       *	haarcascade_smile.xml → detects smiles inside detected faces.
   -	Used by: smileDetector.py
   - Where to get it:
      1. haarcascade_frontalface_default.xml
          *	Detects faces in an image or video.
          *	Download link: https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_frontalface_default.xml
      2. haarcascade_smile.xml
          *	Detects smiles within detected faces.
          *	Download link: https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_smile.xml
      3. Steps for both:
          *	Download the XML files from the links above.
          *	Ensure your smileDetector.py paths match:
   - **Notes:** Keep them in a cascades/ folder or change the path in the script.

5. **Virtual Environment (venv311/)**
      - Type: Folder
      - Purpose: Isolates Python and package dependencies for this project.
      - Used for: Running scripts with the correct Python version (3.11) and installed packages.

6. **.gitignore**
   -	Type: Git configuration file
   -	Purpose: Specifies files/folders Git should ignore.
   -	Don’t commit sensitive files like your virtual environment (venv311) or .pyc files.
   -	Example in your project:
       * You can add venv311/, __pycache__/, and any large data files to avoid pushing them to GitHub.

7. **Other files**
   - README.md (if you have one): Explains your project.
   - Any CSV or images you might use for testing.
---

## Setup Steps

1. **Create virtual environment:**

   ```bash
   py -3.11 -m venv venv311
   venv311\Scripts\activate
   python --version       //Should show: Python 3.11.x
   ```

2. **Upgrade pip and install dependencies:**

   ```bash
   python -m pip install --upgrade pip
   python -m pip install numpy opencv-python dlib-bin   // dlib-bin avoids CMake errors on Windows.
   ```

3. **Download required files:**

   * dlib facial landmarks model:
     [shape_predictor_68_face_landmarks.dat](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)

   * Haar cascades for smile detection:
     
     * [haarcascade_frontalface_default.xml](https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_frontalface_default.xml)
     * [haarcascade_smile.xml](https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_smile.xml)

4. **Smile Detector**

     ```bash
     python smileDetector.py
     ```

     * Opens webcam
     * Detects faces and smiles
     * Press q to quit.
       
**Smile Detection Demo Video**

https://github.com/user-attachments/assets/ac82be02-30da-4c16-b3bb-2e321eb2502b

 5. **Run detectors:**

   * **Yawn Detector**

     ```bash
     python yawnDetector.py
     ```

     * Opens webcam
     * Detects mouth landmarks
     * Counts yawns
     * Press q to quit.
     
 **Yawn Detection Demo Video**

https://github.com/user-attachments/assets/d763dcdf-e5a4-4636-bf82-e5e80721ffd5

---

## Notes & Tips

* Make sure the virtual environment is **activated** before running scripts.
* Press **`q`** to stop the webcam window.
* Recommended to use Python 3.11 to avoid compatibility issues with `dlib`.

---

## Git Setup

To push this project to GitHub:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
```

---

## References

* [dlib face landmarks](http://dlib.net/face_landmark_detection.py.html)
* [OpenCV Haar Cascades](https://github.com/opencv/opencv/tree/master/data/haarcascades)

---

## 👨‍💻 Author

**Sivasankar R**  
AI & ML Engineering Student  
GitHub: [RACHAMADUGUSIVASANKAR](https://github.com/RACHAMADUGUSIVASANKAR)
Linkidin: [RACHAMADUGUSIVASANKAR](https://www.linkedin.com/in/sivasankar-rachamadugu/)


---

## 📄 License

This project is licensed under the MIT License.
```

Let me know if you'd like this formatted for a GitHub Pages site or want badges (e.g., build status, license, Python version) added!



Do you want me to do that next?
```

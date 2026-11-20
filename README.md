# edge-detection-opencv

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

---

## Developed By

- **Name: INDHUJA.K**
- **Register No: 212225040133** 

---
## Program
Load image and convert to grayscale:
```
img = cv2.imread("luffy.jpeg")

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

plt.imshow(gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()
```

Sobel Edge Detector:
```
sobel_x = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=3)
sobel_y = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=3)

sobel = cv2.magnitude(sobel_x, sobel_y)

sobel = cv2.convertScaleAbs(sobel)

plt.imshow(sobel, cmap='gray')
plt.title("Sobel Edge Detector")
plt.axis('off')
plt.show()
```

Roberts Edge Detector:
```
kernel_x = np.array([[1, 0],
                     [0, -1]])

kernel_y = np.array([[0, 1],
                     [-1, 0]])

roberts_x = cv2.filter2D(gray, cv2.CV_64F, kernel_x)
roberts_y = cv2.filter2D(gray, cv2.CV_64F, kernel_y)

roberts = cv2.magnitude(roberts_x, roberts_y)

roberts = cv2.convertScaleAbs(roberts)

plt.imshow(roberts, cmap='gray')
plt.title("Roberts Edge Detector")
plt.axis('off')
plt.show()
```

Laplacian Edge Detector:
```
laplacian = cv2.Laplacian(gray, cv2.CV_64F)

laplacian = cv2.convertScaleAbs(laplacian)

plt.imshow(laplacian, cmap='gray')
plt.title("Laplacian Edge Detector")
plt.axis('off')
plt.show()
```

Canny Edge Detector:
```
canny = cv2.Canny(gray, 50, 150)

plt.imshow(canny, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
plt.show()
```

## Output

###  Sobel Edge Detector
- Detects edges in horizontal and vertical directions  
- Produces gradient-based edge map
  
Load image and convert to grayscale:

<img width="300" height="508" alt="image" src="https://github.com/user-attachments/assets/8d40f1d1-69c0-4f59-93d1-bf9f1b07bfc2" />

Sobel Edge Detector:

<img width="282" height="512" alt="image" src="https://github.com/user-attachments/assets/12d0398a-354c-4a31-9996-9edace52ea2a" />

 

###  Roberts Edge Detector
- Detects edges using diagonal gradients  
- Sensitive to noise
   
<img width="285" height="507" alt="image" src="https://github.com/user-attachments/assets/737456b4-2954-42a0-9940-a97b638d3722" />


###  Laplacian Edge Detector
- Detects edges using second-order derivatives  
- Highlights rapid intensity changes  

<img width="292" height="511" alt="image" src="https://github.com/user-attachments/assets/f1e96b7c-2f94-4d24-bde4-057dc939247e" />

###  Canny Edge Detector
- Multi-stage edge detection  
- Produces clean and thin edges  

<img width="292" height="507" alt="image" src="https://github.com/user-attachments/assets/8fb2ead0-79e2-4089-a224-b67f117e3017" />

---

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.

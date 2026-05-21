# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
**Name:** SANJANA K L

**Register No:** 212224230241
  ### Ex. No. 02

#### 1. import libraries.
```python
import cv2
import matplotlib.pyplot as plt

```
#### 2. Read grayscale image.
```python
Gray_image = cv2.imread("WhatsApp Image 2026-05-12 at 14.16.29.jpeg", 0)

```
#### 3. Display Gray Scale Image.
```python
plt.figure(figsize=(6,6))
plt.imshow(Gray_image, cmap='gray')
plt.title("Gray Scale Image")
plt.axis("off")
plt.show()

```
#### 4. Read color image.
```python
Color_image = cv2.imread("WhatsApp Image 2026-05-12 at 14.32.43.jpeg")

```
#### 5.Convert BGR to RGB.
```python
Color_rgb = cv2.cvtColor(Color_image, cv2.COLOR_BGR2RGB)

```
#### 6.Display Color Image.
```python
plt.figure(figsize=(6,6))
plt.imshow(Color_rgb)
plt.title("Color Image")
plt.axis("off")
plt.show()

```
#### 7.Histogram of Gray Scale Image.
```python
hist_gray = cv2.calcHist([Gray_image], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Gray Scale Image")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_gray, color='black')
plt.xlim([0,256])
plt.show()

```
#### 8.Histogram of Blue Channel.
```python
hist_blue = cv2.calcHist([Color_image], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Blue Channel")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_blue, color='blue')
plt.xlim([0,256])
plt.show()

```
#### 9.Histogram Equalization.
```python
equalized_image = cv2.equalizeHist(Gray_image)
plt.figure(figsize=(6,6))
plt.imshow(equalized_image, cmap='gray')
plt.title("Equalized Image")
plt.axis('off')
plt.show()
```
#### 10.Histogram of Equalized Image
```python
hist_equalized = cv2.calcHist([equalized], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Equalized Image")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_equalized, color='green')
plt.xlim([0,256])
plt.show()
```


##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed
<img width="390" height="670" alt="image" src="https://github.com/user-attachments/assets/88c6fb38-0bdc-4724-aa46-91149e662211" />


- Histogram of original grayscale image is plotted
<img width="887" height="587" alt="image" src="https://github.com/user-attachments/assets/6f14dcad-b438-4e50-8946-cde9d9f7aa65" />

 

### Color Image Histogram Equalization

- Original color image is displayed
<img width="367" height="641" alt="image" src="https://github.com/user-attachments/assets/45bd4b0e-5697-4d5e-ac16-f4279edf878a" />

- Histogram of B, G, R channels is plotted
<img width="898" height="595" alt="image" src="https://github.com/user-attachments/assets/ad3f785b-df5a-4b46-aab7-b0f8567b80cd" />

### Equalization Image 

- Display Equalized Image
<img width="362" height="645" alt="image" src="https://github.com/user-attachments/assets/25099bad-1c3f-44b7-ac78-fb7a62d7a515" />

- Histogram of Equalized Image
<img width="911" height="595" alt="image" src="https://github.com/user-attachments/assets/9eec5b46-71c1-4475-a2da-66d1c0b68c78" />



## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.

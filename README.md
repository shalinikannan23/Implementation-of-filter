# EX-5 IMPLEMENTATION OF FILTERS
### Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.&emsp;&emsp;&emsp;**DATE:** 19.03.2024
### Software Required:
Anaconda - Python 3.7
### Algorithm:
- Step1: Import the require libraries.
- Step2: Read the image and convert to RGB mode.
- Step3: Apply various filter methods.
- Step4: Display the Output Images.
- Step5: End the Program.
### Program:
<table>
<tr>
<td width="60%">
  

#### Importing packages and reading image:
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('animal.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
```

</td>
<td>
  
```
Developed By: SHALINI K
Register Number: 212222240095
```
</td>
</tr>
</table>

<table>
<tr>
<td>

#### 1.) Smoothing Filters
##### i) Using Averaging Filter
```Python
kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
</td>
<td>
  
#### OUTPUT:<br>
<img src="https://github.com/shalinikannan23/Implementation-of-filter/assets/118656529/eb12399d-1b01-4c9c-8600-7418de8c712e">
</td>
</tr>
</tr>
<td width=50%>

##### ii) Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
WgtAvg=cv2.filter2D(img,-1,kernel1)
plot(img1,"Original Image",
      WgtAvg,"Weighted Average Filter")
```

</td>
<td>
  
#### OUTPUT:<br>
<img src="https://github.com/shalinikannan23/Implementation-of-filter/assets/118656529/ba8d52e4-d28e-46d5-a7d2-6273af47c9e5">
</td>
</tr>
</tr>
<td width=50%>
  
##### iii) Using Gaussian Filter
```Python
gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

</td>
<td>
  
#### OUTPUT:<br>
<img src="https://github.com/shalinikannan23/Implementation-of-filter/assets/118656529/6b9abb0a-f327-4eba-9df8-27f89ee415c2">
</td>
</tr>
</tr>
<td width=50%>
  
##### iv) Using Median Filter
```Python
# iv) Using Median Filter

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```

</td>
<td>
  
#### OUTPUT:<br>
<img src="https://github.com/shalinikannan23/Implementation-of-filter/assets/118656529/8ff05e15-c965-4790-b918-156e2b8ca6c6">
</td>
</tr>
</tr>
<td width=50%>

#### 2.) Sharpening Filters
##### i) Using Laplacian Kernal
```Python
kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```

</td>
<td>
  
#### OUTPUT:<br>
<img src="https://github.com/shalinikannan23/Implementation-of-filter/assets/118656529/051f49fb-f133-4ca8-9d87-7eff1a658b71">

</td>
</tr>
</tr>
<td width=50%>

##### ii) Using Laplacian Operator
```Python
new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```

</td>
<td>
  
#### OUTPUT:<br>
<img src="https://github.com/shalinikannan23/Implementation-of-filter/assets/118656529/3ff08d3e-8381-4fb8-b24f-0e0dacf4486a">
</td>
</tr>
</table>

### Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.

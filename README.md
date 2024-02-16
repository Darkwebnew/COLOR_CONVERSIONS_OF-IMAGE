# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By:
### Register Number: 


## Output:

### i) Read and display the image

```
import cv2
import matplotlib.pyplot as plt
image=cv2.imread('image.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('photography',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![1](https://github.com/Darkwebnew/COLOR_CONVERSIONS_OF-IMAGE/assets/143114486/18551302-92c2-4619-9bd3-62b2f047856e)

### ii)Write the image

```
import cv2
image=cv2.imread('image.jpg',0)
cv2.imwrite('news.jpg',image)
```

![2](https://github.com/Darkwebnew/COLOR_CONVERSIONS_OF-IMAGE/assets/143114486/664ff885-6ac5-437b-a299-f55042fa239a)


### iii)Shape of the Image

```
import cv2
image=cv2.imread('image.jpg',1)
print(image.shape)
```

![3](https://github.com/Darkwebnew/COLOR_CONVERSIONS_OF-IMAGE/assets/143114486/1abdffd4-d5a5-4ac4-a223-409695c4a08c)

### iv)Access rows and columns

```
import random
import cv2
image=cv2.imread('image.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
       image[i][j]=[random.randint(0,255),
                    random.randint(0,255),
                    random.randint(0,255)] 
cv2.imshow('image',image)
cv2.waitKey(0)
cv2.destroyAllWindows() 
```

![4](https://github.com/Darkwebnew/COLOR_CONVERSIONS_OF-IMAGE/assets/143114486/8bc9acd8-30ed-41b5-97a6-e8c7072e8af2)

### v)Cut and paste portion of image

```
import cv2
image=cv2.imread('image.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![5](https://github.com/Darkwebnew/COLOR_CONVERSIONS_OF-IMAGE/assets/143114486/0864e6b3-2f5f-4ea3-93e7-17953bd7da2a)

### vi) BGR and RGB to HSV and GRAY

```
import cv2
img = cv2.imread('image.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

![6](https://github.com/Darkwebnew/COLOR_CONVERSIONS_OF-IMAGE/assets/143114486/4a241f6b-5a5c-4285-a680-12e92c83a94b)

### vii) HSV to RGB and BGR

```
import cv2
img = cv2.imread('image.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

![7](https://github.com/Darkwebnew/COLOR_CONVERSIONS_OF-IMAGE/assets/143114486/37a5f239-01c9-46ec-9113-87d63ab3200e)


### viii) RGB and BGR to YCrCb

```
import cv2
img = cv2.imread('image.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

![8](https://github.com/Darkwebnew/COLOR_CONVERSIONS_OF-IMAGE/assets/143114486/d48ff263-39a4-49e9-abfb-363d55b88e05)

### ix) Split and merge RGB Image

```
import cv2
img = cv2.imread('image.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

![9](https://github.com/Darkwebnew/COLOR_CONVERSIONS_OF-IMAGE/assets/143114486/ebd8baca-ced4-4257-a025-a5232be9b656)


### x) Split and merge HSV Image

```
import cv2
img = cv2.imread("image.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

![10](https://github.com/Darkwebnew/COLOR_CONVERSIONS_OF-IMAGE/assets/143114486/d46d1c98-6f9f-46f4-bd4a-4900af92ea35)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.








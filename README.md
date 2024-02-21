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
### Developed By:karnan k
### Register Number: 212222230062


## Output:

### i) Read and display the image
```
import cv2
image=cv2.imread('pig.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('Piggy-Friends',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output
![image](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/87eae3bd-3b9f-488b-b407-a6dfb7e0b0fd)

### ii)Write the image

```
import cv2
image=cv2.imread('pig.jpg',0)
cv2.imwrite('test.jpg',image)
```
### output
![image](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/c05b5297-3d37-4b02-99ff-36dd7f234b57)

### iii)Shape of the Image

```
import cv2
image=cv2.imread('pig.jpg',1)
print(image.shape)
```
### output
![image](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/407154df-a565-45ab-ba5e-d96ef0a65423)

### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('pig.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
        random.randint(0,255),
        random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output

![image](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/17719edb-f4e7-433d-acf8-52d8737db253)


### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('pig.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### output

![image](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/3d7dfff7-2dee-4f24-a2c7-81e6e8836c8e)


### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('pig.jpg',1)
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

### output

![image](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/dac6a029-8f8d-4573-ba26-f9ee1ba9eebb)


### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('pig.jpg')
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

### output

![image](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/86f3ccab-b075-4050-9e65-f9ac8955ed5c)

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('pig.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

### output

![image](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/acb5e470-7c2f-4e61-a8a6-ee077133902f)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('pig.jpg',1)
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
### output

![image](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/802bef97-b707-4798-848c-794cd71de596)

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("pig.jpg",1)
img = cv2.resize(img,(200,200))
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

### output

![image](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/6a4ab099-53dd-4d7b-be13-9675a06ee7a8)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.








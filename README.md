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
image=cv2.imread('img',1)
cv2.imshow('image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output
![1](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/ad9f6826-a2f7-4397-8753-ee0571f08bbc)


### ii)Write the image

```
cv2.imwrite('test.jpg',image)
```
### output
![2](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/65774c4b-769c-43ee-b93b-4432723e3115)

### iii)Shape of the Image

```
print(image.shape)
```
### output
![3](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/b3c8a1a9-2555-429f-bc73-f7239718ef62)


### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('img',1)
for i in range (250,500):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
        random.randint(0,255),
        random.randint(0,255)] 
cv2.imshow('part',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### output

![4](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/04e34d31-a16f-45ee-b1f6-dc6da7c65bdb)


### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('img',1)
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### output

![5](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/c7a54a98-96be-4873-8f39-f4ac0610a3a3)



### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('img',1)
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

![6](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/1a251b78-a10f-43ae-8237-c9f370da585c)



### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('img')
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

![7](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/66a84adf-50a9-46ed-86ff-e5a7a023f3b8)


### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('img')
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

![8](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/5af6cbfe-88b0-4cd0-99aa-ee7ce7a32b25)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('img',1)
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


![9](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/e867748e-899d-4b3b-93d2-23eea20dcbc6)

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("img",1)
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

![10](https://github.com/karnankasinathan/COLOR_CONVERSIONS_OF-IMAGE/assets/118787064/b9b89d60-b0a4-4c74-9f8e-5a37ba28ccbf)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.








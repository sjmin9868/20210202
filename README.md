# 2021/02/02 미팅문서 사진

## 1. Original sampling 문제점
#### original image
![A](https://user-images.githubusercontent.com/78393745/106554609-13989f80-655f-11eb-94a1-55fa3b46daad.jpg)

#### 2:1 pixel sampling
![A_resize](https://user-images.githubusercontent.com/78393745/106554632-1dba9e00-655f-11eb-9870-f78831a9a771.jpg)
 * 전체적인 밝기 저하


## 2. Histogram matching
#### A_adjust
![A_adjust](https://user-images.githubusercontent.com/78393745/106554721-4d69a600-655f-11eb-9f29-60d086e343e0.jpg)
 * 0~255 pixel value에서 90%~100%에 해당하는 pixel은 saturation
 * histogram의 target 이미지

#### A_histeq
![A_histeq](https://user-images.githubusercontent.com/78393745/106554749-56f30e00-655f-11eb-9e91-907e13723692.jpg)
 * gamma correction 후 histogram equalization
 * histogram matching의 source 이미지

#### A_match
![A_match](https://user-images.githubusercontent.com/78393745/106554754-59edfe80-655f-11eb-859b-8c83396ff756.jpg)
 * A_match = imhistmatch(A_histeq, A_adjust)


## 3. Stretching에 적용
#### original image
<img src = "./A.jpg" width="640" height="360">
<img src = "./A.jpg">

#### histogram matching stretching
<img B = "https://user-images.githubusercontent.com/78393745/106555576-30ce6d80-6561-11eb-9704-ffa4fd551512.jpg" width="960" height="360">

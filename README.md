# 2021/02/02 미팅문서 사진

## 1. Original sampling 문제점
![A](https://user-images.githubusercontent.com/78393745/106554609-13989f80-655f-11eb-94a1-55fa3b46daad.jpg)
* original image

![A_resize](https://user-images.githubusercontent.com/78393745/106554632-1dba9e00-655f-11eb-9870-f78831a9a771.jpg)
* 2:1 검은 pixel sampling


## 2. Histogram matching
![A_adjust](https://user-images.githubusercontent.com/78393745/106554721-4d69a600-655f-11eb-9f29-60d086e343e0.jpg)
* A_adjust
 + 0~255 pixel value에서 90%~100%에 해당하는 pixel은 saturation
 - histogram의 target 이미지


![A_histeq](https://user-images.githubusercontent.com/78393745/106554749-56f30e00-655f-11eb-9e91-907e13723692.jpg)
* A_histeq
 - gamma correction 후 histogram equalization
 - histogram matching의 source 이미지


![A_match](https://user-images.githubusercontent.com/78393745/106554754-59edfe80-655f-11eb-859b-8c83396ff756.jpg)
* A_match
 - A_match = imhistmatch(A_histeq, A_adjust)

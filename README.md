# 2021/02/02 미팅문서 사진

## 1. Original sampling 문제점
#### original image
<img src = "./A.jpg">

#### 2:1 pixel sampling
<img src = "./A_resize.jpg">
 * 전체적인 밝기 저하


## 2. Histogram matching
#### A_adjust
<img src = "./A_adjust.jpg">
 * 0~255 pixel value에서 75%~100%에 해당하는 pixel은 saturation
 * histogram의 target 이미지

#### A_histeq
<img src = "./A_histeq.jpg">
 * gamma correction 후 histogram equalization
 * histogram matching의 source 이미지

#### A_match
<img src = "./A_match.jpg">
 * A_match = imhistmatch(A_histeq, A_adjust)


## 3. Stretching에 적용
#### original image
<img src = "./A.jpg">

#### histogram matching stretching
<img src = "./B.bmp">

## 4. Logarithmic contrast
<img src = "./original.bmp">
<img src = "./adaaptivetonemapped.bmp">

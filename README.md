# multi_cctv_tracking

[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](LICENSE)

## 시스템 설명 

팀장 : 김병철   
팀원 : 박형민, 서주영, 위재원, 이명원

### 데모파일 


### 1. 다중 CCTV 객체추적 시스템

>1) 지리정보시스템과 연계하여 CCTV를 지도에 등록
>2) CCTV에서 용의자를 객체처리(마우스 드래그 박스형식)
>3) 주위의 CCTV에서 객체를 추적해 용의자의 경로를 파악하는 시스템

### 2. 법보행 분석

>1) 수사관이 다중 CCTV 객체추적 시스템 활용
>2) 추적 데이터를 바탕으로 법보행 분석 데이터 확보
>3) 더욱 정확한 법보행 분석 모델



## 환경 설정 

### Conda 환경설정  (Recommended)

```bash
# Tensorflow CPU 환경
conda env create -f conda-cpu.yml
conda activate yolov4-cpu

# Tensorflow GPU 환경
conda env create -f conda-gpu.yml
conda activate yolov4-gpu
```

### Pip

pip 패키지 관리자를 최신으로 업데이트 해준다( 최소 19.0 이상 버전 )

```bash
# TensorFlow CPU
pip install -r requirements.txt

# TensorFlow GPU
pip install -r requirements-gpu.txt
```

### 아나콘다 환경이 아니면서 CUDA toolkit 이 없는 경우 

하단 링크로 접속해서 CUDA toolkit 을 설치해준다.  
https://developer.nvidia.com/cuda-10.1-download-archive-update2

### YOLOv4 모델을 사용하려는 경우 미리 학습된 가중치 파일을 다운 받는다.

하단 링크에 가서 가중치를 다운 받고 data 폴더 안에 넣어준다. 
https://drive.google.com/open?id=1cewMfusmPjYWbrnuJRuKhPMwRe_b9PaT


_____

## 실행법 

하단 커맨드를 입력한다. 
```bash
# Convert darknet weights to tensorflow model
python save_model.py --model yolov4 

# Run yolov4 deep sort object tracker on video
python object_tracker.py --video ./data/video/test.mp4 --output ./outputs/demo.avi --model yolov4
```


### References  

   Huge shoutout goes to hunglc007 and nwojke for creating the backbones of this repository:
  * [tensorflow-yolov4-tflite](https://github.com/hunglc007/tensorflow-yolov4-tflite)
  * [Deep SORT Repository](https://github.com/nwojke/deep_sort)











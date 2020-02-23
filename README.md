# YOLO v3 설치하기
***

* OpenCV 4.1 설치하기 (설치했다면 패스)
```
$ git clone https://github.com/jetsonworld/buildOpneCV.git
$ ./buildOpenCV.sh |& tee openCV_build.log
$ make -j4
```

* 젯슨 나노의 cuda 버젼 체크하기
```
$ cd /usr/local/
$ ls
```

* 기본으로 설치되어있는 CUDA Path를 export하기
```
$ export PATH=/usr/local/cuda-10.0/bin${PATH:+:${PATH}}
$ export LD_LIBRARY_PATH=/usr/local/cuda-10.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
```

* darknet 프로젝트 YOLO를 다운로드하기
```
$ git clone https://github.com/AlexeyAB/darknet

cd darknet
wget https://pjreddie.com/media/files/yolov3.weights
wget https://pjreddie.com/media/files/yolov3-tiny.weights
```

* build를 위한 Makefile 설정하기
```
$ sudo vi Makefile
-------
GPU=1
CUDNN=1
OPENCV=1
-------
```

* Darknet YOLO build하기
```
$ make
```


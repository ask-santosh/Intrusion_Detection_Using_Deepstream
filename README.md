# Crowd_count


Link for model file, cfg file, video file and engine file. 
https://drive.google.com/drive/folders/1hlrkKUmIeX647U8_2RR2Igy4J2VzePC7?usp=sharing

## Approach and Logic
Model : Yolov8s 
Tracking Algo: NVDCF
Env : Deepstream 6.2 / Ubuntu-20.04

1. The complete pipeline is built above deepstream python SDK bindings. This pipeline can handle multiple streams , for now it is configured for 3 streams. 
2. Every stream has it's own ROI so user can change this ROI according to the video feed.
3. This pipeline is restricted for only single class detection i.e person .
4. If any person is detected inside the given ROI then alert will be triggered .
5. The generated triggered is based on the tracking id and this tracking id is stored on respective lists.
6. Alerts are stored in a JSON file with all the details like : Tracking id , Date, Time, Stream/Message

## Run Program
Download all the files and place it inside the project folder and run :
python3 [deepstream_main_file.py] [file:/your-file-name-1] [file:/your-file-name-2] [file:/your-file-name-3]

Note: Requirements like DS-6.2 is installed with CUDA/CUdNN & Python bindings .

open cmd and switch to the directory where you have cloned the repository

run these commands to first create and then activate the environment

**Tensorflow CPU**

	conda env create -f conda-cpu.yml
	conda activate yolov4-cpu

**Tensorflow GPU (if GPU is available)**

	conda env create -f conda-gpu.yml
	conda activate yolov4-gpu

**download the weight file from the link below and place it in the data folder**
	
	https://drive.google.com/drive/folders/1_v74x1yE0-fKxy-NUFrE1TYrZv9ojy9y?usp=sharing

The following commands will allow you to run your custom yolov4 model. (video and webcam commands work as well)

#custom yolov4
	
	python save_model.py --weights ./data/custom.weights --output ./checkpoints/custom-416 --input_size 416 --model yolov4 

#Run custom yolov4 tensorflow model
	
	python detect.py --weights ./checkpoints/custom-416 --size 416 --model yolov4 --images ./data/images/car.jpg

**Install tesseract OCR**
In order to run tesseract OCR you must first download the binary files and set them up on your local machine. Please do so before proceeding or commands will not run as 	expected

	https://github.com/UB-Mannheim/tesseract/wiki


**Running License Plate Recognition on Images**

	python detect.py --weights ./checkpoints/custom-416 --size 416 --model yolov4 --images ./data/images/car2.jpg --plate


**Running License Plate Recognition on Video**

	python detect_video.py --weights ./checkpoints/custom-416 --size 416 --model yolov4 --video ./data/video/license_plate.mp4 --output ./detections/recognition.avi --crop


**Running License Plate Recognition on Camera**
	
	python detect_video.py --weights ./checkpoints/custom-416 --size 416 --model yolov4 --video 0 --output ./detections/recognition.avi --crop

(0 is for default camera, change it to 1 if using external camera)


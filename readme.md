Guitar Chord Detector
 Add short description of project here > 
 This is a model using imagenet that gets input from a webcam and detects what guitar chord is being played. It can detect Am, C, Dm, Em, F, and G.


## The Algorithm

This model uses ImageNet and determines what is being played by processing the finger positions on the fretboard. It uses the NVIDIA Jetson Nano. To train the model, I used a database from user raiwal.

## Running this project

1. Make a folder in /home/nvidia/jetson-inference/python/training/classification/models called guitar
2. Download the model and place it in the new folder
3. Download the all_guitar_data folder and place it in /home/nvidia/jetson-inference/python/training/classification/data/
4. Place the file that you want to process in the test folder at /home/nvidia/jetson-inference/python/training/classification/data/test
6. Open the terminal and go to the classification directory by running the following command: cd python/training/classification/
7. Run these two commands: NET=models/guitar and DATASET=data/all_guitar_data
8. Run the following command: imagenet.py --model=$NET/resnet18g.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/placeholder1/placeholder2.jpg placeholder3.jpg where placeholder1 is the sub folder within test where your input file is, placeholder2 is the name of your input file, and placeholder3 is the desired name of the output file
9. Copy the output into the test folder by running the following command: cp placeholder3.jpg data/all_guitar_data where placeholder3 is your output

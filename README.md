# **MagikMoments**

Finds the "magic" and the most happy moments of a given movie and makes a trailer out of it.


## Requirements :

### To run locally :
1. A CPU which supports AVX instruction set. Starting with TensorFlow 1.6, binaries use AVX instructions which may not run on older CPUs.The processors with AVX instructions are listed in this 
[Wikipedia link](https://en.wikipedia.org/wiki/Advanced_Vector_Extensions#CPUs_with_AVX).
2. A working Python 3.6 environment along with pip installed. 
3. External modules installed. Instructions below :
    * To install the external modules, open CMD/Terminal and navigate inside the MagikMoments directory.
    Then run :
    * On windows :
        ```bash
        pip install -r requirements.txt
        ```
    
    * On Linux :
        ```bash
        pip3 install -r requirements.txt 
        ```

 4. The learned weights when the classifier was run can be found [here](https://drive.google.com/open?id=1-aZlFq9g5dHLGIu-ZjtvzjtVb60M0mB7).
 The entire model (architecture, layers, and weights) can be found [here](https://drive.google.com/open?id=1-Kovmt0wQDeyfYEPW5pIPZ2GyPezW7rv).
 5. To execute it, open CMD/Terminal, navigate inside `MagikMoments/src/` directory and run :
    * On Windows :
        ```bash
        python classifier.py
        ``` 
    * On Linux :
        ```bash
        python3 classifier.py
        ```

### Running on Google Colaboratory :
Navigate to this [Google Colaboratory Link](https://colab.research.google.com/drive/1_-WocNc11cWxlrMmnCRN8jeWxVb5wCc-), copy the jupyter notebook to your drive and run it.

## Running The Test

Pre-requisites:
- An image with visible human(s).
- A sample video to test.


## Working (Internal):

1. Specify the video file to be used.
2. The video file will be sent to `create_frames` method which is a generator function yielding frames.
3. The frame from `create_frames` will be passed to `detect_face` method which will check for faces and display if any found.
4. The faces from `detect_face` will be passed to `check_emotion` method which will check if the face is happy and store timestamp.
5. The method `cut_moments` will be called, which will cut 5-sec clips will be cut for each moment (2.5 before, 2.5 after) and store clips objects into a array.
6. That array will be passed to `combine_clips`, which will combine all those clips into a final video.

## Contribution 

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Author

- [Supragya Raj](https://github.com/supragya)

## List of Contributors
- [Kogam22](https://github.com/Kogam22)
- [masterchef2209](https://github.com/masterchef2209)
- [aayush1205](https://github.com/aayush1205)
- [DeboDevelop](https://github.com/DeboDevelop)

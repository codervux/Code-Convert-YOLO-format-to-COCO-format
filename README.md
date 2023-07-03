# Yolo-to-COCO-format-converter

When you use **Yolo-model**, you might create annotation labels with [Yolo-mark](https://github.com/AlexeyAB/Yolo_mark).  
For example,  
- `obj.names` - example of list with object names  
- `train.txt` - example with list of image filenames for training Yolo model  
- `train/` - example of folder that contain images and labels
> - *.jpg : example of list of image  
> - *.txt : example of list of label  

**But, when you want to use another model(ex. efficientdet), you need another annotation format! :disappointed_relieved:**  
### This code will help you make a COCO format annotations with Yolo format!  

### Updates  
- Oct 13th, 2021 - We could support not only **`Yolo-mark`** outputs, but also **`OpenLabeling`** outputs!  
                Also, We could make segmentation mask polygons information in json file.  
                Thanks to [@NauchtanRobotics](https://github.com/NauchtanRobotics)!  
       

## How to use
### Requirements
- numpy
- OpenCV  

Install these lib:
- `pip install numpy`  
- `pip install opencv`  
- `pip install imagesize`


Then, Just clone this repository.  
- `git LINK_TO_THIS_REPO`  
- `cd Yolo-to-COCO-format-converter`  

### It will be easy to understand if you refer to the tutorial folder.  

When you have your own Yolo annotation format, just change a little bit!  
### 1. Change `classes` with your own dataset.  
In `main.py`, there is a code that declare the classes. You will change this with your `obj.names`.  
Mean that: 
1. Change classes in obj.names
2. Change classes in main.py

<p align="center"><img src="https://user-images.githubusercontent.com/41863759/100314803-cfd36800-2ffa-11eb-90ed-bf821ba2de4f.png" width="400px"></p>  

Next, merge folder image and annotation of YOLO into 1 folder (in YOLO format, each image has one .txt annotation file).

### 2. Prepare COCO annotation file from multiple YOLO annotation files.
Use this approach if your training data file structure looks like this:
<pre>
    directory/
        Photo_00001.jpg
        Photo_00001.txt
        Photo_00002.jpg
        Photo_00002.txt
</pre>

then run in terminal 

- `python main.py --path <Absolute path to dataset_root_dir> --output <Name of the json file>`  
- (For example)`python main.py --path /home/taeyoungkim/Desktop/Yolo-to-COCO-format-converter/tutorial/ --output train_coco`  



## License
```
Copyright (c) 2021 Tae Young Kim

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

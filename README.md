# OIDv4 To VOC XML format

If you have experience in working with Pascal VOC format but not able to work with [Open Image Dataset v4](https://storage.googleapis.com/openimages/web/index.html) that has [600](https://storage.googleapis.com/openimages/2018_04/bbox_labels_600_hierarchy_visualizer/circle.html) classes. Than there are steps how you can download images per class and convert annotation to XML files.

The Code is documented and easy to understand. Please see the Usage steps down.

# Open Image Dataset v4

All the information related to this huge dataset can be found [here](https://storage.googleapis.com/openimages/web/index.html)
In these few lines are simply summarized some statistics and important tips.

<table>
    <tr><td></td><td><b>Train<b></td><td><b>Validation<b></td><td><b>Test<b></td><td><b>#Classes<b></td></tr>
    <tr><td>Images</td><td>1,743,042</td><td>41,620	</td><td>125,436</td><td>-</td></tr>
    <tr><td>Boxes</td><td>14,610,229</td><td>204,621</td><td>625,282</td><td>600</td></tr>
</table>

# Getting Started

## Installation

Python3 is required.

1. Clone this repository. 
```bash
   git clone https://github.com/EscVM/OIDv4_ToolKit.git
```
2. Install the required package.
```bash
   pip3 install -r requirements.txt
```
Peek inside the requirements file if you have everything already installed. Most of the dependencies are common libraries.

## Launch the ToolKit to check the available options
First of all, if you simply want a quick reminder of al the possible options given by the script, you can simply launch, from your console of choice, the [main.py](main.py). Remember to point always at the main directory of the project
   ```bash
   python3 main.py
   ```
or in the following way to get more information
   ```bash
   python3 main.py -h
   ```

## Download the Dataset

To download the Dataset per class goto this repository [https://github.com/EscVM/OIDv4_ToolKit](https://github.com/EscVM/OIDv4_ToolKit)

Read [README.MD](https://github.com/EscVM/OIDv4_ToolKit/blob/master/README.md) file to download some classes.

## Make Annotation into XML format.

To Convert a class say 'Apple' give source path of Images containing Images and Labels Folder. 

└───Apple

        |0fdea8a716155a8e.jpg
        |2fe4f21e409f0a56.jpg
        |...
        └───Labels
                |0fdea8a716155a8e.txt
                |2fe4f21e409f0a56.txt
                |...

And give destination path to store converted xml files. 

```bash
python3 OIDv4_to_VOC.py --sourcepath Dataset/train/Apple --dest_path Dataset/train/Annotation/Apple
```


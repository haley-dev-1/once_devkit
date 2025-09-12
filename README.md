# ONCE dataset conversion

## Documentation for dataset
https://once-for-auto-driving.github.io/  
*Note* You can download the datasets through Download/  
Download train and val, not test (irrelevant)

## In the repo

- once_og.py is the same as once.py but with a few changes/debug statements
- THE DIRECTORIES ARE MISSING!! But I do tell you how to get them back. These are crucial for running, of course.

## Running right out of the box!
- open and activate a condas environment 
```bash
    conda create once
    conda activate once
```
- run once_og.py
```python
python3 once_og.py
```
*There shouldn't be any issues (IF YOU SET THE DIRECTORIES CORRECTLY) but, uhh, if so.... welp!*

# File structure
I couldn't figure out how to commit the file structure without the massive amounts of image data (I tried .gitignore -- sorry if that causes issues), but the directories *did* need changing in order to work

It should look like this (ignoring top level, which the repo already has as is)

once_devkit/  
once/data/  
 000027/  
 ├── cam03/  
 ├── lidar_roof/  
 └── 000027.json  


 Each frame e.g. '000027' should have camera03 data (you'll find all these annotations in each frames .json files)

# Which camera?
We use **cam03** because that is the middlemost camera in the ONCE data! There are other cameras, but we ignore them for now.


# Next steps for you
Need:
1. LiDAR image (numpy format preferred)
2. 2D Bounding Box annotations **converted to YOLO Format**
3. RGB Image 

Need to **convert from ONCE formatting to YOLO formatting** (2D bounding boxes only, within each JSON For each frame for each sequence)

Project the LiDAR Images onto the RGB images!



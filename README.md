<div align="center">

# A Generalized Framework for Recognition of Expiration Dates on Product Packages Using Fully Convolutional Networks

[**Ahmet Cagatay Seker**](https://acseker.github.io/acseker/)<sup>1,2</sup>&nbsp;·&nbsp;
[**Sang Chul Ahn**](https://sites.google.com/view/asckist)<sup>1,2,&#9993;</sup>

<sup>&#9993;</sup> Corresponding Author &emsp;

<div style="display: flex; justify-content: center; flex-wrap: wrap; gap: 2em; text-align: center;">
  <div style="min-width: 150px;">
    <span><sup>1</sup> University of Science and Technology</span><br>
    <a href="https://www.ust.ac.kr/eng/">
      <img src="./static/assets/ust.svg" height="50"
           alt="UST Logo">
    </a>
  </div>
  
  <div style="min-width: 150px;">
    <span><sup>2</sup> Korea Institute of Science and Technology </span><br>
    <a href="https://www.kist.re.kr/eng/index.do">
      <img src="./static/assets/kist.svg" height="50"
           alt="KIST Logo">
    </a>
  </div>
</div>
  
<br>

[![Elsevier ESWA](https://img.shields.io/badge/-ESWA-FF6C00?style=flat&logo=elsevier&logoColor=FF6C00&labelColor=white)](https://doi.org/10.1016/j.eswa.2022.117310)
[![Project Page](https://img.shields.io/badge/%F0%9F%8C%90-Project%20Page-blue?style=flat)](https://felizang.github.io/expdate/)
[![Executables](https://img.shields.io/badge/%E2%9A%99%EF%B8%8F-Executables-green)](https://drive.google.com/drive/folders/15bEaQMYmjgJ7LHl2bS-fkKM6mw0iwq1S?usp=sharing)
[![Dataset](https://img.shields.io/badge/-Dataset-red?style=flat&logo=googledrive&logoColor=white&labelColor=555)](https://drive.google.com/drive/folders/1YuxWzVj6bT6gs6XlewEGetYrdgwZt7EH)

</div>



## Overview

We provide standalone executable files for testing the date detection and recognition framework separately without configuring the source code or training the models.

The framework is divided into two executable files:

- `run_detection.exe`: Detects date regions in product images.
- `run_recognition.exe`: Identifies the day, month, and year components and understands the expiration dates.

A separate executable, `run_webcam.exe`, is also provided for real-time expiration-date detection and recognition using a webcam.



## Testing with Images

### Step 1: Prepare the Input Images

Create a folder named `images_det` and place your test images inside it.

### Step 2: Organize the Files

Place the `images_det` folder and all executable files in the same directory:

```text
executable_directory/
├── images_det/
│   ├── image_1.jpg
│   ├── image_2.jpg
│   └── ...
├── run_detection.exe
├── run_recognition.exe
└── run_webcam.exe
```

### Step 3: Detect Date Regions

Open a terminal in the executable directory and run the detection executable:

```bash
# Windows
cd path/to/executable_directory
run_detection.exe

# Ubuntu
cd path/to/executable_directory
./run_detection
```

After execution, the following folders are created in the same directory:

- `results_det`: Contains visualizations of the detected date regions.
- `images_rec`: Contains the cropped regions of detected dates used as inputs for the `run_recognition.exe`.

The `images_rec` folder also contains a `cropped_img_list.json` file that associates each input image with its detected and cropped date regions.


### Step 4: Recognize and Interpret the Dates

Run the recognition executable:

```bash
# Windows
cd path/to/executable_directory
run_recognition.exe

# Ubuntu
cd path/to/executable_directory
./run_recognition
```

After execution, a folder named `results_rec` is created in the same directory. It contains:

- Detection results for the day, month, and year components
- Recognized expiration dates
- Text files containing the interpreted date information

> **Note:** If you would like to run `run_recognition.exe` independent from the results of `run_detection.exe`, place your date-region images directly in the `images_rec` folder and remove `cropped_img_list.json` before execution.



## Testing with a Webcam

We also provide a standalone executable for testing the complete pipeline using webcam video frames as input. The executable:

- Detects expiration-date regions
- Interprets the detected expiration dates
- Displays the interpreted results directly on the product package in the live webcam feed

Ensure that a webcam is connected and accessible. Then, open a terminal in the executable directory and run:

```bash
# Windows
cd path/to/executable_directory
run_webcam.exe

# Ubuntu
cd path/to/executable_directory
./run_webcam
```



## Citation
If you find this work useful in your research, please consider citing:
```bibtex
@article{seker2022generalized,
  title     = {A generalized framework for recognition of expiration dates on product packages using fully convolutional networks},
  author    = {Seker, Ahmet Cagatay and Ahn, Sang Chul},
  journal   = {Expert Systems with Applications},
  volume    = {203},
  pages     = {117310},
  year      = {2022},
  publisher = {Elsevier},
}
```


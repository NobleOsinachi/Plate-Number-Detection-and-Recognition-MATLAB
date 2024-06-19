# License Plate Number Detection and Recognition

This MATLAB script is designed to detect and recognize license plate numbers from a given image. It leverages image processing techniques to identify and process the license plate characters, comparing them against a predefined set of characters for recognition.

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Explanation of the Script](#explanation-of-the-script)
- [License](#license)

## Features

- Detects and extracts the license plate from an image.
- Recognizes and outputs the license plate number.
- Utilizes edge detection and morphological operations.
- Compares detected characters with predefined character images for recognition.

## Requirements

- MATLAB
- Image Processing Toolbox

## Installation

1. Download and install MATLAB from [MathWorks](https://www.mathworks.com/products/matlab.html).
2. Ensure the Image Processing Toolbox is installed.
3. Download the script and the character image files (`0.bmp`, `1.bmp`, ..., `Z.bmp`).

## Usage

1. Place the character image files in the same directory as the script.
2. Run the script in MATLAB.
3. Select an image file when prompted.

```matlab
[path, file] = uigetfile('*.jpg', 'Select Image');
```

## Explanation of the Script

### Step-by-Step Breakdown

1. **Image Selection and Display**

   - The script starts by prompting the user to select a `.jpg` image file.
   - The selected image is displayed.

2. **Grayscale Conversion and Edge Detection**

   - The image is converted to grayscale.
   - Horizontal and vertical edges are detected using the Sobel operator.

3. **Morphological Operations**

   - Small objects are removed.
   - The image is dilated and filled to enhance features.
   - The processed image is thinned and eroded to isolate the license plate characters.

4. **Character Segmentation**

   - The image is multiplied with the processed mask to highlight the characters.
   - The script calculates vertical and horizontal profiles to find the bounding box of the license plate.
   - The license plate region is extracted and displayed.

5. **Character Recognition**

   - The script loads predefined character images (`0.bmp`, `1.bmp`, ..., `Z.bmp`).
   - Each character in the detected license plate is compared with the predefined characters using image difference.
   - The recognized characters are concatenated to form the license plate number.

6. **Output**
   - The recognized license plate number is displayed in a message box.

```matlab
msgbox(strcat('Vehicle Registration Number: ', out));
```

## License

This script is released under the MIT License. You are free to use, modify, and distribute it as per the terms of the license.

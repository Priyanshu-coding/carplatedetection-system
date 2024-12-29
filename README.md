 Image Processing Project
Overview
This project is focused on image processing using Python, leveraging libraries such as OpenCV, Pytesseract, and Pillow. The primary goal is to load images, display them, and perform Optical Character Recognition (OCR) to extract text.
Features
Load and display images.
Extract text from images using OCR.
Support for various image formats.
Requirements
Ensure the following libraries are installed:
OpenCV: For image manipulation.
Pytesseract: For OCR functionality.
Pillow: For image handling.
NumPy: For numerical operations.
Matplotlib: For displaying images.
You can install these dependencies via pip:
bash
pip install opencv-python pytesseract Pillow numpy matplotlib
Setup Instructions
Mount Google Drive (if using Google Colab):
python
from google.colab import drive
drive.mount('/content/drive')
Specify Image Path:
Define the path to your image:
python
image_path = "/content/drive/MyDrive/your_image.jpg"
Import Required Libraries:
Include the necessary libraries in your script:
python
import cv2
import pytesseract
from PIL import Image
import numpy as np
import matplotlib.pyplot as plt
Load and Display the Image:
Create a function to load and visualize the image:
python
def load_image(image_path):
    image = cv2.imread(image_path)
    if image is None:
        print("Error: Image not found. Check the file path.")
        return None
    image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
    plt.imshow(image)
    plt.axis("off")
    plt.title("Input Image")
    plt.show()
    return image

# Load the image
image = load_image(image_path)

if image is None:
    raise FileNotFoundError("Image could not be loaded. Verify the image path.")
Perform OCR:
Configure Pytesseract and extract text from the loaded image:
python
pytesseract.pytesseract.tesseract_cmd = "/usr/bin/tesseract"  # Path to Tesseract executable

# Perform OCR on the image
extracted_text = pytesseract.image_to_string(image)
print("Extracted Text:", extracted_text)
Usage Instructions
Upload your images to Google Drive or specify a local path.
Modify the image_path variable to point to your specific image file.
Execute the script in a Python environment (Google Colab recommended) to see the output.
Contributing
Contributions are welcome! Please fork this repository and submit a pull request for any enhancements or bug fixes.
License
This project is licensed under the MIT License - see the LICENSE file for details. This README provides a detailed guide for users to set up and utilize this image processing project effectively. Adjust paths and filenames as necessary based on your specific setup and requirements.

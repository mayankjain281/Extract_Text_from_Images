### How to Extract Text from Images with Python?

OCR (Optical Character Recognition) is the process of electronical conversion of Digital images into machine-encoded text. Where the digital image is generally an image that contains regions that resemble characters of a language. OCR is a field of research in pattern recognition, artificial intelligence and computer vision. This is due to the fact that newer OCR’s are trained by providing them sample data which is ran over a machine learning algorithm. This technique of extracting text from images is generally carried out in work environments where it is certain that the image would be containing text data. In this article, we would learn about extracting text from images. We would be utilizing python programming language for doing so. 

Firstly we imported the Image module from PIL library (for opening an image) and then pytesseract module from pytesseract library(for text extraction). Then after we defined the path_to_tesseract variable which contains the path to the executable binary (tesseract.exe) that we installed in the prerequisite (this path would depend on the location where the binary is installed). Then we defined the image_path variable which contains the path to the image file. This path is passed to the open() function to create an image object out of our image. After this, we assigned the pytesseract.tesseract_cmd variable the path stored in path_to_tesseract variable (this would be used by the library to find the executable and use it for extraction). After which we passed the image object (img) to image_to_string() function. This function takes in argument an image object and returns the text recognized inside it. In the end, we displayed the text which was found in the image using text[:-1] (due to a additional character (^L) that gets appended by default).


### Example:

from PIL import Image 
from pytesseract import pytesseract 
  
path_to_tesseract = r"C:\Program Files\Tesseract-OCR\tesseract.exe"
image_path = r"csv\sample_text.png"
img = Image.open(image_path) 
pytesseract.tesseract_cmd = path_to_tesseract 
text = pytesseract.image_to_string(img) 
print(text[:-1])

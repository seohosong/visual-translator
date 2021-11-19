# Image Translator

This repository includes codes and details for the project "Visual (Image) Translator" at YBIGTA, Yonsei University in South Korea. The system automatically detect and translate any texts in given image. Those translated texts are used to reconstruct images to be placed on the original location with similar style with background. (Pipeline : OCR - Translation - Reconstruction)

## OCR

The system detects any texts in given image with Google Cloud's OCR service and return them as plain texts to be translated after.

## Translation

The detected texts are translated with Google Cloud's Translation service to target language. The input langugae is automatically detected by the service.

## Reconstruction

The translated texts are then used to reconstruct an image to replace the original location of text patches. For simplicity, we stored each English alphabet as an image file and used it to reconstruct the default image for the replacement. To define the color of text and background, we employed K-means clustering algorithm to extract two colors for each. We set K=2 and checked which centroid has more similar pixel in color. We defined the centroid with more similar pixels has a RGB value of the background and the other has the color of texts for reconstruction. On resconstructed default image, we resized and applied text and background colors and rotated it to fit the original location of the patch. 


## Example images

The example images used in our project are in inputs and outputs folder in this repository.


## Links

You can download standard character images used in this project from below.
<https://drive.google.com/file/d/1BOJyJN_qBPH_iAdUIqZJF6ymIJSXpPk3/view?usp=sharing>

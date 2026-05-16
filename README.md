# Part 2: Computer Vision Problem Formulation and CNN Prototype

## Task 1: Problem Identification
This dataset represents an **Image Classification** problem. The goal is to take a single image of a product surface and classify the entire image into one of four distinct categories: `normal`, `scratch`, `dent`, or `stain`. We are not trying to draw bounding boxes around the defects (Object Detection) or highlight specific defective pixels (Segmentation); we just want a single label for the whole image.

## Project Structure
- `notebook.ipynb`: Contains dataset exploration, CNN model building, training, and evaluation.
- `requirements.txt`: Dependencies to run the code.
- `results/`: Contains accuracy/loss curves and the confusion matrix.
- `sample_predictions/`: Visual outputs of the model's predictions on test images.

## Task 6: CNN Concept Explanation
* **What is convolution?** Think of convolution like scanning an image with a tiny magnifying glass. It slides across the image, looking for specific visual patterns like straight edges, curves, or specific color patches.
* **Why is pooling used?** Pooling essentially shrinks the image down, keeping only the most important features. It helps reduce the computational power needed and ensures the model learns the "idea" of a pattern rather than memorizing its exact pixel location.
* **Why is ReLU commonly used in CNNs?** ReLU (Rectified Linear Unit) simply changes any negative numbers in the network to zero. It's used because it's computationally cheap and introduces non-linearity, allowing the model to learn complex patterns without breaking the math during training (avoiding the vanishing gradient problem).
* **Why are CNNs better than regular feed-forward networks for image data?** A regular feed-forward network flattens an image into a single 1D line of pixels right away, which completely destroys the spatial relationship between pixels (e.g., losing the shape of a circle). CNNs process the image in its 2D grid format, allowing them to actually understand shapes and textures.

## Task 7: Business Use Case Mapping
**Domain: Manufacturing**
This type of computer vision solution is perfectly suited for automated quality control on a manufacturing assembly line. Instead of having human inspectors manually look at every single product (which is slow and prone to fatigue), a camera can take a picture of the product as it moves down the conveyor belt. The CNN model can instantly classify the image as `normal` or flag it if it detects a `scratch`, `dent`, or `stain`, automatically routing defective products off the line for rework. This drastically improves inspection speed and consistency.

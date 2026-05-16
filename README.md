# Task 1: Problem Identification
## Selected Problem Type: Image Classification

### Explanation:
The dataset represents an image classification problem because the objective is to categorize an entire image into a single, discrete class label (normal, scratch, dent, or stain).

Unlike object detection, we are not predicting bounding boxes around specific defect coordinates.

Unlike semantic or instance segmentation, we are not classifying every individual pixel in the image to isolate the exact contours of the defects.
Instead, the presence of a feature determines a global property of the surface, making it a classic multi-class image classification task where each input image maps directly to one categorical output.

# Task 6: CNN Concept Explanation
## What is convolution?
Think of convolution as looking at an image through a small magnifying glass (called a filter or kernel) that slides across the picture row by row. This filter multiplies its own weights with the pixel values it currently covers, summing them up to create a new map. It allows the computer to highlight and extract local patterns like sharp edges, lines, and textures.

## Why is pooling used?
Pooling reduces the physical size (width and height) of the image maps while keeping the most critical visual data intact. For instance, Max Pooling takes only the brightest, highest pixel value in a small window. This shrinks the amount of calculation needed for the next layers and helps the model recognize shapes even if they shift slightly in position.

## Why is ReLU commonly used in CNNs?
ReLU (Rectified Linear Unit) converts negative numbers to zero and leaves positive numbers exactly as they are. This introduces "non-linearity" into the network without costing much computer math power. Without non-linearity, the entire model behaves like one giant simple linear formula, making it unable to learn complex patterns like scratches, curves, or stains.

## Why are CNNs better than regular feed-forward networks for image data?
Regular networks flatten images into a single long string of numbers, which completely breaks and forgets how pixels relate to their neighboring pixels vertically or horizontally. CNNs actively retain this 2D physical spatial structure. Additionally, CNNs use weight sharing (the same small filter is reused everywhere across the image), which drastically reduces the number of parameters and prevents the network from overfitting.

# Task 7: Business Use Case Mapping
## Domain Choice: Manufacturing

In modern manufacturing facilities, implementing an Automated Visual Quality Inspection pipeline using computer vision can yield significant returns.

The Problem: Manual inspection by human workers is prone to fatigue, subjective bias, and can limit line throughput speeds. Tiny micro-scratches or structural dents can easily escape notice over a 12-hour shift.

The Solution: By placing high-resolution industrial cameras above a conveyor belt, this exact image classification model can scan components in real-time as they pass by.

Operational Integration: * Items categorized as normal continue automatically down the assembly line to packaging.

Items flagged with scratch, dent, or stain trigger an automated physical sorting arm that ejects the item into a rework or scrap bin.

Data Intelligence: If the system suddenly counts a sudden spike in stain defects over an hour, it can instantly text/alert floor engineers to inspect a leaking lubricant valve upstream before thousands of products are ruined.

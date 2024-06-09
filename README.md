# Edge Detection and Gradient Image Generation

This C program performs edge detection and gradient image generation using pre-computed horizontal and vertical differential images. It implements edge detection by identifying points where the gradient magnitude exceeds a specified threshold, marking them as edges in the output image. The gradient image is computed from the horizontal and vertical differential images using a 3x3 or 5x5 filter.

## Description

The program consists of two main functions:

1. **computeGradient**: Computes the gradient image from the horizontal and vertical differential images. It calculates the magnitude of the gradient at each pixel using the Euclidean distance formula.

2. **detectEdges**: Detects edge points in the gradient image based on a specified threshold. If the magnitude of the gradient at a pixel exceeds the threshold, it is marked as an edge point with a bright intensity (200). Otherwise, it is set to zero.

The program also includes utility functions to load images from files and perform memory allocation and deallocation.

## Usage

1. **Compile the Program**: Compile the program using a C compiler such as GCC.
   
   Example:
   ```
   gcc edge_detection.c -o edge_detection -lm
   ```

2. **Run the Program**: Execute the compiled program.
   
   Example:
   ```
   ./edge_detection
   ```

3. **Input Images**: Ensure that the input horizontal and vertical differential images are provided in raw format. Adjust the file paths in the code accordingly.

4. **Output Images**: The program generates gradient images and edge images for both 3x3 and 5x5 filters. The output images are saved as raw files.

## Sources and Dependencies

- **MTCNN for Face Detection**: Uses pre-trained models from the Facenet PyTorch repository.
- **OpenCV for Image Processing**: Utilizes OpenCV library for image loading and manipulation.
- **Scikit-learn for Cosine Similarity Calculation**: Depends on Scikit-learn library for cosine similarity calculations.

## Notes

- Overflow and underflow are handled by normalizing the filtered results into the range of a byte.
- Threshold values for edge detection can be adjusted manually through trial-and-error to achieve desired edge results.

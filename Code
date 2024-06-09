#include <stdio.h>
#include <stdlib.h>
#include <math.h>
void computeGradient(unsigned char *horizontal, unsigned char *vertical, unsigned
char *gradient, int width, int height) {
for (int i = 0; i < height; ++i) {
for (int j = 0; j < width; ++j) {
int horizontalValue = horizontal[i * width + j];
int verticalValue = vertical[i * width + j];
int magnitude = (int)sqrt(horizontalValue * horizontalValue +
verticalValue * verticalValue);
gradient[i * width + j] = (unsigned char)magnitude;
}
}
}
void detectEdges(unsigned char *gradient, unsigned char *edge, int width, int
height, unsigned char threshold) {
for (int i = 0; i < height; ++i) {
for (int j = 0; j < width; ++j) {
if (gradient[i * width + j] >= threshold) {
edge[i * width + j] = 200;
} else {
edge[i * width + j] = 0;
}
}
}
}
unsigned char *loadImage(const char *filename, int width, int height) {
FILE *file = fopen(filename, "rb");
if (!file) {
printf("Error opening file %s\n", filename);
return NULL;
}
unsigned char *image = (unsigned char *)malloc(width * height * sizeof(unsigned
char));
fread(image, sizeof(unsigned char), width * height, file);
fclose(file);
return image;
}
void main() {
int width = 512;
int height = 512;
unsigned char *horizontal3x3 =
loadImage("/Users/shubvats/Desktop/MULTIMEDIA/barbara_grayoutputImage3x3Horizontal.
raw", width, height);
unsigned char *vertical3x3 =
loadImage("/Users/shubvats/Desktop/MULTIMEDIA/barbara_grayoutputImage3x3Vertical.ra
w", width, height);
unsigned char *horizontal5x5 =
loadImage("/Users/shubvats/Desktop/MULTIMEDIA/barbara_grayoutputImage5x5Horizontal.
raw", width, height);
unsigned char *vertical5x5 =
loadImage("/Users/shubvats/Desktop/MULTIMEDIA/barbara_grayoutputImage5x5Vertical.ra
w", width, height);
unsigned char *gradientImage = (unsigned char *)malloc(width * height *
sizeof(unsigned char));
unsigned char *edgeImage = (unsigned char *)malloc(width * height *
sizeof(unsigned char));
computeGradient(horizontal3x3, vertical3x3, gradientImage, width, height);
unsigned char threshold3x3 = 50;
detectEdges(gradientImage, edgeImage, width, height, threshold3x3);
FILE *gradientFile3x3 =
fopen("/Users/shubvats/Desktop/MULTIMEDIA/barbara_grayoutputImagegradient_image_3x3
.raw", "wb");
fwrite(gradientImage, sizeof(unsigned char), width * height, gradientFile3x3);
fclose(gradientFile3x3);
FILE *edgeFile3x3 =
fopen("/Users/shubvats/Desktop/MULTIMEDIA/barbara_grayoutputImageedge_image_3x3.raw
", "wb");
fwrite(edgeImage, sizeof(unsigned char), width * height, edgeFile3x3);
fclose(edgeFile3x3);
computeGradient(horizontal5x5, vertical5x5, gradientImage, width, height);
unsigned char threshold5x5 = 100;
detectEdges(gradientImage, edgeImage, width, height, threshold5x5);
FILE *gradientFile5x5 =
fopen("/Users/shubvats/Desktop/MULTIMEDIA/barbara_grayoutputImagegradient_image_5x5
.raw", "wb");
fwrite(gradientImage, sizeof(unsigned char), width * height, gradientFile5x5);
fclose(gradientFile5x5);
FILE *edgeFile5x5 =
fopen("/Users/shubhamvats/Desktop/MULTIMEDIA/barbara_grayoutputImageedge_image_5x5.
raw", "wb");
fwrite(edgeImage, sizeof(unsigned char), width * height, edgeFile5x5);
fclose(edgeFile5x5);
free(gradientImage);
free(edgeImage);
free(horizontal3x3);
free(vertical3x3);
free(horizontal5x5);
free(vertical5x5);
}

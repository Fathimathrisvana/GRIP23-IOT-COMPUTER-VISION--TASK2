# GRIP23-IOT-COMPUTER-VISION--TASK2
color quantization through K-Means clustering, identifies the most dominant colors in an image, visualizes them using Matplotlib, and overlays the visualization on the original image for easy interpretation.
Importing Libraries:

The necessary libraries are imported: cv2 for image processing, numpy for numerical operations, matplotlib.pyplot for visualization, KMeans from sklearn.cluster for color clustering, and imutils for image resizing.
Setting the Number of Clusters:

The variable clusters is set to 5, indicating that the code will identify the top 5 dominant colors in the image.
Loading and Preprocessing the Image:

The image specified by the file path (9.jpeg) is loaded using OpenCV (cv2.imread).
A copy of the original image (org_img) is created to be used later.
The image is resized to have a height of 200 pixels using the imutils.resize function. This resizing is performed to make the image more manageable for processing.
Performing K-Means Clustering:

The pixel values of the resized image are flattened into a 2D array (flat_img) where each row represents a pixel, and each column represents a color channel (Red, Green, Blue - RGB).
K-Means clustering is applied to the flattened image (flat_img) using the KMeans function from Scikit-learn. It is configured to create clusters (5 in this case) clusters and uses a random seed (random_state) for reproducibility.
The centroids of these clusters, representing dominant colors, are stored in the dominant_colors variable.
Calculating Color Percentages:

The percentage of each dominant color in the image is calculated based on the number of pixels assigned to each cluster.
This is achieved by counting the number of pixels assigned to each cluster label and dividing it by the total number of pixels in the image.
The results are stored in the percentages array
Sorting Dominant Colors by Percentage:

The script pairs each dominant color with its corresponding percentage and stores these pairs in a list.
This list is sorted in descending order based on color percentage. This ensures that the most dominant colors come first in the list.
Creating Color Blocks for Visualization:

A white block (block) with dimensions 50x50 pixels is created. This block will be filled with color for visualization.
A Matplotlib figure is initialized for displaying dominant colors.
Displaying Dominant Colors:

For each dominant color:
A subplot is created within the Matplotlib figure.
The white block is filled with the dominant color.
X and Y ticks (axis labels) are disabled to keep the visualization clean.
The color's percentage is displayed as a label below the block.
Creating a Horizontal Bar for Color Visualization:

A white horizontal bar (bar) is created with dimensions 50x500 pixels. This bar will be used to visualize the dominant colors proportionally.
Each segment of the bar represents a dominant color, and the length of each segment corresponds to its percentage of the image.
Resizing the Original Image:

The original image (org_img) is resized to a new size, maintaining the aspect ratio. The new dimensions are determined by a specified height (2000 pixels in this case). This resized image is suitable for final visualization.
Overlaying Text on the Resized Image:

A copy of the original image (copy) is created.
A white rectangle with text is overlaid on the copied image. This rectangle serves as a title for the visualization.
Overlaying Dominant Colors and Labels:
Overlaying Dominant Colors and Labels:

The top five dominant colors are overlaid on the image.
Each color is placed in a horizontal row.
Labels and rank numbers are added to each color block to identify them.
Displaying the Result:

The Matplotlib figure displaying the dominant colors is shown using plt.show(). This figure provides a visual representation of the dominant colors and their percentages.
An OpenCV window is opened to display the final image (final) with overlaid dominant colors, labels, and title.
Saving the Final Image:

The final image (final) is saved as output.png using cv2.imwrite. This saved image includes all the visualizations and overlays.

The top five dominant colors are overlaid on the image.
Each color is placed in a horizontal row.
Labels and rank numbers are added to each color block to identify them.


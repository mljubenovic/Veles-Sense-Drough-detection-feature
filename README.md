# Veles-Sense-Drough-detection-feature
This project loads thermal maps captured by a thermal camera on a drone and creates zones/areas under water stress.
Thermal ROI Clustering with GMM

This script loads a thermal GeoTIFF, lets the user draw a polygon ROI, and applies a Gaussian Mixture Model (GMM) to cluster pixel values. The result is displayed as a colorized thermal map.

# Features

Load single-band thermal .TIF using rasterio
Draw a free-shape ROI with the mouse
Cluster ROI pixels using GaussianMixture (scikit-learn)
Visualize results with a thermal-style color map (OpenCV + matplotlib)
Works on large rasters by downsampling for interaction

# Requirements
python 3.9+
opencv-python
numpy
scikit-learn
matplotlib
rasterio

# Install:
pip install opencv-python numpy scikit-learn matplotlib rasterio

# How to Run
Set your image_path in the script.
Run:
python script_name.py
Click to draw ROI → double-click to finish
The clustered result appears in a matplotlib window.

# Key Config (top of script)
image_path = "path/to/image.TIF"
resize_factor = 0.25
k = 4  # GMM components

# Output
ROI pixels are clustered and colorized (blue/orange/red/white by default)
Displayed via matplotlib
Add plt.savefig() or rasterio export if needed

# Notes
Requires at least 3 clicks to form ROI
Colors are assigned by cluster label, not temperature order
rasterio must be installed with GDAL support


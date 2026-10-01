# KAGGLE---Biohub-Cell-Tracking
Repository for my submission to the Kaggle Biohub Cell Tracking Competition. 

My strategy was similar to other projects in this competition:
I implemented a 3D U-Net model with skip connections from the encoder to decoder to help with segmentation. Each convolutional block utilized batch normalization and RELU. Each frame in the volumes were treated independely and normalized based on image intensity. As each image was read, the anisotropic factor of each z slice was accounted for. The model outputs a probabability heatmap of embreyo centroids, and learns on an adaptive wing loss metric to focus on accurately identifying centroids. Centroids are the segmented to isolate the center and tracked over time using an hungarian assignment algorithm.

If I had more time, I really looked forward to:
1. Adding input manipulations (ex: flips, rotations) to input images to help with generalization
2. Implement a temporal transformer/simple neural network for predicting division to help with division detection and assignment

This was a really tough competition for me that I am glad I saw all the way through! I learned many ideas through using AI, following kaggle discussions, and general forum searches:
1. building kaggle dependencies for offline runs
2. interacting with .geff and building .zarr files
3. generating maps for anisotropy in voxel size
4. 3D U-Net Architecture with skip connections
5. Dealing with limited RAM/GPU/CPU/Memory (AKA Making models efficient)

Some smaller details that I still found to shape my experience include:
1. Working with adaptive wing loss metric and weighted losses
2. Experimenting with multiple decoders
3. Training data engineering (validation, k-fold, etc.)

From looking at winning submissions, I really hope to:
1. Study flow fields for predictions
2. Learn about emsemble modeling
3. Learn about Masked autoencoder
4. Teacher student model training is another area which I would love to learn about
5. Implement cross-attention in my projects
6. Implement more manipulations to training data for better generalization
7. Consider anisotropic pooling in future similar cases

In the end, I scored a 0.72450! I am happy with my progress

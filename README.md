Facial Image Characterization and Reconstruction Using Singular Value Decomposition (Eigenfaces)
This repository contains the assignment and implementation for the course AS1209 (Matrix Computations) at J.K. Lakshmipat University, Jaipur. The project explores the use of Singular Value Decomposition (SVD) to perform dimensionality reduction for facial image characterization and reconstruction, commonly known as the Eigenfaces method.
📁 Repository Contents
 * eigenfaces-reconstruction.ipynb: The Jupyter Notebook implementing the Eigenfaces algorithm. It includes code for generating the mean face, performing SVD, and demonstrating image reconstruction from masked data.
 * svd-eigenfaces-report.pdf: The formal assignment report, Facial Image Characterization and Reconstruction Using Singular Value Decomposition, detailing the mathematical background and results.
 * Dataset (External): The implementation is designed to work with a dataset of facial images. The example uses M=3000 images, each resized to an n \times m matrix (specifically 250 \times 250), resulting in N=62500 elements.
💡 Key Concepts and Implementation Steps
The Eigenfaces method involves the following core matrix computations:
1. Mean Image Calculation
The average image (\overline{\varphi}) represents the "common structure" of all faces in the dataset.
2. Perturbation Matrix Construction
Each individual image (\varphi_i) is flattened into an N \times 1 column vector. The perturbation matrix (P) is constructed by subtracting the mean face vector (\overline{\varphi}) from each individual face vector (\varphi_i).
3. Singular Value Decomposition (SVD)
SVD is performed on the perturbation matrix (P) to find the principal components (eigenvectors/eigenfaces). The left singular vectors (U) are the eigenvectors of AA^T (where A here is P).
The left singular vectors (u_i, or the columns of U) represent the principal components that form an orthonormal basis for the image space.
4. Image Reconstruction
A test image is reconstructed (\hat{\varphi}) by projecting the perturbation of the test image onto the principal components and adding the mean face back.
5. Error Analysis
The reconstruction error (using the Frobenius norm) decreases as more singular vectors (u_i) are included in the reconstruction sum (i.e., as i increases from k+1 to m). The error is determined by the remaining singular values.
⚙️ How to Run the Code
 * Prerequisites: Ensure you have Python, Jupyter Notebook, and the necessary libraries (numpy, matplotlib, PIL/Pillow) installed.
 * Dataset: The notebook requires a folder structure like dataset_small/train and dataset_small/test populated with grayscale facial images for the training and testing phases.
 * Execute Notebook: Open and run the eigenfaces-reconstruction.ipynb notebook. It will perform the SVD on the training data and demonstrate reconstruction on a test image, complete with a plot showing the reduction in error values as more singular vectors are used.

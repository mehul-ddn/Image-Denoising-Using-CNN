The project focuses on developing a model for the task of Image Denoising. The BSDS 500 dataset is used for training, validation, and testing(Link for the dataset - https://drive.google.com/drive/folders/1Aaj8TjehroKCwwSoGq7_mQpkXZgcrxfr?usp=sharing). The objective is to achieve a good  performance from the  Model developed and compare it other models.

The code starts by loading and preprocessing the training, validation, and testing datasets from the BSDS 500 dataset. The images are converted to grayscale and resized to a fixed height and width. Additionally, pairs of noisy and clean images are generated for training.

CNN Model:
The CNN model is defined using the Keras Sequential API. It consists of several convolutional layers, each followed by ReLU activation, and a final sigmoid activation layer. The model is then compiled using the mean squared error loss and the Adam optimizer with an initial learning rate of 0.001. Early stopping is applied during training to prevent overfitting. The model is trained using the generated noisy and clean image pairs.

Autoencoder Model:
The Autoencoder model is defined using the Keras Functional API. It consists of convolutional layers for encoding and upsampling layers for decoding. The model aims to reconstruct the noisy input images. The model is also compiled with the mean squared error loss and trained using the noisy images as both input and target.

After training both models, the denoising process is applied to the test images. The denoised images from both the CNN and Autoencoder models are obtained.

Performance Evaluation:
The performance of the denoised images is evaluated using two metrics: Peak Signal-to-Noise Ratio (PSNR) and Structural Similarity Index (SSIM). These metrics provide a quantitative measure of how well the denoised images match the original clean images.

The results are visualized through bar graphs for PSNR and SSIM, comparing the denoised images produced by the CNN and Autoencoder models for selected test images. The code also provides a comparison of the PSNR and SSIM values for both models on the same test images.

Findings:
The project demonstrates that both the CNN model and Autoencoder model are capable of denoising images. However, it is observed that the CNN model performs way better in terms of PSNR and SSIM compared to the Autoencoder model. The CNN model shows higher PSNR and SSIM values, indicating better denoising performance for the given dataset.

Future Improvements:
The project suggests potential areas for improvement. It can be noted that both models might achieve even higher denoising performance with more epochs, a larger dataset (possibly larger size), and more computing capabilities. To further improve the models' capacity for denoising, optimisations in the model architectures or hyperparameters may also be investigated.

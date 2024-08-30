# Implementation of Underwater Image Enhancement

## Project Overview

This project focuses on enhancing underwater images, which are crucial in various fields such as marine research, underwater surveillance, and inspection of aquatic habitats. Underwater images often suffer from low visibility, color distortion, and low contrast due to light absorption and scattering as depth increases. This project aims to develop an effective method for enhancing these images to improve their quality and usability.

## Abstract

Underwater images are significantly degraded due to the absorption and scattering of light in water, especially at greater depths where red light is absorbed more due to its longer wavelength, resulting in predominantly bluish-green images. The project addresses this issue by implementing an image enhancement technique that improves image quality while preserving critical information, making it suitable for various applications like marine research and underwater surveillance.

## Dataset Used

A dataset consisting of seven underwater images with their corresponding reference images was used for this project. The images were chosen to cover a range of visibility and color distortion levels, providing a comprehensive testbed for the enhancement techniques.

## Approach

The enhancement process involves several key steps:

- **Color Correction**:
  - **Histogram Analysis**: Histograms of the RGB channels were analyzed to understand the distribution and degradation of colors in underwater images.
  - **Compensation for Red and Blue Channels**: A compensation formula was applied to adjust the red and, when necessary, blue channels by adding a fraction of the green channel, which is the least degraded.
  - **White Balancing**: The Gray World algorithm was used to perform white balancing, reducing color distortion.

- **Contrast Enhancement**:
  - **Global Histogram Equalization**: Images were converted to the HSV color space, and the Value component was equalized to enhance contrast, then recombined with the original Hue and Saturation components.

- **Image Sharpening**:
  - **Unsharp Masking**: Applied to the color-corrected images to enhance edges and improve clarity.

- **Image Fusion**:
  - **Averaging-based Fusion**: Combined the contrast-enhanced and sharpened images by averaging corresponding pixel intensities.
  - **PCA-based Fusion**: Principal Component Analysis was used to create a fused image by emphasizing the components that contribute most to image clarity.

- **Performance Metrics**:
  - **MSE and PSNR**: Mean Squared Error (MSE) and Peak Signal-to-Noise Ratio (PSNR) were calculated to evaluate the quality of the enhanced images against the reference images.

## Observations & Results

The enhanced images showed significant improvement in visibility and color fidelity, with less degradation in the RGB channels compared to the original images. The PCA-based fusion method generally provided better results than the averaging method, as evidenced by lower MSE and higher PSNR values.

## Conclusion

The project successfully developed a method for enhancing underwater images that improves contrast and reduces color distortion. While effective, the method may produce artifacts in certain conditions, such as blue artifacts on whitish areas with bubbles. Future improvements could include automating the process to adjust for different types of degradation and increasing the robustness to handle a broader range of underwater image conditions.

## Technologies and Tools Used

- **Programming Languages**: Python
- **Libraries**: OpenCV, NumPy, Matplotlib
- **Algorithms**: Histogram Equalization, Unsharp Masking, PCA, Gray World White Balancing
- **Performance Metrics**: MSE, PSNR

## Significance of the Project

This project provides a robust framework for enhancing underwater images, which is essential for fields requiring accurate visual data from underwater environments. By improving image clarity and color accuracy, the project contributes to advancements in marine research, underwater exploration, and environmental monitoring.

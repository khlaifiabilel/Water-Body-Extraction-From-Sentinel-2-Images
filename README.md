# Water-Body-Extraction-From-Sentinel-2-Images

## Description 
The project presents a deep learning model that extracts water bodies from Sentinel-2 satellite images. Traditional methods for water extraction have limitations, and therefore we propose a new model called the Attentional Dense Convolutional Neural Network (ADCNN).

## Architecture 

The model is based on a combination of dense convolutional neural networks (DenseNet) and an attention mechanism. DenseNet is a deep learning architecture that connects each layer to every other layer in a feedforward fashion. This allows for better feature reuse and gradient propagation. The attention mechanism allows the model to focus on the most important regions of the image for water extraction.

The attention mechanism used in This project is a type of self-attention mechanism called the squeeze-and-excitation (SE) block. This mechanism is used to adaptively recalibrate the feature maps of the convolutional neural network (CNN) based on their importance for the task at hand, in this case, water body extraction.

The SE block has two main components: the squeeze operation and the excitation operation. The squeeze operation aggregates the feature maps along the spatial dimensions (i.e., width and height) to generate a channel descriptor vector that captures the channel-wise statistics of the feature maps. This is done using a global average pooling operation that computes the average of each channel's activation map.

The excitation operation then uses a two-layer neural network to generate a channel-wise attention map based on the channel descriptor vector. The first layer is a fully connected layer that reduces the dimensionality of the channel descriptor vector and applies a nonlinear activation function. The second layer is also a fully connected layer that maps the output of the first layer to a channel-wise attention map. The attention map is then applied element-wise to the original feature maps to generate the final, attention-weighted feature maps.

By using the SE block, the ADCNN model can dynamically adapt to the spatial and channel-wise characteristics of the input data and focus on the most important regions of the image for water body extraction. This results in improved performance compared to using a standard CNN without attention.

## Sentinel 2  indexes
We have used two spectral indices to extract water body marks from Sentinel-2 satellite images. These indices are the Normalized Difference Water Index (NDWI) and the Modified Normalized Difference Water Index (MNDWI).

The NDWI is a widely used index for water body extraction and is defined as:

NDWI = (Green - NIR) / (Green + NIR)

where Green is the reflectance in the green band and NIR is the reflectance in the near-infrared band. The NDWI measures the difference in absorption between water and vegetation and is sensitive to the presence of water bodies.

The MNDWI is a modified version of the NDWI that is more effective in areas with built-up features such as urban areas. The MNDWI is defined as:

MNDWI = (Green - SWIR) / (Green + SWIR)

where SWIR is the reflectance in the short-wave infrared band. The MNDWI is similar to the NDWI but uses the SWIR band instead of the NIR band, which makes it more sensitive to the presence of man-made features such as buildings and roads.

In the paper, the authors used a combination of the NDWI and MNDWI indices to generate a single water body extraction mask. The indices were computed for each Sentinel-2 satellite image and the resulting masks were combined using a logical OR operation. This approach helped to improve the accuracy of the water body extraction compared to using a single index alone.

## Sentinel 2 bands
We have used multiple bands from Sentinel-2 satellite images to extract water body marks.

Specifically, the authors used the following 10 spectral bands from Sentinel-2:

Band 2: Blue
Band 3: Green
Band 4: Red
Band 5: Vegetation Red Edge 1
Band 6: Vegetation Red Edge 2
Band 7: Vegetation Red Edge 3
Band 8: Near-Infrared
Band 8A: Narrow Near-Infrared
Band 11: Short-Wave Infrared 1
Band 12: Short-Wave Infrared 2

These bands cover a wide range of the electromagnetic spectrum, from visible to short-wave infrared wavelengths. The combination of these bands allows for the extraction of water body marks using spectral indices such as the Normalized Difference Water Index (NDWI) and the Modified Normalized Difference Water Index (MNDWI).
In addition to the spectral bands, the authors also used a cloud mask and a normalized difference vegetation index (NDVI) to preprocess the Sentinel-2 images before feeding them into the Attentional Dense Convolutional Neural Network (ADCNN) model. The cloud mask was used to remove cloudy pixels, while the NDVI was used to mask out vegetation pixels.

## Contributing
We welcome contributions from the community. If you would like to contribute to the project, please follow these steps:

Fork the repository
Create a new branch for your feature or bug fix
Make your changes and commit them
Push your changes to your forked repository
Create a pull request to merge your changes into the main repository
We will review your changes and merge them if they meet our standards.

## License
This project is licensed under the MIT License.

## Contact
If you have any questions or comments about the project, please contact us at Khlaifiabilel@icloud.com.

# SegNet: A Deep Convolutional Encoder-Decoder Architecture for Image Segmentation
Badrinarayanan, Vijay, Alex Kendall, and Roberto Cipolla. "SegNet: A Deep Convolutional Encoder-Decoder Architecture for Image Segmentation." arXiv preprint arXiv:1511.00561 (2015). 

## Introduction
**Segnet** is a deep fully CNN architecture for semantic pixel-wise segmentation. It consists of an encoder network and a corresponding decoder network followed by a pixel-wise classification layer. The architecture of the encoder network is topologically identical to the 13 convolutional layers in the VGG16 network. **The role of the decoder network is to map the low resolution encoder feature maps to full input resolution feature maps for pixel-wise classification.** Specifically, the decoder uses pooling indices computed in the max-pooling step of the corresponding encoder to perform non-linear upsampling. Therefore, the upsampled maps are sparse and are then convolved with trainable filters to produce dense feature maps.

some of these recent approaches have tried to directly adopt deep architectures designed for category prediction to pixel-wise labelling. The results, although very encouraging, appear coarse. This is primarily because max pooling and sub-sampling reduce feature map resolution. SegNet dealt with this issue by map low resolution features to input resolution for pixel-wise classification.

SegNet has some characteristic:
- Retain boundary information in the extracted image representation.
- Train end-to-end, which enable using SGD to update weight efficiently (without multi-stage training or other supporting aids, e.g. region proposals)
- Efficient in terms of both memory and computation time during inference. (?)

By reusing max-pooling indices in the decoding process, it achieve 
- it improves boundary delineation
- it reduces the number of parameters enabling end-to-end training
- this form of upsampling can be incorporated into any encoder-decoder architecture

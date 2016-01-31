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

## Literature
Typically, a patch is fed into a classifier e.g. random forest or boosting, to predict the class probabilities of the center pixel. These per-pixel noisy predictions (often called unary terms) from the classifiers are then smoothed by using a pair-wise or higher order CRF to improve the accuracy. The result of all these techniques indicate **the need for improved features for classification**.

- The CRF-RNN network can be appended to any core segmentation engine including SegNet.
- Multi-scale deep architectures are also being pursued.

Several of the recently proposed deep architectures for seg- mentation are not feed-forward in inference time. They require either MAP inference over a CRF or aids such as region proposals for inference. **SegNet on the other hand uses decoders to obtain features for accurate pixel-wise classification.**

The recently proposed Deconvolutional Network and its semi-supervised variant the Decoupled network use the max locations of the encoder feature maps (pooling indices) to perform non-linear upsampling in the decoder network. **In this work we discard the fully connected layers of the VGG16 encoder network which enables us to train the network using the relevant training set using SGD optimization.**

**This work was inspired by the unsupervised feature learning architecture proposed by Ranzato et al. [1]**

## Reference
[1] M. Ranzato, F. J. Huang, Y. Boureau, and Y. LeCun, “Unsupervised learning of invariant feature hierarchies with applications to object recognition,” in CVPR, 2007.

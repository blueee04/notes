+++
title = "Evaluation metrics of Generative Adversarial Networks"
date = "2024-02-11"
summary = "Evaluating generative adversarial networks (GANs) is inherently challenging. In this paper, we revisit several representative sample-based evaluation metrics for GANs, and address the problem of how to evaluate the evaluation metrics. "
+++

**FID** - To evaluate the quality of the generated images, we use FID to measure the distance between the generated distribution and the real one through features extracted by Inception Network. Lower FID values indicate better quality of the generated images.

**LPIPS** - To evaluate diversity, we employ LPIPS [30] following [10, 14, 32]. LIPIS measures the average feature distances between generated samples. Higher LPIPS score indicates better diversity among the generated images

**NDB and JSD** - To measure the similarity between the distribution between real images and generated one, we adopt two bin-based metrics, NDB and JSD, proposed in. These metrics evaluate the extent of mode missing of generative models. Following, the training samples are first clustered using K-means into different bins which can be viewed as modes of the real data distribution. Then each generated sample is assigned to the bin of its nearest neighbor. We calculate the bin-proportions of the training samples and the synthesized samples to evaluate the difference between the generated distribution and the real data distribution. NDB score and JSD of the bin-proportion are then computed to measure the mode collapse. Lower NDB score and JSD mean the generated data distribution approaches the real data distribution better by fitting more modes.

![](https://cdn.discordapp.com/attachments/1099629557126012940/1212823014580686989/image.png?ex=65f33c73&is=65e0c773&hm=68be318c5f171ef28f21395e0a1c79a055fa17e1f04b1a561af75e939f573627&)

### Conditioned on Class Label

We first validate the proposed method on categorical generation. In categorical generation, networks take class labels as conditional contexts to synthesize images of different categories. We apply the regularization term to the baseline framework DCGAN. We conduct experiments on the CIFAR-10 dataset which includes images of ten categories. Since images in the CIFAR-10 dataset are of size 32 × 32 and upsampling degrades the image quality, we do not compute LPIPS in this task. Table 1 present the results of NDB, JSD, and FID. MSGAN mitigates the mode collapse issue in most classes while maintaining image quality.


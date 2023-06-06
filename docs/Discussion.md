---
layout: default
title: Discussion
nav_order: 7
has_children: false
permalink: /docs/discussion
---

# Discussion and Future Work

---

## Limitations

The current approach has several limitations. Firstly, despite the considerable time-saving benefits of the automatic data labeling pipeline, the quality of the segmentation and annotation results can be further improved through manual annotation. For example, users can use Roboflow's annotation editor to modify the object's labeling and segmentation boundary. Aside from improving the quality of the dataset, the size of the dataset can be expanded for more effective model training. Our dataset currently comprises roughly 700 images for each class, but we hypothesize that the model could perform better by doubling the size of the dataset. One possible strategy for expanding the training dataset is by incorporating various unused data augmentation techniques in this research, such as adding Gaussian noise.

## Future Work

Future works in the field can focus on further improving the current model's performance on semantic segmentation tasks by exploring different variations of vision transformers, such as MobileViT [14], Transformer iN Transformer (TNT) [4], and Swin Transformer [12]. We believe the self-attention mechanism would enable the model to understand the contextual relationships between pixels or regions and make more informed segmentation decisions. Moreover, by attending to all tokens (image patches) in the input instead of relying on local receptive fields like in CNNs, the model could better understand the spatial relationships between objects and background. Besides, classifying garbage into 12 classes is unlikely to be practical in real life due to space constraints and increased costs for acquiring and maintaining more trash cans. Therefore, we encourage researchers to determine a suitable number of classes based on user studies and real-world analysis.

## Conclusion

In this research, we validate the viability of real-time garbage segmentation using models that judiciously balance computational efficiency and accuracy. We propose the combination of MobileNetV3 and DeepLabv3 as our solution for real-time garbage segmentation tasks. Our findings underscored the importance of maintaining a moderate model complexity in real-time garbage segmentation tasks: a lighter backbone like MobileNetV3 is crucial and can lead to a more significant increase in inference speed than simplifying the head.

Additionally, our contribution extends to the novel data processing paradigm we developed, significantly improving segmentation and annotation efficiency and effectiveness. We hope our dataset processing paradigm sets a foundation for future research in other real-time semantic segmentation tasks.

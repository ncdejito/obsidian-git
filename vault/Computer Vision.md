[[Machine Learning]]

## Semantic Segmentation

## Object Detection
[Foundations](https://lilianweng.github.io/posts/2017-12-31-object-recognition-part-3/)

IoU - intersection over union, Jaccard index

NMS (non-maximum suppression) - from all intersecting boxes with specified IoU threshold get highest confidence

Imbalanced datasets - use Precision Recall, F1

[mAP](https://jonathan-hui.medium.com/map-mean-average-precision-for-object-detection-45c121a31173)
compare detections with ground truth, 
consider correct if detection and ground truth intersect by IoU threshold, 
sort detections by confidence, 
calculate precision and recall for each row, 
plot precision vs recall in graph, 
area under curve is mAP
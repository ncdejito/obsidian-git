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

Yolov1 to v8 review
https://www.researchgate.net/publication/369760111_A_Comprehensive_Review_of_YOLO_From_YOLOv1_to_YOLOv8_and_Beyond

Satellite detection
Waldo
Yolo nas sat
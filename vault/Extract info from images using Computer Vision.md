[[Deep Learning]]

Python Rust Computer Vision - [Rerun.io](https://github.com/rerun-io)
No-code VisualBlocks - https://github.com/google/visualblocks
Resources for learning computer vision
https://www.linkedin.com/posts/activity-7083338933912121344-2Mmn?utm_source=share&utm_medium=member_desktop

## Semantic Segmentation
Segment anything by Meta
https://www.linkedin.com/posts/asturksever_meta-ai-introduced-segment-anything-i-just-activity-7049719568956551168-Ecgx?utm_source=share&utm_medium=member_android

Segment anything on medical image segmentation
https://www.linkedin.com/posts/nick-konz-247988168_im-excited-to-present-our-paper-segment-activity-7055202700107395072-3NsP?utm_source=share&utm_medium=member_android

No training data needed [STEGO](https://www.youtube.com/watch?v=58uhMDO7dTQ)

Filed Boundary Detection [RadiantHub](https://www.linkedin.com/posts/radiant-mlhub_machinelearning-models-activity-7047212001328062465-sin_?utm_source=share&utm_medium=member_desktop)



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

Yolov1 to v8 review
https://www.researchgate.net/publication/369760111_A_Comprehensive_Review_of_YOLO_From_YOLOv1_to_YOLOv8_and_Beyond

Label Annotation - LandingAI by Andrew Ng
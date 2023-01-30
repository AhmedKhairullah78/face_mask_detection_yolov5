# face_mask_detection_yolov5
“YOLO”, refering to “You Only Look Once”, is a family of object detection models introduced by Joseph Redmon with a 2016 publication “You Only Look Once: Unified, Real-Time Object Detection”.

Since then, several newer versions have been released, of which, the first three were released by Joseph Redmon. On June 29, Glenn Jocher released the latest version YOLOv5, claiming significant improvements with respect to its predecessor.

The most interesting improvement, is its “blazingly fast inference”. As posted in this article by Roboflow, running in a Tesla P100, YOLOv5 achieves inference times of up to 0.007 seconds per image, meaning 140 FPS!


YOLO models comparison (image source)
Why YOLO?
Using an object detection model such as YOLOv5 is most likely the simplest and most reasonable approach to this problem. This is because we’re limiting the computer vision pipeline to a single step, since object detectors are trained to detect a:

Bounding box and a
Corresponding label
This is precisely what we’re trying to achieve for this problem. In our case, the bounding boxes will be the detected faces, and the corresponding labels will indicate whether the person is wearing a mask or not.

Alternatively, if we wanted to build our own deep learning model, it would be more complex, since it would have to be 2-fold: we’d need a model to detect faces in an image, and a second model to detect the presence or absence of face mask in the found bounding boxes.

A drawback of doing so, apart from the complexity, is that the inference time would be much slower, especially in images with many faces.

What about the data?
We now know which model we can use for this problem. The next natural, and probably most important, aspect is… what about the data??

Luckily, there is a publicly available dataset in Kaggle named Face Mask Detection, which will make our life way easier.

The dataset contains 853 images and their corresponding annotation files, indicating whether a person is wearing a mask correctly, incorrectly or not wearing it.

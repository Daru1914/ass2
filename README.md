# Assignment 2:

### Progress Report:

1.
##### Task: Take photos of your environment of two or more objects. (at least 100 instances between all objects) 

Solution: I have simply reused the dataset from the previous assignment - 39 images with >100 instances of chairs and radiators and 1 image of a monkey living in a society.

Screenshot:![image](https://user-images.githubusercontent.com/63430051/235314488-1fb85fe7-aeb8-4d3a-8f05-a1273370e295.png)

2.
##### Task: Annotate them on Roboflow for segmentation.

Solution: I have annotated all the images for segmentation using the automatic tool provided by Roboflow, and corrected them manually when the tool did not provide sufficient precision.

Screenshot:![image](https://user-images.githubusercontent.com/63430051/235314642-140f5680-d825-4752-8eb2-857f75f653bc.png)

3.
##### Task: Train a Mask RCNN model using detectron2.

Solution: I have trained the Mask RCNN model using detectron2 by following all the steps presented in the Mask RCNN notebook on Roboflow - training took 500 epochs. Below I present the screenshot of the result of applying said model to one of the images in the validation dataset.

Screenshot:![image](https://user-images.githubusercontent.com/63430051/235314960-bde13a1b-ae00-4d23-8bb5-d7a0804018c6.png)

4.
##### Task: Train Yolov8 the smallest size for segmentation.

Solution: I have trained the yolov8n-seg.pt (YoloV8nano) by following all the steps presented in the YoloV8 Image Segmentation notebook on Roboflow - training took 167/500 epochs (stopped early due to no improvement of loss). Below I present the screenshot of the result of applying said model to one of the images in the validation dataset.

Screenshot:![image](https://user-images.githubusercontent.com/63430051/235315077-0d808407-dde7-4023-8b95-6e295e8eb232.png)

5.
##### Task: Evaluate both models based on mAP and speed and size.

Solution: mAP of Mask RCNN: ![image](https://user-images.githubusercontent.com/63430051/235315269-25e975f0-e4be-4848-a0a0-ede18671af0f.png)

mAP of YoloV8n: ![image](https://user-images.githubusercontent.com/63430051/235315341-962c5f27-d28e-4cd2-a1ca-0db23fe0dfea.png)

As we can see, both models have a much easier time identifying a radiator rather than a chair, while YoloV8n has a slightly better mean average precision in general than detectron2 model.

speed of Mask RCNN: ![image](https://user-images.githubusercontent.com/63430051/235315626-bf50134e-7913-4eaf-a9b1-18108c7e59ee.png)

![image](https://user-images.githubusercontent.com/63430051/235315670-e8a3d5a8-2c7b-4527-8da8-61428802946c.png)

Training of 500 iterations took around 9 minutes.

speed of YoloV8n: ![image](https://user-images.githubusercontent.com/63430051/235315777-df8abf6c-debc-40b0-9ce1-7f1b1fd0af58.png)

YoloV8n is therefore significantly slower than Mask RCNN.

size of Mask RCNN: ![image](https://user-images.githubusercontent.com/63430051/235315840-47f3881a-993b-42ab-a259-59556e8f0e7e.png)

size of YoloV8n: ![image](https://user-images.githubusercontent.com/63430051/235315864-47c94d8a-972d-4f60-8c51-9ba36023031f.png)

YoloV8n demonstrably uses much more memory than Mask RCNN.

Conclusion: while Mask RCNN with detectron2 has slightly worse mAP scores than YoloV8n, it is a significantly faster and more memory-efficient model.

6. Links to Colab:
Mask RCNN: https://colab.research.google.com/drive/1xZZVwJvqGG84ay_iz9Y6hYpGJKGq6kOJ?usp=sharing
YoloV8: https://colab.research.google.com/drive/1j3SVvKKa7MUx6mIMOYjyWMNLWxNHICgp?usp=sharing

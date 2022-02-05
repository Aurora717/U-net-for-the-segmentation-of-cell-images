
# U-net-for-the-segmentation-of-cell-images

U-net (Ronneberger et al., (2015) is a Fully Convolutional Network for supervised image segmentation.U-net expands upon Fully Convolutional Neural networks (FCN) to yield a network that doesn’t require a large number of training examples while producing better segmentations. The architecture is illustrated in the figure below.

<img width="600" alt="Screenshot 2022-02-05 at 19 36 57" src="https://user-images.githubusercontent.com/49812606/152652549-ff53e261-6c84-4d68-b3fb-237812ef6299.png">

The network consists of 9 modules, where each module contains two 3x3 convolutional layers with a ReLU activation function, followed by batch normalization. The U-shape of the network is attributed to having a contracting/ downsampling path and a symmetrical expansive/upsampling path. The downsampling modules are connected by
a 2x2 max-pooling layer that doubles the number of feature channels, the purpose of the path is to capture context, i.e., what is in the image. The upsampling
modules are connected by 2x2 2D transposed convolutional layers that halve the number of feature channels, the purpose of the path is to capture location, i.e.,
where are the objects in the image. Skip Connections   are used to retrieve the spatial information lost during the downsampling process.The final layer is a 1x1
convolution that maps features to the desired output. None of the network’s layers are fully connected and only the segmentation map is used at each convolution.

For this project, I built and used U-net to segment images of cells. The dataset is a public dataset found on kaggle https://www.kaggle.com/paultimothymooney/identification-and-segmentation-of-nuclei-in-cells

![cell](https://user-images.githubusercontent.com/49812606/152652784-7a7738dd-0c9e-4f6a-bae9-915206ca997f.png)
![cell00](https://user-images.githubusercontent.com/49812606/152652791-171d5de2-6075-45ec-82ff-7fe9a8e0a35f.png)

Here are some of the results of the network:

![real_9](https://user-images.githubusercontent.com/49812606/152652841-3b2b1995-b059-4132-96b1-82613e910bca.png)
![pred_9](https://user-images.githubusercontent.com/49812606/152652844-d76866db-39de-40a2-b0cd-cbd65a0bbac3.png)
![real_25](https://user-images.githubusercontent.com/49812606/152652848-33f5d5cc-c653-4f9d-b5af-95ebbafea3d0.png)
![pred_25](https://user-images.githubusercontent.com/49812606/152652849-04d9333c-3f66-4d4e-b0c7-28de356e1f5b.png)
![real_30](https://user-images.githubusercontent.com/49812606/152652850-d3083cb0-2df3-47c2-b347-0e91fba9d2ee.png)
![pred_30](https://user-images.githubusercontent.com/49812606/152652852-6389d2e9-4eb4-4c20-a857-5f94d549aadc.png)
![real_527](https://user-images.githubusercontent.com/49812606/152652855-b81dad0d-ee17-4660-9c47-a9605cca39b1.png)
![pred_527](https://user-images.githubusercontent.com/49812606/152652857-64ffffea-1f11-417a-9b8e-85ca97a04d3e.png)

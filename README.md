# Face-Recognition-Siamese-Network
Face recognition with Siamese Network

    We send a triplet of images into the neural network to calculate the euclidean distances as done in the loss function. Increment count by one each type the loss is zero. Divide the resultant by the total number of triplets and multiplied them by 100 to get our accuracy. With the current adjustments our model gives us the accuracy of 80.DATASET DETAILS
    In our project we used the Labelled Faces in the Wild (LFW) dataset. The data set contains more than 13,000 images of faces collected from the web. Each face has been labeled with the name of the person pictured. 1680 of the people pictured have two or more distinct photos in the data set. 

## Steps to run

    1. To access the dataset from the shareable link of the drive, copy and paste the link below in your browser.

    https://drive.google.com/drive/folders/1OJ_-xTedx0kQE4AEuMOX0fC9IoorQwK5?usp=sharing

    2. To use the data set to run the project use the following pattern to mount the dataset on the drive, make sure that the dataset in the following path:

    “/content/Drive/My Drive/”

    The project file should also be in the same directory in order for it to run.

    3. Run the code on Collab

## PRE PROCESSING
    Pre processed the data and converted it into tensor using ToTenser() function and resized the data to 224 rows and 224 columns. We trained our data on the siamese network and then tested on randomly picked data to calculate the accuracy of the model.
    EXTRACTING TRIPLETS
    We extracted triplets by inheriting the __getitem__() function of class torchvision. datasets. DatasetFolder.We modified the function to get triplets of the form [anchor, positive, negative]. We extracted the paths and labels of a random index and assigned it to the anchor image. Then we picked up the path of the image having the same label as the positive image. Negative image was picked randomly in a way that its label does not match with the anchor image. 
    
## SIAMESE NETWORK
    In the implementation of the siamese neural network we used convolutional and linear layers to train our network.

## TRIPLET LOSS
    In the loss function we sent the three images the anchor image the positive image and the negative that resulted from extracting triplet from the datasets.We calculated the euclidean distance first between, the anchor image and the positive image then between the anchor image and the negative image Subtracted the positive euclidean distance from the negative euclidean distance. Then we calculated the max(dist_pos_anch-dist_neg_anch,0) so that if the value is -ive it returns 0 otherwise the loss calculated is returned.

## TESTING



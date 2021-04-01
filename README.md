# pokemon autoencoder
Training a Vanilla AutoeEncoder to encode and decode pokemons.

[Dataset](https://www.kaggle.com/vishalsubbiah/pokemon-images-and-types) is available in kaggle. Download the dataset and unzip it. Unzipped folder, preprocessing.ipynb and Vanilla AutoEncoder.ipynb should be in the same folder

In this dataset, there are 809 pokemons, 789 of them will be used in training, 20 of them will be used to test (eye test) the results.

AutoEncoder pipeline.

- Encode images of size 120 x 120 x 4 (rgba) to 8 x 8 x 128  (57600 pixels to 8192 pixels)
- Decode images of size  to 8 x 8 x 128 to 120 x 120 x 4 (rgba)  (8192 pixels to 57600 pixels)

Install the required libraries
```bash
$ pip install -r requirements.txt
```

Run the preprocessing.ipynb to construct the following files.

         ├── trainTensor.pt                 
         └── testTensor.pt
         └── trainLabels.txt
         └── testLabels.txt
         
Then, run the Vanilla AutoEncoder.ipynb to train the network and reconstruct pokemons.


## Train

### Results after epochs

![/epochImgs/epoch1.png](/epochImgs/epoch1.png)  |  ![/epochImgs/epoch5.png](/epochImgs/epoch5.png)
:-------------------------:|:-------------------------:
Reconstructing a random pokemon after epoch 1            |  Reconstructing a random pokemon after epoch 5


![/epochImgs/epoch20.png](/epochImgs/epoch20.png)  |  ![/epochImgs/epoch40.png](/epochImgs/epoch40.png)
:-------------------------:|:-------------------------:
Reconstructing a random pokemon after epoch 20        |  Reconstructing a random pokemon after epoch 40

![/epochImgs/epoch80.png](/epochImgs/epoch80.png)  |  ![/epochImgs/epoch146.png](/epochImgs/epoch146.png)
:-------------------------:|:-------------------------:
Reconstructing a random pokemon after epoch 80        |  Reconstructing a random pokemon after epoch 146


![/epochImgs/epoch296.png](/epochImgs/epoch296.png)  |  ![/epochImgs/epoch313.png](/epochImgs/epoch313.png)
:-------------------------:|:-------------------------:
Reconstructing a random pokemon after epoch 296        |  Reconstructing a random pokemon after epoch 313

![/epochImgs/epoch381.png](/epochImgs/epoch381.png)  |  ![/epochImgs/epoch400.png](/epochImgs/epoch400.png)
:-------------------------:|:-------------------------:
Reconstructing a random pokemon after epoch 381        |  Reconstructing a random pokemon after epoch 400


In the first epochs, network learns to reconstruct the shape of the pokemon.


Around epoch 45, network starts to learn reconstructing colors. However, until epoch 290+, reconstucted colors don't match with the original pokemon.


## Testing on unseen pokemons

![/resultImgs/unseen1.png](/resultImgs/unseen1.png)  |  ![/resultImgs/unseen2.png](/resultImgs/unseen2.png)
:-------------------------:|:-------------------------:
Test 1          |  Test 2

![/resultImgs/unseen3.png](/resultImgs/unseen3.png)  |  ![/resultImgs/unseen2.png](/resultImgs/unseen4.png)
:-------------------------:|:-------------------------:
Test 3         |  Test 4

![/resultImgs/unseen5.png](/resultImgs/unseen5.png)  |  ![/resultImgs/unseen6.png](/resultImgs/unseen6.png)
:-------------------------:|:-------------------------:
Test 5          |  Test 6

![/resultImgs/unseen7.png](/resultImgs/unseen7.png)  |  ![/resultImgs/unseen8.png](/resultImgs/unseen8.png)
:-------------------------:|:-------------------------:
Test 7        |  Test 8

![/resultImgs/unseen9.png](/resultImgs/unseen9.png)  |  ![/resultImgs/unseen10.png](/resultImgs/unseen10.png)
:-------------------------:|:-------------------------:
Test 9       |  Test 10

![/resultImgs/unseen11.png](/resultImgs/unseen11.png)  |  ![/resultImgs/unseen12.png](/resultImgs/unseen12.png)
:-------------------------:|:-------------------------:
Test 11       |  Test 12


![/resultImgs/unseen11.png](/resultImgs/unseen13.png)  |  ![/resultImgs/unseen12.png](/resultImgs/unseen14.png)
:-------------------------:|:-------------------------:
Test 13      |  Test 14

![/resultImgs/unseen15.png](/resultImgs/unseen15.png)  |  ![/resultImgs/unseen16.png](/resultImgs/unseen16.png)
:-------------------------:|:-------------------------:
Test 15       |  Test 16

![/resultImgs/unseen17.png](/resultImgs/unseen17.png)  |  ![/resultImgs/unseen18.png](/resultImgs/unseen18.png)
:-------------------------:|:-------------------------:
Test 17       |  Test 18

![/resultImgs/unseen19.png](/resultImgs/unseen19.png)  |  ![/resultImgs/unseen20.png](/resultImgs/unseen20.png)
:-------------------------:|:-------------------------:
Test 19       |  Test 20

## Running Keras on Floyd

[Floyd](https://www.floydhub.com/) has native support for Keras including Tensorflow or Theano backends. This page lists some of the best example projects for Keras.

## Keras Official Examples

The Keras project ([fchollet/keras](https://github.com/fchollet/keras)) itself comes with a great set of [examples](https://github.com/fchollet/keras/tree/master/examples) for Keras. These range from simple CNN to deep dream transformation of your own images.

You can start by cloning the keras repository and initializing a floyd project.

```bash
$ git clone https://github.com/fchollet/keras
$ cd keras/examples
$ floyd init keras-examples
```

### Deep Dream

To run the `deep_dream.py` example on a GPU instance:
First download the image you want to transform the current directory.
Then run floyd using the Keras environment.

```bash
$ wget URL/sample.jpg
$ floyd run --env keras --gpu python deep_dream.py sample.jpg /output/
$ floyd logs -t <RUN_ID>
$ floyd output <RUN_ID>
```
The output should contain all the deep dream generated images.

### CNN on Cifar10

To train a simple deep CNN on the CIFAR10 small images dataset:

```bash
$ wget URL/sample.jpg
$ floyd run --env keras --gpu python cifar10_cnn.py
$ floyd logs -t <RUN_ID>
```

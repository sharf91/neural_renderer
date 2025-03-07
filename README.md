# Neural 3D Mesh Renderer (CVPR 2018)

This repo contains a PyTorch implementation of the paper [Neural 3D Mesh Renderer](http://hiroharu-kato.com/projects_en/neural_renderer.html) by Hiroharu Kato, Yoshitaka Ushiku, and Tatsuya Harada.
It is a port of the [original Chainer implementation](https://github.com/hiroharu-kato/neural_renderer) released by the authors.
Currently the API is the same as in the original implementation with some smalls additions (e.g. render using a general 3x4 camera matrix, lens distortion coefficients etc.). However it is possible that it will change in the future.

The library is fully functional and it passes all the test cases supplied by the authors of the original library.
Detailed documentation will be added in the near future.

## Fork Notes:
Compiles with Python 3.7, 3.9 and Pytorch 1.10 on both Linux and Windows.

## Requirements
To run the examples you will need the following packages:
```
tqdm
imageio
scikit-image
```
## Installation

### __Linux__
The installation is done using conda.
Make sure to install the same version of cudatoolkit-dev as used for pytorch.
```
conda create -n render python=3.9
conda install pytorch torchvision torchaudio cudatoolkit=11.3 -c pytorch
conda install -c conda-forge cudatoolkit-dev=11.3
```
Then finally install using 
```
python setup.py install
```
### __Windows__
```
conda create -n render python=3.9
conda install pytorch torchvision torchaudio cudatoolkit=11.3 -c pytorch
```
You also need to manually install cuda. Make sure down download the same version as used for pytorch.

Then finally install using 
```
python setup.py install
```

## Running examples
```
python ./examples/example1.py
python ./examples/example2.py
python ./examples/example3.py
python ./examples/example4.py
```


## Example 1: Drawing an object from multiple viewpoints

![](https://raw.githubusercontent.com/hiroharu-kato/neural_renderer/master/examples/data/example1.gif)

## Example 2: Optimizing vertices

Transforming the silhouette of a teapot into a rectangle. The loss function is the difference between the rendered image and the reference image.

Reference image, optimization, and the result.

![](https://raw.githubusercontent.com/hiroharu-kato/neural_renderer/master/examples/data/example2_ref.png) ![](https://raw.githubusercontent.com/hiroharu-kato/neural_renderer/master/examples/data/example2_optimization.gif) ![](https://raw.githubusercontent.com/hiroharu-kato/neural_renderer/master/examples/data/example2_result.gif)

## Example 3: Optimizing textures

Matching the color of a teapot with a reference image.

Reference image, result.

![](https://raw.githubusercontent.com/hiroharu-kato/neural_renderer/master/examples/data/example3_ref.png) ![](https://raw.githubusercontent.com/hiroharu-kato/neural_renderer/master/examples/data/example3_result.gif)

## Example 4: Finding camera parameters

The derivative of images with respect to camera pose can be computed through this renderer. In this example the position of the camera is optimized by gradient descent.

From left to right: reference image, initial state, and optimization process.

![](https://raw.githubusercontent.com/hiroharu-kato/neural_renderer/master/examples/data/example4_ref.png) ![](https://raw.githubusercontent.com/hiroharu-kato/neural_renderer/master/examples/data/example4_init.png) ![](https://raw.githubusercontent.com/hiroharu-kato/neural_renderer/master/examples/data/example4_result.gif)


## Citation

```
@InProceedings{kato2018renderer
    title={Neural 3D Mesh Renderer},
    author={Kato, Hiroharu and Ushiku, Yoshitaka and Harada, Tatsuya},
    booktitle={The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
    year={2018}
}
```

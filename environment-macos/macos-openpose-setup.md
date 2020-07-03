# Mac os Openpose setup

## Installation on Mac (https://github.com/CMU-Perceptual-Computing-Lab/openpose/blob/master/doc/installation.md#installation)

1) Check this: https://stackoverflow.com/questions/58081084/target-boostlibrary-already-has-an-imported-location-link-errors if warnings occur during CMake generation
2) CMake generate, see instructions above
3) Don't forget to check BUILD PYTHON
4) cd build/
5) make -j`sysctl -n hw.logicalcpu`

## Reinstallation on Mac

### [Update project and remove old installation](https://github.com/CMU-Perceptual-Computing-Lab/openpose/blob/master/doc/installation.md#reinstallation)

1) git pull origin master
2) cd build/
3) make uninstall
4) rm -rf build/*
5) In CMake GUI, click on File -> Delete Cache

## Installing Python version

cd build/python
sudo make install

pip install opencv-python-headless

vim ~/.zshrc
export PYTHONPATH=/path/to/openpose/build/python

(export PYTHONPATH="/Users/allarviinamae/EduWorkspace/openpose/build/python")
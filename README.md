# SLAM Project

### Installation
#### Dependency
```sh
sudo add-apt-repository ppa:borglab/gtsam-develop
sudo apt install libgtsam-dev libgtsam-unstable-dev
sudo apt install libboost-all-dev
```

#### Project
```sh
git clone https://github.com/trunc8/slam-project.git
mkdir build && cd build
cmake .. && cmake --build . && ../bin/main
```

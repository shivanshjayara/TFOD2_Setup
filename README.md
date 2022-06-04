# COMMANDS

## 1) For Local System

## download gitignore using curl
For windows: curl:
```bash
 https://raw.githubusercontent.com/c17hawke/general_template/main/.gitignore > .gitignore
```

For linux: 
```bash
curl https://raw.githubusercontent.com/c17hawke/general_template/main/.gitignore
```

## initialise enviornment file setup
For windows: 
```bash
curl https://raw.githubusercontent.com/c17hawke/general_template/main/init_setup.sh > init_setup.sh
```
Remove unnecessary commands

Installing particular file which is store in some folder of repository:
repository link then ".git" then "hash(#)" then "subdirectory='Directory Name'" i.e.
```bash
pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
```


All the above commands can be written inside the init_setup.sh file also.
To commit the changes in the github we need to initialise our gitub repository. We can also do it in init_setup.sh file'
Currently gitinit initialisation command is mentioned in the init_setup.sh file only.
Run command: 
```bash
bash init_setup.sh
```


## Tensorflow vwrification
* For GPU Check:
```bash
python -c "import tensorflow as tf; print(tf.config.list_physical_device('GPU'))"
```
* For CPU check:
```bash
python -c "import tensorflow as tf; print(tf.config.list_physical_device('CPU'))"
```
* If you dont specify 'CPU' or 'GPU' then it will show you both of them.


## Installation of Object detection API
```bash
mkdir TensorFlow && cd TensorFlow
```

## Clone the TensorFlow model folder here

```bash
This Will download tensorflow official directory
git clone https://github.com/tensorflow/models.git
```

## Removing .git folder from models directory (./TensorFlow/models/.git/)

* remove .git directory of the TensorFlow/models repository to avoid git conflict. 
* Do not delete outside .git directory. 
* Because that git folder will again create a model files into your git repository while pushing into github.


## Adding 'TensoFlow/models' repository path to the .gitignore file

* add models folder into .gitignore file i.e. "TensorFlow/models". This is because this folder is already available in the    internet so no need to upload it in our repository unecessary.
* This can be done either by cut paste or by following command as well 
  (You must be at the root directory. So change the directory if not):
```bash
echo "TensorFlow/models" >> .gitignore
```

## Protobuff installation

**By default Protoc is installed in google colab. Check it by this: !protoc --version**
* Like json and xml files, Google developers invented protobuffer. 
* Its a way of transferring the data. 
* It is more faster than those.
* It is used to serialized the structure data. It is Open source

Visit the link - https://github.com/protocolbuffers/protobuf/releases

* windows user - search for - protoc-3.20.1-win64.zip
* mac users - search for - protoc-3.20.1-osx-x86_64.zip
* linux users -
```bash
sudo apt install -y protobuf-compiler
```
* Unzip it into root folder (its folder name must be 'protoc') and add `<PATH TO protoc folder>/bin` into system enviornment   variable.
* Check protoc version by: protoc --version


## Converting all the protoc files in "research" folder into python files
* Change the path to "TensorFlow/models/research/". 
* Enter the command:

```bash
cd TensorFlow/models/research/
protoc object_detection/protos/*.proto --python_out=.
```
This way we can convert all the protos files into python file and kept all the files there only. You can check this via:
"TensorFlow/models/research/object_detection/protos/". Here you can see that all the protos file is now converted into python file.


## Add "protoc" directory in gitignore file

```bash
echo "protoc" >> .gitignore
```

## Installation of COCO API

* To do this we need to install cython. Cython is must. If it is not installed use this command:
```bash
pip install Cython
```

If installed already tyen check by using this command:
```bash
pip freeze | grep Cython
```
*use of 'grep' command: We know that 'pip freeze' command will show all the depencies(libraries) which are installed in our current environment. But what if we need to check just a single depedencies like 'terminado, it will give the line (with its version number) where 'terminado' is present.*

*It's a kind of search engine for depedencies*

* Download the COCO API:
  This must be install inside the 'research' folder.
```bash
pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
```


## Installation of Object Detection API

* Firstly copy the file from research folder. For that you need to be in research folder.

```bash
cp object_detection/packages/tf2/setup.py .
```
Above command will save setup.py file in research folder.

* Now you need to install this setup.py file

```bash
python -m pip install .
```
*If we get error while installing setup.py from above command, then check protoc upgrade*



## Test your installation

* Stay in 'research' folder.
```bash
python object_detection/builders/model_builder_tf2_test.py
```
*If there is no error then we can say we have install everything successfully*


## Run test sample

*  Create workspace/example_1 directory in project root
* Suppose you dont have parent directory like "workspace" the use "-p" command. So even if parent directory say "workspace" folder is not created, it will automatically create it and then it will create child folder (example_1)
* Make sure you are at the "TFOD2" folder i.e. root folder. If not do change it

  ```bash
  mkdir -p workspace/example_1
  ```
* Change directory to example 1.
  ```bash
  cd workspace/example_1
  ```


  ## Download Jupyter Notebook/ Python Notebook
* Download sample code in this directory using curl command. You can either download .py file or .ipynb notebook.

  1) For Local System- Jupyter Notebook (.ipynb)
  ```bash
  curl https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/2.2.0/_downloads/7f6123c070712ed53dd2521219dd011c/plot_object_detection_simple.ipynb > plot_object_detection_simple.ipynb
  ```

  2) For Google colab: Python file (.py)
  ```bash
  curl https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/2.2.0/_downloads/7dbbdbf71c3c2b2b95d1be96108eb15b/plot_object_detection_simple.py > plot_object_detection_simple.py
  ```

  *Run jupyter notebook in terminal. Sometime it is not able to find the kernel in jupyter notebook in VSC. So simply run the command in terminal*
  ```bash
  jupyter-notebook
  ```

* In the jupyter notebook the model which is used is "centernet_hg104_1024x1024_coco17_tpu-32". We can also change this pretrained model and can used any other model from "model zoo".
https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2_detection_zoo.md
 You can use any other model also like "SSD ResNet50 FPN 640X640 (RetinaNet50)".

 * In jupyter file there is a cell where it is written under comment section "Download and extract model". Here do remember, variable named 'MODEL_DATE' is a date of model creation. So for every pretrained model this date will be change. This you can get from the above repository link. And when you copy the link of the respective model you will get the date in its URL.




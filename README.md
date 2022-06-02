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
* Because that git folder will again create a model files into your grepository while pushing into github.


## Adding 'models' repository path to the .gitignore file

* add models folder into .gitignore file i.e. "TensorFlow/models". 
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
* Unzip it into root folder (its folder name must be 'proc_dir') and add `<PATH TO protoc folder>/bin` into system enviornment   variable.
* Check protoc version by: protoc --version


## Converting all the protoc files in "research" folder into python files
* Change the path to "TensorFlow/models/research/". 
* Enter the command:
```bash
protoc object_detection/protos/*.proto --python_out=.
```
This way we can convert all the protos files into python file and kept all the files there only. You can check this via:
"TensorFlow/models/research/object_detection/protos/". Here you can see that all the protos file is now converted into python file.
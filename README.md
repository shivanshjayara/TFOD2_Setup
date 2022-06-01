# COMMANDS

## download gitignore using curl
'''bash
For windows: curl https://raw.githubusercontent.com/c17hawke/general_template/main/.gitignore > .gitignore
For linux: curl https://raw.githubusercontent.com/c17hawke/general_template/main/.gitignore
'''

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

## create a Tensorflow directory
```bash
mkdir TensorFlow && cd TensorFlow
```

## Clone the TensorFlow model folder here

```bash
This Will download tensorflow official directory
git clone https://github.com/tensorflow/models.git
```

## Removing .git folder from models directory (./TensorFlow/models/.git/)

* remove .git directory of the TensorFlow/models. Do not delete outside .git directory. Because that git folder will again create a model files into your grepository while pushing into github.

* add models folder into .gitignore file i.e. TensorFlow/models. This can be done either by cut paste or by following command as well (You must be at the root directory. So change the directory):
```bash
echo "TensorFlow/models" >> .gitignore


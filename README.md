# Image classification as a service

> This is a actuallization for python3.9 and Tensorflow 2.x for 
> The original code is: https://github.com/marcobaturan/Image-classification-from-mess-folder-to-ordered-folder

I have a folder where I put all my cambridge holidays pictures... I would love to sort by topics my pictures of my holidays in Cambridge.

![messed_path](assets/image/cambridge_mess.png)

> In fact, these pictures are a groundtruth for computer vision algorithms from [University of Washington](http://imagedatabase.cs.washington.edu/groundtruth/)

Here is the expected result of the classification :

![messed_path](assets/image/sorted_path.png)

Oh dear god ! My computer analysed my pictures and recognized on its own all the churches of my cambridge holidays pictures and put them in the same folder :

![messed_path](assets/image/churches.png)

## Example
With this command line, I am now able to sort my pictures by topics as above
```
python3.9 messed_path_to_classify.py --out_path ./example/sorted ./example/cambridge
```
_____
## Installation
> The installation procedure has been tested on Ubuntu 16.04.

### Dependancies
This code needs python3 and TensorFlow to work.
- Install python3 :

```sh
sudo apt-get install python3.9
```

- Install TensorFlow :

	You need to first install pip3 plugin for managing the modules.
```sh
sudo apt-get install python3-pip python3-dev
```
Then, install Tensorflow :
```sh
sudo pip3 install --upgrade <link>
```
> Choose your link on [tensorflow documentation](https://www.tensorflow.org/install/install_linux#the_url_of_the_tensorflow_python_package).
>> Because of some difficulties to install TensorFlow with cuda and cudnn libraries, I used :  
>> ``` sudo pip3 install --upgrade https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-1.0.1-cp35-cp35m-linux_x86_64.whl ```


### Get the code
Once you have fill the requirements, you need to clone the repository :
```
git clone https://github.com/marcobaturan/Image-classification-from-mess-folder-to-ordered-folder
cd image-classifier-service
```

### Create an alias
The goal of creating an alias is to not care about the location of the repository but used it anywhere.

```
chmod +x ./alias.sh
./alias.sh
```
You could now use ```classify_path``` to call the script. Easier and faster.

### Create virtual environment

```
virtualenv env --python=python3.9

source env/bin/activate
```

### Install libraries from requirements

```
pip install -r requirements.txt
```

Now have fun and classify your folder !
_____
## Usage :
- Mainly use :
	```
	classify_path --out_path ./sorted ./path_to_classify/
	```
	where :
	- ```./sorted``` is the destination path
	- ```./path_to_classify/``` is the path where images are located


- Help :
	```
	classify_path -h
	```


## How does it work ?


![Schema](assets/diagram/how_does_it_work/diagram_how_does_it_work.png)
- Label image with deep learning
- Create folder corresponding to the Label
- Copy the image into the right path

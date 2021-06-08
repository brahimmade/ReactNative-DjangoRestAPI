# React-Native and Django Rest API

React Native and Django Rest Framework (Mongodb & SQL)

Rest Framework is located at django-program folder as the backend


Prerequisites
Before you begin, you should have a non-root user with sudo privileges available on your Ubuntu 20.04 server. To set this up, follow our Ubuntu 20.04 initial server setup guide.

Global Install from Packages
If you wish to install Django using the Ubuntu repositories, the process is very straightforward.

First, update your local package index with apt:

sudo apt update

Next, check which version of Python you have installed. 20.04 ships with Python 3.8 by default, which you can verify by typing:

python3 -V

You should see output like this:

Output
Python 3.8.2
Next, install Django:

sudo apt install python3-django

You can test that the installation was successful by typing:

django-admin --version

Output
2.2.12
This means that the software was successfully installed. You may also notice that the Django version is not the latest stable version. To learn more about how to use the software, skip ahead to learn how to create sample project.

Install with pip in a Virtual Environment
The most flexible way to install Django on your system is within a virtual environment. We will show you how to install Django in a virtual environment that we will create with the venv module, part of the standard Python 3 library. This tool allows you to create virtual Python environments and install Python packages without affecting the rest of the system. You can therefore select Python packages on a per-project basis, regardless of conflicts with other projects’ requirements.

Let’s begin by refreshing the local package index:

sudo apt update

Check the version of Python you have installed:

python3 -V

Output
Python 3.8.2
Next, let’s install pip and venv from the Ubuntu repositories:

sudo apt install python3-pip python3-venv

Now, whenever you start a new project, you can create a virtual environment for it. Start by creating and moving into a new project directory:

mkdir ~/newproject
cd ~/newproject

Next, create a virtual environment within the project directory using the python command that’s compatible with your version of Python. We will call our virtual environment my_env, but you should name it something descriptive:

python3 -m venv my_env

This will install standalone versions of Python and pip into an isolated directory structure within your project directory. A directory will be created with the name you select, which will hold the file hierarchy where your packages will be installed.

To install packages into the isolated environment, you must activate it by typing:

source my_env/bin/activate

Your prompt should change to reflect that you are now in your virtual environment. It will look something like (my_env)username@hostname:~/newproject$.

In your new environment, you can use pip to install Django. Regardless of your Python version, pip should just be called pip when you are in your virtual environment. Also note that you do not need to use sudo since you are installing locally:


Frontend with React native
-----------------------------


Application layout
We will begin by initialising a authapp/src directory and subdirectories that will contain all our application code and components.

mkdir -p ./src/components
Our application will consist of three screens:

1 - Login screen
2 - Registration screen
3 - Home screen (will serve as the logout screen)
For this we will be using the react-native-router-flux package, based on react navigation.

npm install --save react-native-router-flux
In order to issue the network requests, React Native provides access to the Fetch API out of the box, instead we will be using the axios package as it has some neater features out of the box, such as automatic transformation of JSON data.

npm install --save axios
Ok, we’re ready to start writing some React Native at this point.

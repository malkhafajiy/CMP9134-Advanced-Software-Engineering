# Create a Python library
This tutorial on creating a Python library! In this tutorial, we will go over the basics of creating a Python library, which is a collection of Python modules that can be reused in different projects. By the end of this tutorial, you will have a fully functional Python library that you can use in your own projects or share with others.

## Why create a library?
Creating a Python library can provide many benefits to developers and organizations, such as:

1. Reusability: Libraries allow developers to write code once and reuse it in multiple projects. This can save time and effort in development.

2. Scalability: Libraries can help with the scalability of projects, as they can be easily maintained and updated separately from the main project.

3. Standardisation: Libraries can provide a standard set of functionality for a particular task, making it easier for developers to collaborate and work on projects together.

4. Code Quality: Libraries can help promote code quality by enforcing best practices and reducing code duplication across projects.

5. Community Support: By publishing a library to the Python Package Index `(PyPI)`, other developers can easily find and use your library, and provide feedback or contribute to its development.


## How to create a Python library
#### Step 1: Create a directory in which you want to put your library
Follow the steps below to create a GitHub repository and then pull it to your local machine:

1. Create a new GitHub repository: Go to github.com and sign in to your account. Click on the "+" icon in the top right corner of the page and select "New repository". Give your repository a name (name it `mypythonlibrary`) and click "Create repository".

2. Clone the repository: Once your repository is created, copy the repository's URL. Open up your terminal or command prompt and navigate to the directory where you want to store your local copy of the repository. Then, use command: `git clone <repository URL>`. This will create a local copy of your repository on your machine.

3. Open VSCode: Launch Visual Studio Code from the applications menu or the command line. Open the project directory you have created (aka `mypythonlibrary`). To do this From the VSCode welcome screen, select "Open Folder" and navigate to the directory where your project is located. Alternatively, you can select "Open" from the File menu and choose the project directory.


#### Step 2: Create a virtual environment for your folder
When starting your project, it is always a good idea to create a virtual environment to encapsulate your project. A virtual environment consists of a certain Python version and some libraries.

Virtual environments prevent the issue of running into dependency issues later on. For example, in older projects you might have worked with older versions of the `numpy` library. Some old code, that once worked beautifully, might stop working once you update its version. Perhaps parts of `numpy` are no longer compatible with other parts of your program. Creating virtual environments prevents this. They are also useful in cases when you are collaborating with someone else, and you want to make sure that your application is working on their computer, and vice versa.

Go ahead and create a virtual environment by following these steps:

1. open the terminal in VSCode by selecting "Terminal" from the View menu.

2. Set up a Python virtual environment using this command `python3 -m venv venv`. This will create a new virtual environment in a folder named "venv".

3. Activate the virtual environment using this command `venv\Scripts\activate` on Windows, (`venv/bin/activate` on macOS or Linux). You should see the name of your virtual environment in the command prompt.

In your environment, make sure you have `pip` installed `wheel`, `setuptools` and `twine`. We will need them for later to build our Python library.
> pip install wheel

> pip install setuptools

> pip install twine



#### Step 3: Create a folder structure
In VSCode, your folder `mypythonlibrary` (or whatever name you have given). It should look something like this:
```
📦mypythonlibrary
 ┣ 📂mypythonlib
 ┃ ┣ 📜myfunctions.py
 ┃ ┗ 📜__init__.py
 ┣ 📂tests
 ┃ ┣ 📜test_myfunctions.py
 ┃ ┗ 📜__init__.py
 ┣ 📂venv
 ┣ 📜README.md
 ┗ 📜setup.py
```

You now can start adding folders and files to your project. You can do this either through the command prompt or in VSCode itself directly.

1. Create an empty file called `setup.py`. This is one of the most important files when creating a Python library!

2. Create an empty file called `README.md`. This is the place where you can write markdown to describe the contents of your library for other users.

3. Create a folder called `mypythonlib`, or whatever you want your Python library to be called when you pip install it. (The name should be unique on pip if you want to publish it later.)

4. Create an empty file inside `mypythonlib` that is called `__init__.py`. Basically, any folder that has an `__init__.py` file in it, will be included in the library when we build it. Most of the time, you can leave the `__init__.py` files empty. Upon import, the code within `__init__.py` gets executed, so it should contain only the minimal amount of code that is needed to be able to run your project. For now, we will leave them as is.

4. Also, in the same folder, create a file called `myfunctions.py`.

5. And, finally, create a folder `tests` in your root folder. Inside, create an empty `__init__.py` file and an empty `test_myfunctions.py`.



#### Step 4: Create content for your library
Now you can write functions inside your library, you can place them in the `myfunctions.py` file. 

In this tutorial, we will create a library to get the distance between two GPS points using Haversine formula. 

```
The Haversine formula is a mathematical formula used to calculate the distance between two points on the surface of a sphere, such as the Earth. The formula takes into account the curvature of the sphere to provide more accurate results than other distance calculation methods that assume a flat surface. The Haversine formula is defined as follows:

$a = sin^2(dLat/2) + cos(lat1) * cos(lat2) * sin^2(dLon/2)$
$c = 2 * atan2( √a, √(1−a) )$
$d = R * c$

Where:
- d is the distance between the two points in kilometers
- R is the radius of the Earth (mean radius = 6,371km)
- lat1 and lat2 are the latitude of point 1 and point 2, respectively, in radians
- dLat is the difference in latitude between the two points in radians
- dLon is the difference in longitude between the two points in radians

The Haversine formula is commonly used in GPS systems and location-based applications to calculate the distance between two points on the Earth's surface. It is also used in aviation and navigation.
```


example, copy the haversine function in your file:


#### Step 5: Build your library



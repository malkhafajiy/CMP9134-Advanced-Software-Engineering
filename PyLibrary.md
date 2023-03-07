# Create Python library
This tutorial on creating a Python library! In this tutorial, we will go over the basics of creating a Python library, which is a collection of Python modules that can be reused in different projects. By the end of this tutorial, you will have a fully functional Python library that you can use in your own projects or share with others.

## Why create a library?
Creating a Python library can provide many benefits to developers and organizations, such as:

1. Reusability: Libraries allow developers to write code once and reuse it in multiple projects. This can save time and effort in development.

2. Scalability: Libraries can help with the scalability of projects, as they can be easily maintained and updated separately from the main project.

3. Standardisation: Libraries can provide a standard set of functionality for a particular task, making it easier for developers to collaborate and work on projects together.

4. Code Quality: Libraries can help promote code quality by enforcing best practices and reducing code duplication across projects.

5. Community Support: By publishing a library to the Python Package Index `(PyPI)`, other developers can easily find and use your library, and provide feedback or contribute to its development.


## How to create a Python library
### Step 1: Create a directory in which you want to put your library
Follow the steps below to create a GitHub repository and then pull it to your local machine:

1. Create a new GitHub repository: Go to github.com and sign in to your account. Click on the "+" icon in the top right corner of the page and select "New repository". Give your repository a name (name it `mypythonlibrary`) and click "Create repository".

2. Clone the repository: Once your repository is created, copy the repository's URL. Open up your terminal or command prompt and navigate to the directory where you want to store your local copy of the repository. Then, use command: `git clone <repository URL>`. This will create a local copy of your repository on your machine.

3. Open VSCode: Launch Visual Studio Code from the applications menu or the command line. Open the project directory you have created (aka `mypythonlibrary`). To do this From the VSCode welcome screen, select "Open Folder" and navigate to the directory where your project is located. Alternatively, you can select "Open" from the File menu and choose the project directory.

---
***
___
### Step 2: Create a virtual environment for your folder
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



### Step 3: Create a folder structure
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



### Step 4: Create content for your library
Now you can write functions inside your library, you can place them in the `myfunctions.py` file. 

In this tutorial, we will create a library to get the distance between two GPS points using Haversine formula. 


> The Haversine formula is a mathematical formula used to calculate the distance between two points on the surface of a sphere, such as the Earth. The formula takes into account the curvature of the sphere to provide more accurate results than other distance calculation methods that assume a flat surface. The Haversine formula is commonly used in GPS systems and location-based applications to calculate the distance between two points on the Earth's surface. It is also used in aviation and navigation.

The Haversine formula is defined as follows:
```
$a = sin^2(dLat/2) + cos(lat1) * cos(lat2) * sin^2(dLon/2)$
$c = 2 * atan2( √a, √(1−a) )$
$d = R * c$
```
Where:
- `d` is the distance between the two points in kilometers
- `R` is the radius of the Earth (mean radius = `6,371km`)
- `lat1` and `lat2` are the latitude of point 1 and point 2, respectively, in radians
- `dLat` is the difference in latitude between the two points in radians
- `dLon` is the difference in longitude between the two points in radians

> It is a good idea to have the Haversine formula as a library, isn't it? By creating a library, you can package the Haversine formula into a reusable and modular component that can be used by other developers in their projects. This saves them the effort of having to implement the formula themselves, which can be time-consuming and error-prone.

In the `myfunctions.py` file, wrtie the following python code for Haversine formula. The `haversine` function in the code will return the distance in kilometers between two latitude and longitude points. 

```
from math import radians, cos, sin, asin, sqrt

def haversine(lon1, lat1, lon2, lat2):
    """
    Calculate the great circle distance in kilometers between two points 
    on the earth (specified in decimal degrees)
    """
    # convert decimal degrees to radians 
    lon1, lat1, lon2, lat2 = map(radians, [lon1, lat1, lon2, lat2])

    # haversine formula 
    dlon = lon2 - lon1 
    dlat = lat2 - lat1 
    a = sin(dlat/2)**2 + cos(lat1) * cos(lat2) * sin(dlon/2)**2
    c = 2 * asin(sqrt(a)) 
    r = 6371 # Radius of earth in kilometers. Use 3956 for miles. Determines return value units.
    return c * r
```

#### Write tests for your library
Whenever you write any code, it is highly encouraged to also write tests for this code. For testing with Python you can use the libraries `pytest` and `pytest-runner`. Install the library in your virtual environment:

> pip install pytest

> pip install pytest-runner

Let’s create a small test for the `haversine` function. Copy the following and place it inside the `test_myfunctions.py` file:

```
from mypythonlib import myfunctions
def test_haversine():
    assert myfunctions.haversine(52.370216, 4.895168, 52.520008,
    13.404954) == 945793.4375088713
```

Now let’s create a `setup.py` file, that will help us to build the library. A limited version of `setup.py` will look something like this:

```
from setuptools import find_packages, setup
setup(
    name='mypythonlib',
    packages=find_packages(),
    version='0.1.0',
    description='My first Python library',
    author='Me',
    license='MIT',
)
```
The name variable in setup holds whatever name you want your package wheel file to have. To make it easy, we will gave it the same name as the folder `mypythonlibrary`.

#### Set the packages you would like to create
While in principle you could use `find_packages()` without any arguments, this can potentially result in unwanted packages to be included. This can happen, for example, if you included an `__init__.py` in your `tests` directory (which we did). Alternatively, you can also use the exclude argument to explicitly prevent the inclusion of tests in the package, but this is slightly less robust. Let’s change it to the following:

```
from setuptools import find_packages, setup
setup(
    name='mypythonlib',
    packages=find_packages(include=['mypythonlib']),
    version='0.1.0',
    description='My first Python library',
    author='Me',
    license='MIT',
)
```
#### Set the requirements your library needs
Note that pip does not use `requirements.yml` / `requirements.txt` when your project is installed as a dependency by others. Generally, for that, you will have to specify dependencies in the `install_requires` and `tests_require` arguments in your `setup.py` file.

> `Install_requires` should be limited to the list of packages that are absolutely needed. This is because you do not want to make users install unnecessary packages. Also note that you do not need to list packages that are part of the standard Python library. Since we have only defined the haversine function so far and it only uses the `math` library (which is always available in Python), we can leave this argument empty.

You remember we installed the `pytest` library before. Of course, you do not want to add `pytest` to your dependencies in `install_requires`: it isn’t required by the users of your package. In order to have it installed automatically only when you run tests you can add the following to your `setup.py`:
```
from setuptools import find_packages, setup
setup(
    name='mypythonlib',
    packages=find_packages(include=['mypythonlib']),
    version='0.1.0',
    description='My first Python library',
    author='Me',
    license='MIT',
    install_requires=[],
    setup_requires=['pytest-runner'],
    tests_require=['pytest'],
    test_suite='tests',
)
```

> To execute all tests stored in the ‘tests’ folder, you can use `python setup.py pytest`. 


### Step 5: Build your library
Now that all the content is there, we want to build our library. In your command prompt, run `python setup.py bdist_wheel`.
Your wheel file is stored in the “dist” folder that is now created. 

> Remember to save your solution on your git repository.

You can install your library by using `pip install /path-to/wheelfile.whl`.

Once you have installed your Python library in a project, you can import it using:
```
import mypythonlib
from mypythonlib import myfunctions
```

> Note that you could also publish your library to an internal file system on intranet at your workplace, or to the official PyPI repository and install it from there.






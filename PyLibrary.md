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

2. Set up a Python virtual environment using this command `python3 -m venv venv`. This will create a new virtual environment in a folder named "env".

3. Activate the virtual environment using this command `source venv\Scripts\activate` on Windows, (`source venv/bin/activate` on macOS or Linux). You should see the name of your virtual environment in the command prompt.

In your environment, make sure you have `pip` installed `wheel`, `setuptools` and `twine`. We will need them for later to build our Python library.
> pip install wheel

> pip install setuptools

> pip install twine



#### Step 3: Create a folder structure



#### Step 4: Create content for your library

#### Step 5: Build your library



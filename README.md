# About

This is a project for Code Louisville's Data Analysis Course - May 2023 .


# Overview

  ![LFPL](https://www.arcgis.com/sharing/rest/content/items/372216992aea4b2cb5b02837d7a48eaf/info/thumbnail/thumbnail1659543230768.png?w=800)

For this project, we'll use data from the [Louisville Free Public Library](https://data.louisvilleky.gov/datasets/louisville-metro-ky-library-collection-inventory/about), specifically the books dataset. 

Some analysis will be performed with the data, and will use API calls to fill out part of the missing data.
  

# Running the Program

You will need Python 3 to run this code. The scripts were tested with Python 3.11.6. If you need to download or update Python, go to [www.python.org](www.python.org). If you are in a Windows 10 or 11 environment, you can  [Download Python from Microsoft Store](https://apps.microsoft.com/detail/python-3-11/9NRWMJP3717K?hl=en-US).

You will need to use Jupyter notebooks too. You can download it [here](https://jupyter.org/install), use [Visual Studio Code](https://code.visualstudio.com/), or the environment of your choice.

The following is a guide to running the project files locally. Further instructions can be found on [GitHub](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository).
 
1.  Fork the [repository.](https://github.com/lcabrp/LFPL_Data) 
2.  Clone the repository to your Github account.
3.  Access the repository from your command line or preferred terminal software.
4.  Install a virtual environment. The command in Gitbash is python -m venv venv.
5.  Activate the virtual environment. The command in Gitbash is source venv/scripts/activate. On Unix like systems use source venv/bin/activate.
6.  Install the  requirements.txt file to install necessary packages by running pip install requirements.txt.

There are 2 jupyter notebooks on the repo. On the first one, analysis.ipynb, the data preparation takes place.

On the second one, visuals.ipynb, is where the diagrams and graphs are created.

# Code Louisville Requirements

The following criteria have been met with this project:

1. Loading data.

  A csv file will be loaded into a Pandas dataframe. Some data cleaning is performed on the original dataframe. Using  APIs, a second csv file is created to enrich the original data source.

2. Clean and operate on the data while combining them.

  The two datasets will be merge to enrich the original one.

3. Visualize / Present your data

   Matplotlib and seaborn are used to visualize the data.

5. Best practices

   Virtual environment used.

7. Every step of the process is documented in the Jupyter notebooks.


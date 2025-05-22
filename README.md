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
    *   **Note**: The `requirements.txt` file in this project was initially UTF-16 encoded and has been corrected to UTF-8 for compatibility.

There are 2 jupyter notebooks on the repo. 
- On the first one, `analysis.ipynb`, the data preparation takes place.
- On the second one, `visuals.ipynb`, is where the diagrams and graphs are created.

# Code Louisville Requirements

The following criteria have been met with this project:

1. Loading data.

  - A csv file is loaded into a Pandas dataframe from the LFPL Open Data website.
  - Initial data cleaning is performed on the original dataframe. This includes:
    - Filtering out non-book items (e.g., items with "Laptop" as title).
    - Removing irrelevant item collections (e.g., 'Listening Device', 'Magazines and Newspaper', 'Adult DVD').
    - Handling missing `Title` values by dropping rows where the title is not available.
  - Using APIs (OpenLibrary and Google Books), a second dataset (`openlib_data.csv` and subsequently `book_info_updated.csv`) is created to enrich the original data source, specifically for missing `Author` and `ISBN` information.
  - Intermediate and final cleaned/enriched datasets are saved as compressed CSV files (`lfpl_books.csv.gz`, `lfpl_new.csv.gz`).

2. Clean and operate on the data while combining them.

  - The `ISBN` column is converted to a string type, and 'nan' string values are replaced with empty strings for consistency.
  - The original dataset is merged with the data obtained from APIs to fill in missing `Author` and `ISBN` values.
  - API functions (`get_open_library_data`, `get_google_books_data`) in `analysis.ipynb` were refactored for robust error handling (network issues, JSON decoding, missing keys, and API rate limits with retries).
  - Configuration variables for file paths and API URLs were added to `analysis.ipynb` for better maintainability.

3. Visualize / Present your data

   - Matplotlib and seaborn are used in `visuals.ipynb` to visualize the data.
   - Visualizations include:
     - Distribution of publication years (histogram and bar chart of top 5 years), with filtering for erroneous year data.
     - Average item prices by item collection (bar chart).
     - Distribution of book counts by library location (pie chart with grouping for small slices and horizontal bar plot).
   - These visualizations help in understanding the library's collection composition, age, pricing structure, and distribution across branches.
   - Explanatory markdown cells were added to `visuals.ipynb` to introduce the notebook, clarify data filtering steps, interpret each plot, and suggest further visualization ideas.

5. Best practices

   - Virtual environment used.
   - Code includes error handling, particularly for API calls.
   - Configuration variables are used for paths and URLs.

7. Every step of the process is documented in the Jupyter notebooks.
   - Markdown cells were added to `analysis.ipynb` and `visuals.ipynb` to explain data processing steps, API call efficiency, and visualization insights.

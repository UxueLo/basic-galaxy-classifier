# Galaxy Classifier
This is a basic Machine Learning project, designed as a first-time introduction to the field. The goal of the project is to build a model capable of classifying galaxies into two distinct morphological categories: **Elliptical and Spiral**.

## Dataset
Originally, the project aimed to use a single dataset containing both physical measurements and morphological labels. Since as I wasn't able to find any appropiate dataset, I decided to combine two different datasets and put them together then. Both datasets are available in the repository. The features used in the projec are:
* **'ra', 'dec'**: This coordinates are used to represent the celestial location of a galaxy. Their abbrevations come from Right Ascension and Declination. They are crucial  for the project because they serve as a unique identifiers of galaxies to merge the datasets.
* **'u', 'g', 'r', 'i', 'z'**: This features correspond to the SDSS Photometric filter system. In astrophysics, the wavelength of electromagnetic radiation defines the light's properties. These filters measure light across different bands (from Ultraviolet to Near-Infrared). This features are used to determine the a galaxy's age and star formation rate, calculating *'Color Indices'* (u-g, g-r ...).
* **'p_el', 'p_cs**: This features are the probability of a galaxy being elliptical and spiral.
* **'spiral', 'elliptical'**: These are the binary labels used for Supervised Learning, indicating the final classification of each galaxy.

## Data Processing
To trains the model it's essential to clean, select and adapt the data. In this project several changes were needed in the datasets:
* **Column Names:** The 'ra' and 'dec' columns were written differently: one as upper case and the other as lower case. Hence, both ere changed to upper case.
* **Types:** The raw data for RA and DEC was in sexagesimal format (HH:MM:SS) in one of the datasets. To solve these into degrees, some converting functions were needed.
    * In the RA column is crucial to know that 1 hour is equivalen to 15 degrees.
    * In the DEC column, otherwise, the main formula is: sign* (|d|+m/60+s/3600)
* **Merge:** After rounding the two identifiers into 4 decimals, I succesfully merged both of the datasets and obtain more than *3000* galaxies.
* **Data Cleaning:** To ensure more quality training, I filtered out all the "Uncertain" classifications, so that only elliptical and spiral remain. Moreover, I removed the columns I wasn't interested in from the datasets.

## Packages
To carry out this project some packages were essential:
* *Pandas*: This python package is a commonly used in data science and artificial intelligence developing, as it provides high-performance, easy-to-use data structures. Pandas have two main data structures: Series (1 dimension), DataFrames (2 dimension). This last datastructure will be constantly used in this project.



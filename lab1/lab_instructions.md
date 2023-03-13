# Lab 1 Instructions
60 points total for Lab 1

Due before March 25, 2023 at 11:00 am

## Part 1: Use [free and open-source software](https://en.wikipedia.org/wiki/Free_and_open-source_software) to assess burn scars with satellite imagery 
45 points total for Part 1

> Note: This tutorial was originally developed by Esri's Learn Team. You can find the official maintained version at [this location](https://learn.arcgis.com/en/projects/assess-burn-scars-with-satellite-imagery/). Additionally you can find other tutorials in the [tutorial gallery](https://learn.arcgis.com/en/gallery/).

#### Prerequisites
* Google account with access to Drive
    * This lab uses Google Colaboratory, a free Google Drive-based Python Jupyter Notebook environment.
* Willingness to try `rasterio`, a free and open source Python library to read and write raster datasets
    * [rasterio GitHub](https://github.com/rasterio/rasterio)
    * [rasterio Docs](https://rasterio.readthedocs.io/en/stable/)

#### Overview
* Compare band combinations
* Calculate the burn index
* Share your results

#### Compare band combinations
##### Download the data
1. Sign into your Google account
2. Open [Google Colaboratory](https://colab.research.google.com/)
3. Select "New notebook" then wait for the Notebook user interface to update.
4. Download the [Montana Fires Project Package](https://www.arcgis.com/sharing/rest/content/items/1bc2bc1305b447fa939b937a8867114f/data) into Google Colaboratory by copy+pasting this command into Colaboratory then pressing the "play" button to run the command. Shift+Enter also works as a shortcut to run the active cell.
    ``` bash
    !wget -c https://www.arcgis.com/sharing/rest/content/items/1bc2bc1305b447fa939b937a8867114f/data -O MontanaFires
    ```

5. Download `dtrx` for easier data unzipping, use `dtx` to unzip the downloaded file (`Montana_Fires.ppkx`), delete the zipped data you don't need, move raster_data to a more convenient location, then run the command to list files in `raster_data/`
    ``` bash
    !pip install dtrx
    !dtrx MontanaFires
    !rm MontanaFires
    !mv MontanaFires.1/commondata/raster_data raster_data
    !ls raster_data
    ```


##### Enhance the imagery
1. Install `rasterio` and check the version installed
    ``` bash
    !sudo apt-get install python-numpy gdal-bin libgdal-dev
    !pip install rasterio
    !rio --version
    ```

##### View various band combinations
1. Display information about the 2014 data
    ``` bash
    !rio info raster_data/G_2014.tif --indent 2 --verbose
    ```

##### Create a custom band combination

#### Calculate the burn index
##### Calculate the Normalized Burn Ratio

##### Determine change in NBR

#### Share your results
##### Upload results to GitHub

## Part 2: Literature search
15 points total for Part 2

Use https://scholar.google.com/ to find three peer-reviewed articles about the remote sensing of burn scars. 

Search with terms like "multispectral remote sensing burn scars", but you can replace the "multispectral" in your Google Scholar search with something like "LiDAR", "hyperspectral", or "UAV", etc. Reach out to the instructor if you need help with your search.

For your deliverable, please write a 2-4 sentence summary (paraphrase in your own words) about each article you select then compile your results into JSON format and follow `submission_instructions.md` to submit your findings. Please use `part_2_submission_template.json` as the formatting template for your submission.

> Tip: Write you summaries in a different text editor (like Word, Docs, etc.) then copy the text into your JSON file. Make sure not to add line breaks.

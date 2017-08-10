# Orchestration of the analytics workflow in IBM Data Science Experience(DSX) using a custom web user-interface built with Node-RED (Work in Progress)

In this developer journey we will use Node-RED to render the web user-interface and invoke the analytics workflows in Jupyter notebooks on IBM Data Science experience(DSX).

When the reader has completed this journey, they will understand how to:

* Create and run a Jupyter notebook in DSX.
* Use DSX Object Storage to access data and configuration files.
* Use Python Pandas to derive insights on the data.
*	Develop a web user interface using Node-RED. 
*	Triggering an analytics workflow from the UI and orchestration of the flow using websockets on Node-RED.


The intended audience for this journey are developers who want to develop an end to end analytics solution quickly with a web user interface. The Data Science Experience(DSX) is primarily used by Data Scientists for developing the analytics code. By using Node-RED, we can quickly develop a user-interface and trigger the DSX analytics code from the uer-interface. 

![](doc/source/images/architecture.png)

## Included components

* [Node-RED](https://console.bluemix.net/catalog/starters/node-red-starter): Node-RED is a programming tool for wiring together hardware devices, APIs and online services in new and interesting ways.

* [IBM Data Science Experience](https://www.ibm.com/bs-en/marketplace/data-science-experience): Analyze data using RStudio, Jupyter, and Python in a configured, collaborative environment that includes IBM value-adds, such as managed Spark.

* [Bluemix Object Storage](https://console.ng.bluemix.net/catalog/services/object-storage/?cm_sp=dw-bluemix-_-code-_-devcenter): A Bluemix service that provides an unstructured cloud data store to build and deliver cost effective apps and services with high reliability and fast speed to market.

## Featured technologies

* [Jupyter Notebooks](http://jupyter.org/): An open-source web application that allows you to create and share documents that contain live code, equations, visualizations and explanatory text.


# Watch the Video

[![](http://img.youtube.com/vi/kp8dcM9AKrA/0.jpg)](https://www.youtube.com/watch?v=kp8dcM9AKrA)

# Steps

Follow these steps to setup and run this developer journey. The steps are
described in detail below.

1. [Sign up for the Data Science Experience](#1-sign-up-for-the-data-science-experience)
1. [Create Bluemix services](#2-create-bluemix-services)
1. [Import the Node-RED flow](#3-import-the-node-red-flow)

1. [Create the notebook](#3-create-the-notebook)
1. [Add the data and configuraton file](#4-add-the-data-and-configuration-file)
1. [Update the notebook with service credentials](#5-update-the-notebook-with-service-credentials)
1. [Run the notebook](#6-run-the-notebook)
1. [Download the results](#7-download-the-results)
1. [Analyze the results](#8-analyze-the-results)

## 1. Sign up for the Data Science Experience

Sign up for IBM's [Data Science Experience](http://datascience.ibm.com/). By signing up for the Data Science Experience, two services: ``DSX-Spark`` and ``DSX-ObjectStore`` will be created in your Bluemix account.

## 2. Create Bluemix services

Create the following Bluemix service by following the link to use the Bluemix UI and create it.

  * [**Node-RED Starter**](https://console.bluemix.net/catalog/starters/node-red-starter)
  
  ![](doc/source/images/bluemix_service_nlu.png)
  * Click on `Visit App URL` to launch the Node-RED editor
  * Click on Next
  * Enter a username and password to secure the Node-RED editor. Click on Next
  * Click on Next
  * Click on Finish
  * Click on Go to your Node-RED flow editor  
  
## 3. Import the Node-RED flow
The flow json for Node-RED can be found under `node-red-flow` directory. 
* Download the `orchestrate_dsx_workflow.json`
* Open the file with a text editor and copy the contents to Clipboard
* On the Node-RED flow editor, click the Menu and select Import -> Clipboard and paste the contents

## 4. Configure the Node-RED flow

## 5. Create the notebook

Use the menu on the left to select `My Projects` and then `Default Project`.
Click on `Add notebooks` (upper right) to create a notebook.

* Select the `From URL` tab.
* Enter a name for the notebook.
* Optionally, enter a description for the notebook.
* Enter this Notebook URL: https://github.com/IBM/watson-document-classifier/blob/master/notebooks/watson_document_classifier.ipynb
* Click the `Create Notebook` button.

![](doc/source/images/create_notebook_from_url.png)

## 6. Add the data 

#### Add the data to the notebook
Use `Find and Add Data` (look for the `10/01` icon)
and its `Files` tab. From there you can click
`browse` and add data files from your computer.

> Note: The data files in the `data` directory - `olympics.csv` and `dictionary.csv` have been downloaded from https://www.kaggle.com/the-guardian/olympic-games. Please visit the site for the terms and conditions for usage of the data.



![](doc/source/images/add_file.png)

#### Fix-up variable names
Once the files have been uploaded into ``DSX-ObjectStore`` you need to update the variables that refer to the data and configuration files in the Jupyter Notebook.

In the notebook, update the global variables the in cell following `2.3 Global Variables` section.

Replace the `sampleTextFileName` with the name of the data file and `sampleConfigFileName` with the configuration file name.

![](doc/source/images/update_variables.png)

## 7. Update the notebook with service credentials

#### Add the Object Storage credentials to the notebook
Select the cell below `2.2 Add your service credentials for Object Storage` section in the notebook to update
the credentials for Object Store. 

Use `Find and Add Data` (look for the `10/01` icon) and its `Files` tab. You should see the file names uploaded earlier. Make sure your active cell is the empty one created earlier. Select `Insert to code` (below your file name). Click `Insert Crendentials` from drop down menu.

![](doc/source/images/objectstorage_credentials.png)

#### Update the websocket URL


## 8. Run the notebook

When a notebook is executed, what is actually happening is that each code cell in
the notebook is executed, in order, from top to bottom.

Each code cell is selectable and is preceded by a tag in the left margin. The tag
format is `In [x]:`. Depending on the state of the notebook, the `x` can be:

* A blank, this indicates that the cell has never been executed.
* A number, this number represents the relative order this code step was executed.
* A `*`, this indicates that the cell is currently executing.

There are several ways to execute the code cells in your notebook:

* One cell at a time.
  * Select the cell, and then press the `Play` button in the toolbar.
* Batch mode, in sequential order.
  * From the `Cell` menu bar, there are several options available. For example, you
    can `Run All` cells in your notebook, or you can `Run All Below`, that will
    start executing from the first cell under the currently selected cell, and then
    continue executing all cells that follow.
* At a scheduled time.
  * Press the `Schedule` button located in the top right section of your notebook
    panel. Here you can schedule your notebook to be executed once at some future
    time, or repeatedly at your specified interval.

## 9. Open the UI web page



## 10. Analyze the results


# Troubleshooting

[See DEBUGGING.md.](DEBUGGING.md)

# License

[Apache 2.0](LICENSE)


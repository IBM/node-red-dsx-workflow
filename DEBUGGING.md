Troubleshooting
===============

Jupyter Notebooks
-----------------

* Make sure the pip install ran correctly. You might need to restart the
  kernel and run the cells from the top after the pip install runs the first
  time.
* Many of the cells rely on variables that are set in earlier cells. Some of
  these are cleared in later cells. Start over at the top when troubleshooting.
* Many of the cells rely on service credentials from Bluemix that are set in
  earlier cells. Make sure to add your service credentials correctly.  
* If there is an error in the `4.1 Prepare data section`, there could be a change in the column names or format of the data files downloaded from [kaggle](https://www.kaggle.com/the-guardian/olympic-games). Please change the column names and format of the files downloaded from [kaggle](https://www.kaggle.com/the-guardian/olympic-games) to match the format below.

    olympics.csv (renamed from summer.csv file downloaded from kaggle)      
    
    |Year|City|Sport|Discipline|Athlete|Country|Gender|Event|Medal|
    |----|----|-----|-----------|------|-------|------|-----|-----|
    |1896|Athens|Aquatics|Swimming|HAJOS, Alfred|HUN|Men|100M Freestyle|Gold|
    |1896|Athens|Aquatics|Swimming|HERSCHMANN, Otto|AUT|Men|100M Freestyle|Silver|

    dictionary.csv
    
    |Country|Code|Population|GDP per Capita|
    |-------|----|----------|--------------|
    |Afghanistan|AFG|32526562|594.3230812|
    |Albania|ALB|2889167|3945.217582|


* If the Start Websocket client step throws an error as shown below, please refer to the step `Update the websocket URL in the notebook` in Section 8 of the documentation.

          --- response header ---
          HTTP/1.1 500 Error 
          X-Backside-Transport: FAIL FAIL
          Content-Type: text/xml
          Connection: close

Node-RED
--------

* Make sure that the websocket URL has been updated with the NODERED_BASE_URL in the HTML code. Refer to section `5. Update the websocket URL in HTML code` in the documentation for details.

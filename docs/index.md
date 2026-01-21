---
title: "Downloading SDA data from CHASS into STATA"
layout: "home"
description: ""
permalink: "/"  #! Remove this if not the homepage
---

# Downloading SDA data from CHASS into STATA

This tutorial demonstrates how to load SDA data for use in Stata.

 

 

### **1\. In SDA**

Go to the [SDA website](https://sda.artsci.utoronto.ca/sdaweb/sda.htm) and select a survey of interest. If you are off campus, you will need to be on the VPN or use the following [link](https://login.library.utoronto.ca/index.php?url=https://sda.artsci.utoronto.ca/sdaweb/index.html).

![]({{ '/assets/images/01.PNG' | relative_url }})

 

![]({{ '/assets/images/02.PNG' | relative_url }})

It is advisable to run this procedure on a few selected variables the first time around in order to identify any errors easily.

![]({{ '/assets/images/03.PNG' | relative_url }})

 

![]({{ '/assets/images/04.PNG' | relative_url }})

 

 

**1\.1** Save the data file as data.txt, the Stata file as stata.txt, and the codebook file as codebook.txt

**1\.2** From file explorer, rename the Stata file as stata.do

 

### **2\. Start Stata**

**2\.1** Click on Window → Do\-file Editor → New Do\-file Editor

**2\.2** From the Do\-file Editor window, click on File → Open → Open → browse for stata.do file

**2\.3** If you scroll to the middle of the do\-file page, you will find the dictionary line.

![]({{ '/assets/images/06.PNG' | relative_url }})

 

### **3\. Start Notepad\+\+**

**3\.1** In the do\-file, from the dictionary line all the way to the bottom, cut and paste into a **new document** in Notepad\+\+ or another text editor and save as .dct (eg. dictionary.dct)

![]({{ '/assets/images/07.PNG' | relative_url }})

 

**3\.2** In the dictionary.dct file, replace Y with the full path in double quotes to your data file (e.g. "C:\\full path\\data.txt"). 

![]({{ '/assets/images/08.PNG' | relative_url }})

 

**3\.3** At the botom of the page, after the closing curly brackets (i.e, "}"), add a period (i.e, ".") **on a new final line**. Then save this file.

### **4\. Return to Stata**

**4\.1** In the do\-file, replace X with the full path to your .dct file (e.g. "C:\\full path\\dictionary.dct") and save it

![]({{ '/assets/images/09.PNG' | relative_url }})

**4\.2** In the do\-file, you will find a list of label definitions of variables starting with the command **label define** and ending with a **semi\-colon**. Unfortunately, the code may include decimal numbers label definitions. If you don't see any decimal numbers in this section, go on to the next step.

If this is the case, you need to delete from the label define until the semi\-colon for the variables that include decimal numbers. If you think you have deleted all of those decimal number label definitions, go on to the next step. If there are any that were not deleted, you will get an error message in the next step. In fact, the error message will help you identify the variable that needs to be deleted. You need to delete it from the label define section. Then type the following code **label drop \_all** in the command window. Then go on to the next step. You might have to go back and forth between step 4\.2 and step 4\.3 until you catch all the decimal number label definitions.

**4\.3** Highlight the code in the do\-file and click on execute (the play button). This step will generate your data set.

**4\.4** To view the data set, go to the View menu \> Data Editor \> Browse.

Once you have generated your data set, you can compare the expected number of observations and variables to those indicated on the CHASS files download page. The number of observations and variables can be found in the properties window of the Stata interface.

**4\.5** To save the data set as a Stata data file (.dta), go to the File menu \> Save as \> Browse to the folder \+ give the data file a name \> Click on Save.

To save the data set in a different file format such as Excel or CSV, go to the File menu \> Export  \> Select the file format and follow the instructions in the dialog.

 

If you need assistance, fill out the [support request form](https://mdl.library.utoronto.ca/research/help).

 

Technique: [Extracting data](/technique/extracting-data) \| Tools: [Stata](/tools/stata)**Date Created:** 2017\-05\-05**Updated:** 2022\-01\-18

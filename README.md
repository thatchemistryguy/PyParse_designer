
Welcome to PyParse_designer!
===================================

Authors: [Joe Mason](https://github.com/thatchemistryguy)


Description
--------------- 

This simple and lightweight tool is to facilitate the quick and easy creation of platemaps from high-throughput experimentation (HTE). 
Once created, these platemaps can be used with [PyParse](https://github.com/thatchemistryguy/PyParse), a python script which takes the data from the platemap to analyse UPLC-MS data 
and generate user-friendly outputs, including a standardised, machine-readable table that contains all information about that plate. 

In conjunction with one another, PyParse_designer and PyParse form an end-to-end workflow of plate design, analysis of data, long-term capture of the 
information generated.

By using this workflow, datasets containing everything from the ID of the catalyst in a particular well, to the temperature of the plate, to the 
peak percentage area of product observed, are created. 




Example Usage 
---------------

The tool is a lightweight HTML file - simply download the repository and load index.html in the browser. 

Choosing a plate size:
You can edit the plate size by selecting from four standardised options at the top of the screen. Once selected, the plate size will update immediately. 

Adding Reagents:

Select wells by clicking on them on the plate visualisation. You can also:
 - click-and-drag a selection of wells
 - Hold shift, and click on multiple wells in turn
 - Click either the letter/number for the row/column, to select all wells in that row or column respectively.
 - Click the top-left corner of the plate, to select or deselect all wells in one go.

Once you have selected the required wells, add a reagent by filling in the reagent name, the SMILES, the reagent ID, the amount of reagent in that well, 
and select the type of reagent from the dropdown menu. Now click "Add Compound to Selected Wells" to do so. 

You can also select any of the pre-filled reagents by typing the first part of their name in the "reagent name" field, and selecting the one you want. 
Note that the common abbreviations are typically used here, e.g. HATU, for the common amide coupling reagent. 

What's Currently in the Plate?

When you make any changes to the contents of the plate, you will see the table at the bottom of the screen update to reflect that change. By default it shows
a summary of the whole plate, but by clicking on a single well in the plate visualisation, you can see exactly what you've added to that well. 

From here, you can remove of any compound or plate parameter from the plate by selecting the wells you wish to change, and clicking the "Delete Definition" button. 

You can also highlight a selection of wells 

		
License
---------------

MIT Licence

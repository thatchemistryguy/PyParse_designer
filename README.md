
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

### Adding Reagents:

Select wells by clicking on them on the plate visualisation. You can also:
 - click-and-drag a selection of wells
 - Hold shift, and click on multiple wells in turn
 - Click either the letter/number for the row/column, to select all wells in that row or column respectively.
 - Click the top-left corner of the plate, to select or deselect all wells in one go.

Once you have selected the required wells, add a reagent by filling in the reagent name, the SMILES, the reagent ID, the amount of reagent in that well, 
and select the type of reagent from the dropdown menu. Now click "Add Compound to Selected Wells" to do so. 

You can also select any of the pre-filled reagents by typing the first part of their name in the "reagent name" field, and selecting the one you want. 
Note that the common abbreviations are typically used here, e.g. HATU, for the common amide coupling reagent. 

### What's Currently in the Plate?

When you make any changes to the contents of the plate, you will see the table at the bottom of the screen update to reflect that change. By default it shows
a summary of the whole plate, but by clicking on a single well in the plate visualisation, you can see exactly what you've added to that well. 

From here, you can remove of any compound or plate parameter from the plate by selecting the wells you wish to change, and clicking the "Delete Definition" button. 

You can also highlight a selection of wells in the plate at the top of the screen to view which parameters have been defined and delete if required. 

### Adding an End-User Plate Design:

End-user plate designs are pre-validated designs which contain a particular set of reagents or catalysts, usually in a 24-well format. These designs often come
with physical plates in the lab that already contain the requisite catalysts and are ready-to-go for the "end-user" to quickly add their staring materials and set the
experiment going.

To add an End-User plate design to your plate:
 - Select 24 wells in your plate
 - Select the plate design from the drop down list on the left-hand side
 - Click "Add End-User Plate Design"

An example of a Suzuki-Miyaura cross-coupling design is provided as an example. You can find out more about this plate design, and the advantages of end-user plates, by visiting the [blog post here](https://www.domainex.co.uk/news/high-throughput-experimentation-hte-approaches-domainex-advantages-end-user-plates). You'll find that two variations on this plate design can be added: 
 - the mL size, where 1 umol of catalyst is added to each well (for larger scale HTE plates)
 - the uL size, where just 0.25 umol of catalyst is added to each well

All of this information is customisable in the plate_templates.js file, where you can add your own commonly used plate designs by following the layout of the Suzuki example provided. 

### Adding a Plate Parameter

Plate parameters are exactly that, they're the same for the whole plate, and don't differ from one well to another. 

PyParse_designer allows the user to specify the temperature and reaction time, but also the irradiation power and wavelength for reactions where this is necessary. All of this is done using the fields and buttons on the left hand side, and you don't need to select any wells to do so. 

### Downloading Your Platemap

You can download your platemap by clicking the "Download CSV" button. This creates a .csv file and saves it to your downloads folder, ready for use in your analysis software 
and Electronic Lab Notebook. 

The headers of the .csv file are optimised for use in [PyParse](https://github.com/thatchemistryguy/PyParse), but these can be edited in the relevant section of index.html to match your preferred analytical software. 

### Reading a Platemap

You can load a platemap that was previously prepared in PyParse_designer by opening the .csv in a text-editor like Notepad, copying the contents, then pasting into the field 
that says "Paste .csv text here". Edit the plate size to match the 



		
License
---------------

MIT Licence

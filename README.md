
Welcome to PyParse_designer!
===================================

Authors: [Joe Mason](https://github.com/thatchemistryguy)


Description
--------------- 

This is a simple, lightweight and functional tool to facilitate the quick and easy creation of platemaps for high-throughput experimentation (HTE). 
Once created, these platemaps can be used with [PyParse](https://github.com/thatchemistryguy/PyParse), a python script which takes the data from the platemap to analyse UPLC-MS data and generate user-friendly outputs, including a standardised, machine-readable table that contains all information about that plate. 

In conjunction with one another, PyParse_designer and PyParse form an end-to-end workflow of plate design, analysis of data, and long-term capture of the 
information generated.

By using this workflow, datasets containing everything from the ID of the catalyst in a particular well, to the temperature of the plate, to the 
peak percentage area of product observed, are created. 

Workflow in a Nutshell:

1. PyParse_designer is used to define ***every*** parameter for ***every*** well in the plate
2. This platemap is then combined with the reaction UPLC-MS data in PyParse, which looks to assign peaks to analytes.
3. PyParse generates an [analytical table](#the-final-outputted-analytical-table), which includes information about both the inputs (catalyst amount, ID, temperature, etc) and the outputs (product percentage area,
   retention time observed, m/z values, etc)
4. The user uploads this [analytical table](#the-final-outputted-analytical-table) to a global data lake for long-term storage, for future interrogation, and to facilitate the creation of machine-learning models.


Example Usage 
---------------

The tool is a lightweight HTML file - simply download the repository and load index.html in the browser. 

Choosing a plate size:
You can edit the plate size by selecting from four standardised options at the top of the screen. Once selected, the plate size will update immediately. 

### Adding Reagents:

Select wells by clicking on them on the plate visualisation. You can also:
 - Click-and-drag a selection of wells
 - Hold the Ctrl key on the keyboard, and click on multiple wells in turn
 - Click either the letter/number for the row/column, to select all wells in that row or column respectively.
 - Click the top-left corner of the plate, to select or deselect all wells in one go.

Once you have selected the required wells, add a reagent by filling in the reagent name, the SMILES, the reagent ID, the amount of reagent in that well, 
and select the type of reagent from the dropdown menu. Now click "Add Compound to Selected Wells" to do so. 

You can also select any of the pre-filled reagents by typing the first part of their name in the "reagent name" field, and selecting the one you want. 
Note that the common abbreviations are typically used here, e.g. HATU, for the common amide coupling reagent. 

When you add a reagent, you'll notice that the number given in the wells you selected will increase by 1. The number in each well is an indication of how many
you have defined for that well so far, so you can get a quick idea of which wells might still be missing something. 
<p align="center">
	<img src="https://github.com/user-attachments/assets/095262e4-460b-44c1-bb5e-5eaa8a4a4104" width="700">
</p>

### What's Currently in the Plate?

When you make any changes to the contents of the plate, you will see the table at the bottom of the screen update to reflect that change. By default it shows
a summary of the whole plate, but by clicking on a single well in the plate visualisation, you can see exactly what you've added to that well. 

![View Contents of Well](https://github.com/user-attachments/assets/39af071e-9683-480a-8418-c79ed04ab54b)

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
<p align="center">
	<img src="https://github.com/user-attachments/assets/08c5c0e4-8907-4518-9a63-c608b6fccb02" width="500">
</p>

An example of a Suzuki-Miyaura cross-coupling design is provided as an example. You can find out more about this plate design, and the advantages of end-user plates, by visiting the [blog post here](https://www.domainex.co.uk/news/high-throughput-experimentation-hte-approaches-domainex-advantages-end-user-plates). You'll find that two variations on this plate design can be added: 
 - the mL size, where 1 umol of catalyst is added to each well (for larger scale HTE plates)
 - the uL size, where just 0.25 umol of catalyst is added to each well

All of this information is customisable in the plate_templates.js file, where you can add your own commonly used plate designs by following the layout of the Suzuki example provided. 

### Adding a Plate Parameter

Plate parameters are exactly that, they're the same for the whole plate, and don't differ from one well to another. 

PyParse_designer allows the user to specify the temperature and reaction time, but also the irradiation power and wavelength for reactions where this is necessary. All of this is done using the fields and buttons on the left hand side, and you don't need to select any wells to do so. 
<p align="center">
<img src="https://github.com/user-attachments/assets/4575523e-40c2-4fe6-b385-facde83e038e" width="500">
</p>

### Downloading Your Platemap

You can download your platemap by clicking the "Download CSV" button. This creates a .csv file and saves it to your downloads folder, ready for use in your analysis software 
and Electronic Lab Notebook. 

The headers of the .csv file are optimised for use in [PyParse](https://github.com/thatchemistryguy/PyParse), but these can be edited in the relevant section of index.html to match your preferred analytical software. 

### Uploading a Platemap

You can load a platemap that was previously downloaded from Parse_designer:
 - Open the .csv in a text-editor like Notepad
 - Copy the contents of the entire file (Ctrl-A, Ctrl-C)
 - Paste into the field in PyParse_designer that says "Paste .csv text here".
 - Edit the plate size to match the size of the plate you're importing
 - Click "Read from CSV Text"

The plate information will load and the table at the bottom of the screen will update to reflect the change. 

> [!WARNING]  
> Uploading a platemap will overwrite any parameters that have already been defined!


### Clear All Data

You can remove everything from a plate and start afresh by clicking the button "Clear All Data". Beware that this action cannot be undone!

You can also achieve the same effect by changing the plate size, which will also delete all parameters in the process. 

### Building Plates for Library Synthesis or Direct-to-Biology

When you're building a platemap for a library synthesis or Direct-to-Biology (i.e. there are a lot of different starting materials and products), it is recommended
that you first enumerate these compounds using your Electronic Lab Notebook to build a simple csv containing a list of starting materials and products, indexed by well. 

You can then edit this .csv so that headers for the SMILES structures, amounts and IDs of these starting materials match what is expected by PyParse_designer. Finally, import this .csv into PyParse_designer to add the remaining parameters like base, catalyst, temperature and time for each well, saving time overall. 

### The Final Outputted Analytical Table

For those who choose to use PyParse to analyse the UPLC-MS data with a platemap generated by PyParse_designer, the analytical table looks like this:

<p align="center">
	<img src="https://github.com/user-attachments/assets/7e5a17e6-d558-4da4-a69c-d2865590b30e" width="500">
</p>

The above example is just a small snippet of the analytical table generated - in general, a 24-well plate will create a table over 1000 rows long, reflecting the high level of detail this table contains for each well. 

The headers were designed such that new data types (e.g. crude NMR data) could be easily added without requiring modifications to the number of columns in the table/database. Any data type is brought in as a new row, which allows flexibility in the analysis conducted. 


### Notes on Nomenclature

You'll notice that all of the pre-defined reagents have been assigned a default type, i.e. potassium carbonate is listed as a base and APhos Pd G3 is listed as a catalyst. 
These two examples are likely not contentious, but others, such as HATU being described as a catalyst are perhaps more so. 

It was the intention when writing this lightweight tool to very broadly classify compounds by their typical usage, with the idea that a catalyst in this sense, simply "makes the reaction go". Following along these lines, a co-catalyst helps the catalyst, Solvent1 is the primary solvent, Solvent2 is the secondary solvent (often water), and the additive is "something else".

These classifications are of course not strictly correct from a chemist's point of view, but are a compromise based on the understanding that added more classifications would make the tool more cumbersome to use without solving the problem. It is important however that anyone reading the output understands these limitations, for example when building machine learning models. 

Acknowledgements
-----------------

This script makes use of JQuery-csv (included in src), a third part plugin published under the MIT licence and available here: https://github.com/evanplaice/jquery-csv.
		
License
---------------

MIT Licence

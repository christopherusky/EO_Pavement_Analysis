## Earth Observation Pavement Analysis Toolkit.

![image](https://github.com/user-attachments/assets/04a78093-f08b-4bd5-9685-153a16b6d2f4)

## eo_pavement_analysis

The Earth Observation Pavement Analysis is a QGOS 3.0+ plugin for the extraction of raster data representing unpaved roads. Once extracted the data set created is used to train a machine learning model for the assessment of unpaved roads in Low and Middle Income Countries, particulary in the Global South. The outcomes from this enable a low cost / cost effective way to maximise limited resouces in the maintenance of unpaved roads as vital arteries connecting people, goods and services. 

If you are looking for a method for preparing raster extracts, this could also be for you :) 


### Step 1. Create Layers. 

This creates the layers required for your project, these are:

  - Road Centre Lines - vector file for the road centre lines along which the sample grid will create the bounding boxes

  - Sample Grid - the layer in which for each class of road condition the bounding boxes are created

  - Source Raster - the virtual raster from which the sample grid will use each feature to clip the raster

  - Clipped Rasters - the resuling clipped rasters. 

as shown in the image below. 

![image](https://github.com/user-attachments/assets/fdc6b558-03cb-48f4-908d-07e1fea81544)

### Step 2. Load the Road Centre Lines

This loads your road centerlines into the QGIS layer group "Road Cente Lines" as shown in the image below. The onclick event opens a file explorer letting you select your road centre lines, either a single shapefile or multiple shapefiles


![image](https://github.com/user-attachments/assets/6ec4b1ce-15ff-4c88-b8a1-799d7365a743)

and a full screen view where can you view the Road Centre Lines as loaded into the QGIS project. 

![image](https://github.com/user-attachments/assets/eb2c1953-d48f-400c-9be1-1d80c42c2925)


### Step 3. Create the Bounding Boxes

This creates bounding boxes along the Road Centre Lines as loaded in the previous step. A pop up dialogue asks you to set the road width, please provide a measurement between 5m - 15m (metres)

Once completed you will now have bounding boxes created along the length of your Road Centre Lines set to the width you have used, an example of this is shown in the image below. 

![image](https://github.com/user-attachments/assets/8034bde3-8280-491c-94fc-2d2f2d98ebb5)

This shows the bounding boxes which have been created along the Road Centre Lines layer and using the width specified 

![image](https://github.com/user-attachments/assets/1471ec58-99d4-4bd5-a955-62a2b8fc4db9)



### Step 4. Create a Virtual Raster

The onclick event opens a file explorer from which can you select the source rasters you want to use in your project, as with previous steps you can select multiple or a single raster file. If you cannot see your raster files when using the file explorer change the file types (bottom right hand corner) to Show all files. You should then be able to select and load your raster to the virtual raster which is then displayed.

You should now have your vitual raster and your bounding boxes for the areas you want to sample:

![image](https://github.com/user-attachments/assets/1b552331-b2ed-49b2-8112-798d4e89fb7f)

and the virtual raster loaded into the layers we created at step one. 

![image](https://github.com/user-attachments/assets/ac3f81d1-c83b-4f50-9cfe-78ba6435e481)

Note: I used  a virtual raster in the event you had multiple raster files / mosaic to reduce the complexity of iterating over each raster and bounding box, its faster with a virtual raster. 

Finally Step 5.

### Step 5. Raster extracts to file. 

This final step in preparing your data set creates the trimmed raster extracts for each of the features in your bounding boxes. 

The on button click will ask you to specify where you want to save the extacts.

Once running the progress bar will update as it processes each raster extract. It does this one file at a time as I found on a machine with limited resources and a large number of features to extract, it was taking too long and running hot.

When completed you will have a series of folders containin the raster extracts!

![image](https://github.com/user-attachments/assets/497380c9-cf58-4868-b65a-70534dd443a6)

You now have your trimmed raster extracts and are good to go! 





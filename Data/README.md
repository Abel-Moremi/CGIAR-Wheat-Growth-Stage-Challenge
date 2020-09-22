# DESCRIPTION OF DATA

Due to licencing I cannot upload the data publicly but in can be found at the [competition](https://zindi.africa/competitions/cgiar-wheat-growth-stage-challenge/data)

The ‘Images’ folder contains 14,253 images, each with a unique ID. Train.csv contains Image_IDs and the associated label. The labels indicate the growth stage of the crop in the image Growth stages indicate the maturity of the wheat plants and are represented as a number from 1 to 7 (mature crop). The sample submission file contains the Image_IDs of the test set - you must predict the growth stage for the crops in each of these images.

It is important to note that some of the labels have been determined by experts, and may be more reliable than the other labels which have been indicated by the farmers themselves. All the test images have reliable labels. The ‘label_quality’ column in Train.csv indicates whether a label is high quality (2) or potentially less reliable (1).

Growth Stage definitions:

| Growth Phase   |    Description |  Common Name |   
|---|---|---|
| 1  |   | Crown Root  | 
| 2  | Early Vegetative Phase   |  Tillering |   
| 3  | Mid Vegetative Phase  |   |  
| 4  | Late Vegetative Phase  | Booting   |  
| 5  | Flowering and Reproductive Phase   | Heading  |  
| 6  |   | Anthesis  |  
| 7  | Ripening and Maturity Phase |  Milking  |  

### FILES

- Train.csv: Contains the image ID (UID), growth stage, and label quality for the training images.
- Images folder: Contains the actual images, with the filenames in the format [UID].jpeg
- SampleSubmission.csv:  is an example of what your submission file should look like. The order of the rows does not matter, but the names of the UIDs must be correct. You must predict growth_stage for the corresponding images.

### BACKGROUND TO THE DATA

The images were collected as part of field trials focusing on the Rabi (winter) growing season in two states of India: Punjab (with data collection in Fatehgarh, Ludhiana and Patiala districts) and Haryana (Fatehabad, Sirsa and Yamunanagar districts). Most villages in the field trials were located in a hot arid steppe climate. Punjab and Haryana fields are typically double-cropped with rice (or cotton) planted during the Kharif monsoon (June - October), and wheat planted in the Rabi season (October - March). Smallholder agriculture in this area is largely mechanized and is heavily reliant on irrigation.

Over two growing seasons a total of 1685 farmers agreed to participate in the PBI studies. For these farmers, the study team listed all plots on which the farmer was planning to grow wheat, and randomly selected one field per farmer to be included in the study. Farmers were asked to take repeat pictures throughout the season, always from approximately the same location as an initial northward oriented picture, and with approximately the same view angle.

Image acquisitions were facilitated using a custom Android application (WheatCam). The farmer set up an observation site by taking an initial geo-referenced image of a field. Subsequent images were referenced relative to the initial “ghosted” image (a mildly transparent image of the initial picture). The application allowed the farmer to frame nearly identical repeat pictures relative to landscape features (or one or two installed reference poles in the first year). A fixed white balance between images was used to minimize in-camera adjustment of illumination and RGB ratios. All pictures were uploaded to a server for further processing.

Before further processing we manually screened all images to ensure that no people were present in the image scenes, to guarantee their privacy. In addition, we removed images which were mistakenly taken indoors, or other accidental acquisitions. We further screened for images which were excessively blurred or discoloured, covered by a finger or otherwise not contained little vegetation or taken during crop cutting or application development. We anonymized the dataset by masking most non-vegetation details which might provide clues to the exact position of a farmers' field, while selecting the vegetation of interest for processing (see below).

The Region-of-Interest (ROI) was delineated automatically on an image-by-image basis using a horizon detection algorithm. The algorithm first resizes the image to 640 pixels along the x-axis, scaling the y-axis proportionally. The algorithm finds change points in the blue channel along the vertical axis of the images using the Pruned Exact Linear Time (PELT) method, approximating the location of the horizon. We then define a trapezoid ROI defined by the median horizon locations for the left and right half of the image, padded by 15% of the image height and 10% of the image width along y and x-axis directions respectively. Similarly, the two bottom corner points were defined by padding the bottom and sides of the image by 10% of the image width and height.

We use this ROI to exclude most other features from the original image which do not pertain to the area evaluated. Areas of no interest are set to black and the image is saved to disk. In addition, we manually screened all processed images and made manual corrections to guarantee the privacy of volunteer farmers where necessary.




**Project management:**
[x] Incorporate same-ish ruff rules as other ICOM projects
[x] Refactor wms.get_bbox_tuple into BBox class
[x] Try MyPy
[x] Refactor codebase to be MyPy conform (except /tools)

**Dataset management:**
[x] Remove images, where source is in trees -> TLM3 Data
[x] Use CustomBaseModel to create label json file along with each image
	> BBox coords + srs
	> Source: True/False

[x] Fix bbox label (add bottom right coords)
[x] Put labels class and wms class in seperate utils files
[x] Use CustomBaseModel to create metadata for entire dataset
	> applied filters

[x] Consider 'is_outlier' flag when creating yolo dataset
[x] Re-think what base dataset is, such that 'is_outlier' can be tracked persistently
	=> Went with external outlier_set.json to keep originial csv's unaltered

[ ] Integrate MIDAT data
	> Define 'master attribute set'
	> Project coordinates to EPSG:2056 (CX, CY use different system!)
	=> WAITING FOR NEW DATASET WITH SPRING TYPE COLUMN

[ ] Integrate MIDAT/Luzern data


[x] Rewrite get_bbox_from_point to use bl and tr coords as tuples
[x] Make sure BBox is used with bl and tr everywhere instead of with tl and br
[x] Use Marc's new CustomBaseModel class in teams chat


**Dataset generation:**
[ ] Make filtered dataset out of MIDAT data 
[ ] Find better method for generating 'not_spring' samples
[ ] Include more *obviously* not_spring examples
	(to make robust)


**Data manipulation tool:**
[x] Pull the one megaclass apart into classes of its elements
[x] Implement selection of labels and updating pixmap w/ corresponding img
[x] Create tool for flagging features as outliers
[x] Make checkbox to enable/disable spring\==true filter
[x] Write 'is_outlier' back into base dataset
( ) Make outlier_set.json output path configurable over GUI
[x] Functionality to write 'is_outlier' from json to dataset
[x] Regenerate bern dataset with new label structure and apply outlier flags

STATUS: Feature complete


**Training:**
[x] Complete first simple pipeline

[x] Try training only on (bern) seepage springs => 87.5% accuracy
[x] Think about if/how other types of springs can be detected
	> Maybe discuss with Senta/Timon
[x] Milestone report @Senta: First predictions

[x] Find out how to plot training curves with ultralytics without wandb
	=> We do get a png with the most basic learning curves 

[ ] Set up Weights and Biases

[ ] Think about how to isolate feature we're looking for from variance nearby
	-> segmentation, bounding boxes?

[ ] Identify what's difficult for the NN to learn


**Prediction:**
[x] Predict for area around given coordinates
[x] Implement'scan' feature using scan_bbox coordinates
[x] Extend PredictionResultsGrid with method to save as geojson for overlaying 
    over topo in QGIS
[x] Check correct implementation of grid idea and prediction results
[x] Make quicker interface for testing "point-and-click" predictions
	-> maybe py script that accepts coordinates as argv, similar to __main__
       in nn_predict.py
[ ] Use overlapping BBoxes to increase chances of spring feature being centered
	 + Different zoom levels? 
	-> Or object detection approach?





## Clues

detect.py: referenced class Annotator()

### utils\plots.py: defined class Annotator()

Annotator() has self.draw, which comes from PIL import Image, ImageDraw, ImageFont, using ImageDraw.Draw(self.im)

self.im is an input from detect.py, which is im0. im0 comes from im0s.copy(). im0s comes from dataset. im0s coms from LoadStreams() from source

utils\dataloaders.py: defined LoadStreams() class which returns im0

Used Annotator().box_label() function. It # Add one xyxy box to image with label. It called cv2.rectangle() function, did something to self.im

annotator instance in detect.py returned annotator.result(), which is an np array of self.im. The code is "im0 = annotator.result()"

#### Todo: find out what exactly is im0

Annotator() has a rectangle() functions that adds  # Add rectangle to image (PIL-only)

utils\plots.py: plot_images() function references Annotator.rectangle(), which is used to annotate the result images

**plot_labels()** plots the labels and rectangles

---

utils\plots.py uses *xywh2xyxy* function in plot_labels() function, plot_images(), 

utils\general.py defined *xywh2xyxy()* function, # Convert nx4 boxes from [x, y, w, h] to [x1, y1, x2, y2] where xy1=top-left, xy2=bottom-right


---

### Train.py

used plot_labels which calls *xywh2xyxy* function

labels is fed into plot_labels, labels come from labels = np.concatenate(dataset.labels, 0)

dataset comes from create_dataloader. train_path is fed. 

---

hubconf.py: referenced AutoShape()

models\common.py: defined AutoShape()

---

## Conclusions and must-dos

If we want to change the shape of anchor boxes, xywh2xyxy has to be modified

I need a training dataset. I'll then take the labeled boxes and first transform them into circles on the fly

The IoU loss function needs to be recalculated (using calculus)

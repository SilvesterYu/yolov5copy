## Clues

detect.py: referenced class Annotator()

utils\plots.py: defined class Annotator()

Annotator() has self.draw, which comes from PIL import Image, ImageDraw, ImageFont, using ImageDraw.Draw(self.im)

self.im is an input from detect.py, which is im0. im0 comes from im0s.copy(). im0s comes from dataset. im0s coms from LoadStreams() from source

utils\dataloaders.py: defined LoadStreams() class which returns im0

Used Annotator().box_label() function. It # Add one xyxy box to image with label. It called cv2.rectangle() function, did something to self.im

annotator instance in detect.py returned annotator.result(), which is an np array of self.im. The code is "im0 = annotator.result()"

#### Todo: find out what exactly is im0

Annotator() has a rectangle() functions that adds  # Add rectangle to image (PIL-only)

utils\plots.py: plot_images() function references Annotator.rectangle(), which is used to annotate the result images

---

hubconf.py: referenced AutoShape()

models\common.py: defined AutoShape()

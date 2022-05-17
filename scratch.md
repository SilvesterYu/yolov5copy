### Possible anchor

detect.py: referenced class Annotator()

utils\plots.py: defined class Annotator()

Annotator() has self.draw, which comes from PIL import Image, ImageDraw, ImageFont, using ImageDraw.Draw(self.im)

self.im is an input from detect.py, which is im0. im0 comes from im0s.copy(). im0s comes from dataset. im0s coms from LoadStreams() from source

utils\dataloaders.py: defined LoadStreams() class which returns im0

#### Todo: find out what exactly is im0

---

hubconf.py: referenced AutoShape()

models\common.py: defined AutoShape()

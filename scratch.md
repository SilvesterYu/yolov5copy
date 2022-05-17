### Possible anchor

detect.py: referenced class Annotator()

utils\plots.py: defined class Annotator()

Annotator() has self.draw, which comes from PIL import Image, ImageDraw, ImageFont, using ImageDraw.Draw(self.im)

---

hubconf.py: referenced AutoShape()

models\common.py: defined AutoShape()

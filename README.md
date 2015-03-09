ingressocr
==========

Scripts for OCRing Ingress profile images into text files and CSVs

usage:

Check out the repo to a Linux box and copy the scripts to somewhere in your path, e.g.:

```
git clone https://github.com/bvenable/ingressocr
cd ingressocr
sudo install -m 0755 ingressocr /usr/local/bin/ingressocr
sudo install -m 0755 ingresscsv /usr/local/bin/ingresscsv
```

Install tesseract OCR, e.g. on Ubuntu:

```
sudo apt-get install tesseract-ocr tesseract-ocr-eng
```

Note: you may need to [add the Universe repository](https://help.ubuntu.com/community/Repositories/CommandLine#Adding_the_Universe_and_Multiverse_Repositories) first.

Make sure you have [Ingress](https://play.google.com/store/apps/details?id=com.nianticproject.ingress) 1.71.1 installed. Go to your Agent profile and use the share button in the top right. Save the file somewhere and copy it to your Linux box where you've put the ingressocr and ingresscsv scripts.  

This will output a human-readable text version of your stats:

```
ingressocr <screenshot.png>
```

To turn it into a CSV (for spreadsheets) and put that into a file:

```
ingressocr <screenshot.png> | ingresscsv > myprofile.csv
```

You can also get just the CSV values if you're going to be updating/appending an existing CSV:

```
ingressocr <screenshot.png> | ingresscsv | tail -1 > myprofilenumbers.csv
```


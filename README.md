# VisualMRC
VisualMRC is a visual machine reading comprehension dataset that proposes a task: given a question and a document image, a model produces an abstractive answer.

You can find more details, analyses, and baseline results in our paper. You can cite it as follows:
<pre>
Paper Link
</pre>

# Statistics
- 10,197 images
- 30,562 QA pairs
- 10.53 average question tokens (tokenizing with NLTK tokenizer)
- 9.53 average answer tokens (tokenizing wit NLTK tokenizer) 
- 151.46 average OCR tokens (tokenizing with NLTK tokenizer)

# Installation
This repository provides pre-processing code and annotations (QA pairs, OCR and ROI annoation). OCR outputs for each image are provided using Tesseract OCR system. Due to the licence issue, it is not possible to distribute document images in this repository. If you want to use the document images, please contact me at ryouta.tanaka.rg@hco.ntt.co.jp. 

Clone this repository and get the document images, and then build it with the following command. 
<pre>
bash create_dataset.sh
</pre>
After pre-processing, you can obtain train.json, val.json, and test.json (we split based on URL domain)

## Dataset Format
<pre>
id: "image id"
license: "license name"
url: "URL"
screenshot_filename: "screenshot file name"
image_filename: "image file name"
bounding_boxes: [
  {
  id: "bounding box id"
  structure: "semantic class of the bounding box"
  shape:
    {
      x: "INT, top left x coordinate of the bounding box"
      y: "INT, top left y coordinate of the bounding box "
      width: "INT, Width of the ROI bounding box"
      height: "INT, Height of the bounding box"
    }
  ocr_info: [
    {
      word: "OCR token"
      confidence: "Confiden score produced by tesseract"
      bbox: 
        {
          x: "INT, top left x coordinate of the OCR bounding box"
          y: "INT, top left y coordinate of the OCR bounding box "
          width: "INT, Width of the OCR bounding box"
          height: "INT, Height of the OCR bounding box"
        }
    }
  ]
]
</pre>


## License



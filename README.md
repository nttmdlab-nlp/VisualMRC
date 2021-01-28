# VisualMRC
VisualMRC is a visual machine reading comprehension dataset that proposes a task: given a question and a document image, a model produces an abstractive answer.

You can find more details, analyses, and baseline results in our [paper](http://arxiv.org/abs/2101.11272 "VisualMRC: Machine Reading Comprehension on Document Images
"). You can cite it as follows:
<pre>
@inproceedings{VisualMRC2021,
  author    = {Ryota Tanaka and
               Kyosuke Nishida and
               Sen Yoshida},
  title     = {VisualMRC: Machine Reading Comprehension on Document Images},
  booktitle = {AAAI},
  year      = {2021}
}
</pre>

# Statistics
- 10,197 images
- 30,562 QA pairs
- 10.53 average question tokens (tokenizing with NLTK tokenizer)
- 9.53 average answer tokens (tokenizing wit NLTK tokenizer) 
- 151.46 average OCR tokens (tokenizing with NLTK tokenizer)

# Get Started
If you want to use the dataset, please contact me at ryouta.tanaka.rg@hco.ntt.co.jp. 

## Dataset Format
<pre>
id: "image id",
url: "URL",
screenshot_filename: "screenshot file name",
image_filename: "image file name",
bounding_boxes: [
  {
  id: "bounding box id",
  structure: "semantic class of the bounding box",
  shape:
    {
      x: "INT, top left x coordinate of the bounding box",
      y: "INT, top left y coordinate of the bounding box ",
      width: "INT, Width of the ROI bounding box",
      height: "INT, Height of the bounding box",
    }
  ocr_info: [
    {
      word: "OCR token",
      confidence: "Confiden score produced by tesseract",
      bbox: 
        {
          x: "INT, top left x coordinate of the OCR bounding box",
          y: "INT, top left y coordinate of the OCR bounding box ",
          width: "INT, Width of the OCR bounding box",
          height: "INT, Height of the OCR bounding box",
        }
     }
   ]
  }
]
qa_data:[
  {
  question:
    {
      text: "question"
    }
   answer:
    {
      text: "answer",
      relevant: ["relevant bounding boxes that needs to answer the question"]
    }
  }
]
</pre>





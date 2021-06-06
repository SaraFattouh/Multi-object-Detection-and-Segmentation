# Multi-object Detection and Segmentation


### Description
Mask R-CNN based instance segmentation model using [Detectron2](https://github.com/facebookresearch/detectron2). Detectron2 was written in PyTorch and contains many state-of-the-art obejct detection models with pretrained weights.

Convert the Simpsons Main Characters dataset to COCO format. After that, finetune a pretrained instance segmentation model (which was trained on COCO dataset) to segment Simpson characters.

## Prepare dataset

* Download the Simpsons Main Characters dataset.Here you can find more information about the dataset: https://www.kaggle.com/mlwhiz/simpsons-main-characters 
* Preprocess the data.
  * In the `file_name`, replace the '\\' characters with '/'.
* Split the dataset into train-test sets. The test set should contain 8 images of each character.
* Convert the datasets to Detectron2's COCO format. Here you can find the format: https://detectron2.readthedocs.io/tutorials/datasets.html#standard-dataset-dicts 
  * You only need to use these fields: `file_name, height, width, image_id, annotations`.
  * Each `annotation` field should contain a list that contains dictionaries with the following keys: `bbox, bbox_mode, category_id, iscrowd, segmentation` (*Note: `category_id` indexing should start from 0 (you can use the original `category_id-1`), and the value of `iscrowd` should be 0.*)
* Finally, register the datasets and visualize some (e.g. 3) samples (randomly), to check that everything works fine.
  * You have to set the `MetadataCatalog` as well, see: https://detectron2.readthedocs.io/tutorials/datasets.html#metadata-for-datasets





![plot](https://github.com/SaraFattouh/Multi-object-Detection-and-Segmentation/blob/main/Simpsons.png)

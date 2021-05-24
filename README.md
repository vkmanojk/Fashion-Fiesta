# [Fashion Fiesta](https://github.com/vkmanojk/Fashion-Fiesta)
### An e-commerce service with additional try-on facility where the user can witness how he/she would look if he/she wears the selected apparel.

<p float="left">
  <img src="inputs/example_person.jpg" width="256" hspace="20"/>
  <img src="inputs/example_clothing.jpg" width="256" hspace="20"/> 
  <img src="output/example_output.png" width="256"/> 
</p>

* [Setup](#setup)
  * [Test Example](#test-example)
* [Notebooks](#notebooks)
* [References](#references)


## Requisites

* [Conda](https://conda.io/docs/user-guide/install/index.html)
* [Flask](https://flask.palletsprojects.com/en/1.1.x/installation/)
* [MySQL](https://www.mysql.com/products/workbench/)

## Setup

First clone the repository:
```
git clone https://github.com/vkmanojk/VirtualTrialRoom.git
cd VirtualTrialRoom
```

Next, run `setup.sh`, which will create a conda environment and install the required packages via
```
conda create --name fashionfiesta python=2.7 pip
source activate fashionfiesta
pip install -r requirements.txt
```
Additionally, `setup.sh` will clone and setup auxiliary repositories that do the [Human parsing](https://github.com/vkmanojk/HumanParsing.git), [Pose estimation](https://github.com/vkmanojk/Pose-Estimation.git), and [Clothing style transfer](https://github.com/vkmanojk/VirtualTrialRoom.git) steps. This process will download models for each of the tasks.

The e-commerce website designed for this project is available here [Fashion Fiesta](https://github.com/vkmanojk/Fashion-Fiesta.git). This website was built using Flask and MySQL

### Test Example

To test whether the setup was successful, run the following command that should reproduce the clothing transfer shown at the top of the README:
```
./run.sh inputs/example_person.jpg inputs/example_clothing.jpg
```
The corresponding output is `output/output.png` and should be similar to `output/example_output.png` (the right-most image above).

## Notebooks

This repo includes some jupyter notebooks (located in `notebooks/`) that may be useful for understanding the SmartFit pipeline and its inputs/outputs. Exact usage instructions are at the top of each notebook.

* `visualize_inputs.ipynb`
  * Explains and shows the main inputs to the clothing transfer model: body mask, face and pants, keypoint pose map, and clothing item.
* `visualize_output.ipynb`
  * Displays the output image.
* `skintone_check.ipynb`
  * Describes how the skintone check works. This is a check to make sure that the clothing transfer model did not change the skintone of the inputted person.

## References

This project builds from the work listed below:

* Human parsing
  * LIP_JPPNet ([repo](https://github.com/Engineering-Course/LIP_JPPNet), [paper](https://arxiv.org/abs/1804.01984))
* Pose estimation
  * Realtime Multi-Person Pose Estimation ([repo](https://github.com/ZheC/Realtime_Multi-Person_Pose_Estimation), [paper](https://arxiv.org/abs/1611.08050))
    * [Keras implementation](https://github.com/michalfaber/keras_Realtime_Multi-Person_Pose_Estimation)
* Virtual try-on
  * VITON ([repo](https://github.com/xthan/VITON), [paper](https://arxiv.org/abs/1711.08447))

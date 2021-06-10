# [Fashion Fiesta](https://github.com/vkmanojk/Fashion-Fiesta)
### An e-commerce service with additional try-on facility where the user can witness how he/she would look if he/she wears the selected apparel.

* [Requisites](#requisites)
* [Setup](#setup)
* [Test](#test)

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

This website was built using Flask and MySQL. The create statements required to initiate the database is also provided in the `MySQL-Setup.sql`

### Test

To run the application, first run the API provided in the [Virtual Trial Room](https://github.com/vkmanojk/VirtualTrialRoom) repository using 

```
python app.py
```

Again, run 
```
python app.py
```


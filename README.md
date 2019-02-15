![alt text](misc/logo.png "KymoButler")
## The AI that analyses your kymograph
### Setup
Clone this repository or download it to your local folder. Make sure to have the correct python version (3.6) and packages installed (see `required_packages.txt` and `conda_environments.txt`). We recommend using Anaconda (https://www.anaconda.com) and setup a virtual environment to avoid any conflicts.
### Running KymoButler from the command line
You have multiple options to run KymoButler:
* Execute this code on the command line:
`python ./KymoButler.py`
This will open up a dialog window, where you will be able to locate an image saved on your system.
* Execute this code on the command line:
`python ./KymoButler.py ./targetImage1 ./targetImage2 ./targetImage3 ...`
This will process all the target images in one go. To process all the .tif images in one folder, use
`python ./KymoButler.py ./imagefolder/*.tif`
* If want to create a one-file executable that works on your system, you can run (tested on macOS):
`pyinstaller KymoButler.spec --onefile`
This will create a ./dist/KymoButler file that you can use either by double clicking on it, or from the command line. Then you can replace
`python ./KymoButler` with `./dist/KymoButler`
and use it as above.
### Outputs
After running KymoButler on your target images, you will find in your folder 4 output files per image:
* `image_antprob.bmp`, showing the anterograde traces found by the network
* `image_retprob.bmp`, showing the retrograde traces found by the network
* `image_overlay.bmp`, showing the thresholded anterograde and retrograde traces found by the network, overlayed to the original image. To change the threshold value (default = 0.2), change threshold_value in `config.py`
* `image_kymographs.csv`, where the coordinates of the thresholded traces are saved
### Cloud version
We provide a hassle-free, one-click version of KymoButler on http://kymobutler.deepmirror.ai
### Source Data
The source data for the validation data set of our paper https://www.biorxiv.org/content/early/2018/08/30/405183 is found under (...). This archive contains 3 folders containing the same 2 biological repeats once analysed by hand, with KymoButler, and with plusTipTracker. The folders contain subfolders for each cell. Raw movie data and kymographs are included in the plustiptracker folder. Hand analysed raw data is supplied in xml format. Both KymoButler and plusTipTracker data is supplied in .mat (MATLAB) format. Full processed data is supplied in .mat format in the respective top folder.

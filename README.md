# Setup README


Performing the following actions will configure a Muse/Kinect workspace.


## Setup kinect

Ensure you see the Kinect connected to the computer with `lsusb` and seeing `Microsoft` listed

Navigate to the `libfreenect2.git` repository.

Follow the instructions for Linux, the base packages are already installed on `heracleiadl`

`git clone https://github.com/OpenKinect/libfreenect2.git`

`cd libfreenect2`

`mkdir build && cd build`

` cmake .. -DCMAKE_INSTALL_PREFIX=$HOME/freenect2`

`make`

`make install`

Once these operations are performed, you can setup the python wrapper.

I suggest creating a virtual environment for this.

`mkvirtualenv --python=$(which python3) VISION_PROJECT`

`pip install numpy`

`pip install cython`

`pip install pylibfreenect2`

`pip install opencv-python`

Open your bashrc, or the config file for whichever shell you use:

`vim ~/.bashrc`

And paste (Change this to reflect the install dir of freenect2):

`export LD_LIBRARY_PATH=$HOME/freenect2/lib:$LD_LIBRARY_PATH`

Soure your changes or restart the terminal:

`source ~/.bashrc`

Now, you can run the `python selective_streams.py` demo, located in the `examples` folder.

## Muse Setups

Download the tools here: https://storage.googleapis.com/ix_downloads/tools-3.4.2/museresearchtools-3.4.2-linux-installer.run

Install to your `$HOME` directory.




## Installing tensorflow-gpu with CUDA and cuDNN on windows 10

#### My environment
- Windows 10 pro
- Nvidia gtx 1050Ti 6GB
- Anaconda 4.6.11
- Virtual env with Python 3.6.8
- CUDA V10.0.130
- cuDNN v7.6.0 for CUDA 10.0
- Tensorflow-gpu 1.14.0

#### Checking NVIDIA driver version
Right click desktop and choose `NVIDIA Control Panel`.  
Then, click `System Info` on the left corner. Choose `Component` and check the version of NIVDIA CUDA driver.

#### Installing CUDA Toolkit
I have NIVDIA CUDA 10.2 driver in my laptop, so I choose CUDA V10.0.130.
Download from [CUDA Toolkit Archive](https://developer.nvidia.com/cuda-toolkit-archive).

Please download the `local` version or you may get an exception like `Could not find 'cudart64_100.dll'` later installing tensorflow.

It's an exe file, just launch the file and follow the defaults. Please verify the files at the default install location after the installation finishes: `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0`.

Note that you need to edit system environments. Adding `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin` to %PATH%, which contains the file `cudart64_100.dll`. If there are also links added to %PATH%, please remove them in case they may effect the environment.

#### Installing cuDNN
Go to [cuDNN Download](https://developer.nvidia.com/rdp/cudnn-download) and find the correct cuDNN version for CUDA. In this case, I use the one `cuDNN v7.6.0 (May 20, 2019), for CUDA 10.0`.

Please unzip the file after download, you can see three folders in it: `cuda\bin`, `cuda\include`, `cuda\lib`, copy all the files inside these folders to the corresponding folders in `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0`.

- `{unzipped dir}/bin/ --> C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`
- `{unzipped dir}/include/ --> C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\include`
- `{unzipped dir}/lib/ --> C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\lib`

#### Installing tensorflow-gpu
Create the virtual environment in anaconda prompt: `conda create -n keras python=3.6`. Then, activate the environment, `activate keras`. Install tensorflow-gpu using `pip install tensorflow-gpu`. Wait until the installation finishes. Please verify your environment using `python -c "import tensorflow"`, it is all good if no exceptions called.

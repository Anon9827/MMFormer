# MMFormer: Multimodal Transformer for Low-light Image Enhancement
CVPR Submission - Paper ID 9827

## Contents
This repository contains pre-trained versions of MMFormer, alongside all necessary code and data for testing and generating visual results on LOL-v1, LOL-v2 (Synthetic and Real), and SDSD (indoor and outdoor).

## Setup
For ease, utilize a Linux machine with CUDA-ready devices (GPUs).

To setup the environment, first run the provided setup script:

```bash
./environment_setup.sh
# or 
bash environment_setup.sh
```

Note: in case of difficulties, ensure ```environment_setup.sh``` is executable by running:

```bash
chmod +x environment_setup.sh
```

Give the setup a couple of minutes to run and ensure internet connectivity - the environment is approximately 7.4 GB large.

## Testing
For testing, we recommend using a GPU with at least 4 GB of VRAM. CPU is also an option, but that will make the process time-consuming.

Testing can be done by running:

```bash

# For LOL_v1
python Enhancement/test_traced_tiff.py --dataset LOL_v1 

# For LOL_v2_Real
python Enhancement/test_traced_tiff.py --dataset LOL_v2_Real

# For LOL_v2_Synthetic
python Enhancement/test_traced_tiff.py --dataset LOL_v2_Synthetic

# For SDSD-indoor
python Enhancement/test_traced_tiff.py --dataset SDSD-indoor

# For SDSD-outdoor
python Enhancement/test_traced_tiff.py --dataset SDSD-outdoor

```

Note: the testing script contains two additional toggle arguments:
- ```--count_params```: prints the number of parameters in the model
- ```--print_trace```: prints the model trace (architecture)

Inference results will be saved under ```results/ValSet```. Please make sure you rename the ```ValSet``` subfolder as per your requirements, as re-running the testing script will overwrite its contents.

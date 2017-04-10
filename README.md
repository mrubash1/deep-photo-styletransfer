# deep-photo-styletransfer
Based on "[Deep Photo Style Transfer](https://arxiv.org/abs/1703.07511)".
Amended from [here](https://github.com/luanfujun/deep-photo-styletransfer).
Utilizing improvements from [here](https://github.com/martinbenson/deep-photo-styletransfer)

### Example using this code base and default settings
![example-style-transfer-montage](images/Montage_WindowsXP_Space.jpg)

PLEASE NOTE RESTRICTIONS ON USAGE OF ORIGINAL CODE.
### Features
* Dockerised for ease of installing.
* Matting Laplacian calculations are ~100 times faster than original MATLAB code.
* No dependency on MATLAB.
* Consistent image scaling is managed automatically, rather than having to manually rescale everything.
* No longer a requirement to use particular filenames and directories.

## Setup

Build this image using something like:
```
docker build -t deep_photo .
```
To run the container you'll need recent nvidia drivers installed and nvidia-docker (from here: https://github.com/NVIDIA/nvidia-docker). Then run something like:
```
nvidia-docker run -it --name deep_photo deep_photo
```
## Usage

Run:

```python3 gen_all.py <options>```

### Arguments

```
usage: gen_all.py [-h] [-in_dir IN_DIRECTORY] [-style_dir STYLE_DIRECTORY]
                  [-in_seg_dir IN_SEG_DIRECTORY]
                  [-style_seg_dir STYLE_SEG_DIRECTORY]
                  [-tmp_results_dir TEMPORARY_RESULTS_DIRECTORY]
                  [-results_dir RESULTS_DIRECTORY]
                  [-lap_dir LAPLACIAN_DIRECTORY] [-width WIDTH]
                  [-gpus NUM_GPUS] [-opt {lbfgs,adam}]
                  [-stage_1_iter STAGE_1_ITERATIONS]
                  [-stage_2_iter STAGE_2_ITERATIONS]

optional arguments:
  -h, --help            show this help message and exit
  -in_dir IN_DIRECTORY, --in_directory IN_DIRECTORY
                        Path to inputs
  -style_dir STYLE_DIRECTORY, --style_directory STYLE_DIRECTORY
                        Path to styles
  -in_seg_dir IN_SEG_DIRECTORY, --in_seg_directory IN_SEG_DIRECTORY
                        Path to input segmentation
  -style_seg_dir STYLE_SEG_DIRECTORY, --style_seg_directory STYLE_SEG_DIRECTORY
                        Path to style segmentation
  -tmp_results_dir TEMPORARY_RESULTS_DIRECTORY, --temporary_results_directory TEMPORARY_RESULTS_DIRECTORY
                        Path to temporary results directory
  -results_dir RESULTS_DIRECTORY, --results_directory RESULTS_DIRECTORY
                        Path to results directory
  -lap_dir LAPLACIAN_DIRECTORY, --laplacian_directory LAPLACIAN_DIRECTORY
                        Path to laplacians
  -width WIDTH, --width WIDTH
                        Image width
  -gpus NUM_GPUS, --num_gpus NUM_GPUS
                        Number of GPUs
  -opt {lbfgs,adam}, --optimiser {lbfgs,adam}
                        Name of optimiser (lbfgs or adam)
  -stage_1_iter STAGE_1_ITERATIONS, --stage_1_iterations STAGE_1_ITERATIONS
                        Iterations in stage 1
  -stage_2_iter STAGE_2_ITERATIONS, --stage_2_iterations STAGE_2_ITERATIONS
                        Iterations in stage 2

```

TODO: Document this properly.

# how to install our code


cuda 11.1 version
:https://github.com/facebookresearch/maskrcnn-benchmark/issues/1236#issuecomment-903606515






## maskrcnn-benchmark

The project is built on maskrcnn-benchmark, which you can install following the instructions from the official repo (see below if using pytorch >=1.5.0): https://github.com/facebookresearch/maskrcnn-benchmark/blob/master/INSTALL.md

NOTE: When building apex on a deep learning AMI remember to set the CUDA_HOME as mentioned above if you get an error about mismatched pytorch and cuda versions

NOTE: If using pytorch >= 1.5.0 you will need to patch maskrcnn-benchmark in order for it to compile. After cloning the repo change into the git root folder and run these commands in the terminal:

cuda_dir="maskrcnn_benchmark/csrc/cuda"
perl -i -pe 's/AT_CHECK/TORCH_CHECK/' $cuda_dir/deform_pool_cuda.cu $cuda_dir/deform_conv_cuda.cu
You can then run the regular setup command
python3 setup.py build develop

Then you can proceed with the setup.py command as normal.

Afer setting up maskrcnn-benchmark and the python dependencies you should be able to run the project code. Make sure though that you can run nvidia-smi before trying to run the project code and reboot if necessary.

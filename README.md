# how to install our code


cuda 11.1 version
:https://github.com/facebookresearch/maskrcnn-benchmark/issues/1236#issuecomment-903606515






## maskrcnn-benchmark
"
cuda_dir="maskrcnn_benchmark/csrc/cuda"
perl -i -pe 's/AT_CHECK/TORCH_CHECK/' $cuda_dir/deform_pool_cuda.cu $cuda_dir/deform_conv_cuda.cu
"
# You can then run the regular setup command
python3 setup.py build develop


Software Build:
====================
* Python 3.7.1 
* PyCharm Professional Edition (Python IDE) 
    + Free for Monash Students https://jetbrains.com/student/
    + Powerful debugging tools
* Git UI (e.g SourceTree/GitKraken)
    + Good practices encouraged: branches, good commit messages, squashed commits, tags, etc.
* PyTorch (Primary ML framework)
    + Install based on CPU/GPU machine
    + https://pytorch.org/
* TensorFlow (for TensorBoard visualisation)
    + https://www.tensorflow.org/install/
* Python libraries in `requirements.txt` (Install: `pip install -r requirements.txt`)


Preamble: Operating Systems and GPU
===================================
PyTorch is compatible for Win/Mac/Linux and each has it's quirks. I, for example, like to work primarily in my Win10 environment and then run high-performance learning on dedicated ML hardware; they are often always Linux systems.

Here are some **PyTorch install notes for Win10**:
- If you have a NVIDIA GPU and plan to use it, you must install the CUDA Toolkit and it must be the correct version that matches the PyTorch you plan to install. PyTorch supports toolkit's 8.0, 9.0, 9.2 as of writing this. Visit https://pytorch.org/ for confirmation of supported versions and install instructions, and visit https://developer.nvidia.com/cuda-downloads to install the CUDA Toolkit.

- There is a known issue where calling `import torch` resolves a missing DDL import error. The fix is to install certain files as per instructed by these two isses: 
> https://github.com/pytorch/pytorch/issues/4518#issuecomment-384202353 
https://github.com/pytorch/pytorch/issues/4518#issuecomment-384209046

- There is a known issue regarding process threading of PyTorch scripts on Windows: `if __name__ == '__main__' freeze_support()`.  This occurs if you are debugging training and iterating over a DataLoader instance, typically. The fix is to wrap the code in a function and run your script in an `if __name__ == '__main__': main()`.

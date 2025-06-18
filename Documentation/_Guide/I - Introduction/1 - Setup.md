# Quick-start

Install the Python library (see the [install guide](https://github.com/pdfosborne/elsciRL#install-guide) for more options)

```
pip install elsciRL
```

Run the App Interface with the following code in a Python script.  
```python
from elsciRL import App
App.run()
```

This will give you a localhost link to open the App in a browser. This enables you to select a problem, change parameters and then input instructions to guide the agent before training. 

Once you've finished a test you can see the results will show on the App and also save the full output in your local file directory.

*Click the image to watch the demo video*

[![YouTube](http://i.ytimg.com/vi/JbPtl7Sk49Y/hqdefault.jpg)](https://www.youtube.com/watch?v=JbPtl7Sk49Y)

# Guide for New Developers

If you wish to apply the elsciRL library to your own problems or design your own algorithms you will need to understand how to train agents without the App interface. 

To edit the core elsciRL library you will need to install it as an editable package, we suggest doing this in a [Python environment](https://github.com/pdfosborne/elsciRL#using-a-python-environment)).
```
git clone https://github.com/pdfosborne/elsciRL.git
cd elsciRL
pip install -e .
```


![DemoExperiment\_UsageExample](<../../Examples/DemoExperiment.md#Usage Example>)


## Notes
- You will need to have Python installed, ideally alongside Anaconda for defining the environment.
- You will need to have Git installed if you wish to clone the demo application, otherwise you can manually download an application from its GitHub repository.
- If you are interested in using the GPU instead of CPU to train agents, then you will need to setup [CUDA](https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/) on your machine.
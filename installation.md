# Installation

You have several options for getting ready for the tutorial:
 - Install several Python packages and have a working ARM
   cross-compilation toolchain.
 - Or use a VM we provide with the tools installed.
 - For the non-physical parts of the tutorial, you can use [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/J08nY/pyecsca-tutorial-croatia2024/HEAD).

We recommend installing things yourself as using a VM inherently brings
issues.

## How do I know the setup is ready?

There are several things you can check on your own, and some for which you need our hardware.

1. Run `jupyter notebook` in the virtualenv with the mentioned Python packages installed. Open the
   `start.ipynb` notebook and run the first cell with the imports. No errors (especially import ones)
   should be produced.


## Installing everything yourself

You will need some ARM cross-compilation packages as well as a Python
environment to run the code during the tutorial.

### Build stuff

`arm-none-eabi` toolchain with the [newlib](https://sourceware.org/newlib/) (also with the nano) variant.

On Debian-like systems you should be OK with the following packages:

    binutils-arm-none-eabi
    gcc-arm-none-eabi
    libnewlib-arm-none-eabi
    libnewlib-nano-arm-none-eabi
    make

Optionally, having `gcc` or some other compiler for your host architecture enables you to compile the
target code to your host and run it there.

### Python stuff

`python >= 3.9` and installed dependencies from [requirements.txt](/requirements.txt), which
include [pyecsca](https://neuromancer.sk/pyecsca/) and [ChipWhisperer](https://github.com/newaetech/chipwhisperer).

#### Linux

Ideally, use a virtual environment:
```bash
python -m venv virt
. virt/bin/activate
pip install -r requirements.txt
```

See the [ChipWhisper docs](https://chipwhisperer.readthedocs.io/en/latest/linux-install.html) for instructions.
On Linux (Debian-like systems), it especially is important to handle the udev rules as described below.

Download the 50-newae.rules file from https://github.com/newaetech/chipwhisperer/tree/develop/hardware.

Run the following commands: 

    sudo cp 50-newae.rules /etc/udev/rules.d/50-newae.rules
    sudo udevadm control --reload-rules
    sudo groupadd -f chipwhisperer
    sudo usermod -aG chipwhisperer $USER
    sudo usermod -aG plugdev $USER
    reboot

#### Windows

See the [ChipWhisperer installation docs](https://chipwhisperer.readthedocs.io/en/latest/windows-install.html).
Then, ideally, install the [pyecsca](https://neuromancer.sk/pyecsca/) requirements into the ChipWhisperer installation.

## Using a VM


Qwiic_TCA9548A_Py
==============

<p align="center">
   <img src="https://cdn.sparkfun.com/assets/custom_pages/2/7/2/qwiic-logo-registered.jpg"  width=200>  
   <img src="https://www.python.org/static/community_logos/python-logo-master-v3-TM.png"  width=240>   
</p>
<p align="center">
	<a href="https://pypi.org/project/sparkfun-qwiic-tca9548a/" alt="Package">
		<img src="https://img.shields.io/pypi/pyversions/sparkfun_qwiic_tca9548a.svg" /></a>
	<a href="https://github.com/sparkfun/Qwiic_TCA9548A_Py/issues" alt="Issues">
		<img src="https://img.shields.io/github/issues/sparkfun/Qwiic_TCA9548A_Py.svg" /></a>
	<a href="https://qwiic-TCA9548A-py.readthedocs.io/en/latest/?" alt="Documentation">
		<img src="https://readthedocs.org/projects/qwiic-tca9548a-py/badge/?version=latest&style=flat" /></a>
	<a href="https://github.com/sparkfun/Qwiic_TCA9548A_Py/blob/master/LICENSE" alt="License">
		<img src="https://img.shields.io/badge/license-MIT-blue.svg" /></a>
	<a href="https://twitter.com/intent/follow?screen_name=sparkfun">
        	<img src="https://img.shields.io/twitter/follow/sparkfun.svg?style=social&logo=twitter"
           	 alt="follow on Twitter"></a>
	
</p>

<img src="https://cdn.sparkfun.com/assets/parts/1/2/8/9/0/14685-SparkFun_Qwiic_Mux_Breakout_-_8_Channel__TCA9548A_-01.jpg"  align="right" width=300 alt="SparkFun Servo pHAT for the Raspberry Pi">

Python module for the [SparkFun Qwiic Mux Breakout - 8 Channel (TCA9548A)](https://www.sparkfun.com/products/14685).

This package should be used in conjunction with the overall [SparkFun qwiic Python Package](https://github.com/sparkfun/Qwiic_Py). New to qwiic? Take a look at the entire [SparkFun qwiic ecosystem](https://www.sparkfun.com/qwiic).

## Contents
* [Supported Platforms](#supported-platforms)
* [Dependencies](#dependencies)
* [Installation](#installation)
* [Documentation](#documentation)
* [Example Use](#example-use)

Supported Platforms
--------------------
The qwiic TCA9548A Python package current supports the following platforms:
* [Raspberry Pi](https://www.sparkfun.com/search/results?term=raspberry+pi)
<!-- Platforms to be tested
* [NVidia Jetson Nano](https://www.sparkfun.com/products/15297)
* [Google Coral Development Board](https://www.sparkfun.com/products/15318)
-->

Dependencies 
---------------
This package depends on the qwiic I2C driver: [Qwiic_I2C_Py](https://github.com/sparkfun/Qwiic_I2C_Py)

Documentation
-------------
The SparkFun qwiic TCA9548A module documentation is hosted at [ReadTheDocs](https://qwiic-tca9548a-py.readthedocs.io/en/latest/?)

Installation
-------------

### PyPi Installation
This repository is hosted on PyPi as the [sparkfun-qwiic-tca9548a](https://pypi.org/project/sparkfun-qwiic-tca9548a/) package. On systems that support PyPi installation via pip, this library is installed using the following commands

For all users (note: the user must have sudo privileges):
```sh
sudo pip install sparkfun-qwiic-tca9548a
```
For the current user:

```sh
pip install sparkfun-qwiic-tca9548a
```

### Local Installation
To install, make sure the setuptools package is installed on the system.

Direct installation at the command line:
```sh
python setup.py install
```

To build a package for use with pip:
```sh
python setup.py sdist
 ```
A package file is built and placed in a subdirectory called dist. This package file can be installed using pip.
```sh
cd dist
pip install sparkfun_qwiic_tca9548a-<version>.tar.gz
  
```
Example Use
 ---------------
See the examples directory for more detailed use examples.

```python
import qwiic_tca9548a
import time
import sys

def runExample():

	print("\nSparkFun TCA9548A Example 1\n")
	test = qwiic_tca9548a.QwiicTCA9548A()

	if test.isConnected() == False:
		print("The Qwiic TCA9548A device isn't connected to the system. Please check your connection", \
			file=sys.stderr)
		return

	try:
		test.list_channels()
		time.sleep(2)

		test.enable_channels([4,5])
		test.list_channels()
		time.sleep(2)

		test.disable_channels(5)
		test.list_channels()
		time.sleep(2)

	except Exception as e:
            print(e)
```
<p align="center">
<img src="https://cdn.sparkfun.com/assets/custom_pages/3/3/4/dark-logo-red-flame.png" alt="SparkFun - Start Something">
</p>

# python-amcrest
This repository is a wapper for Amcrest SDK HTTP API.

This is a working in process project.

Installation
============


PIP + GIT
---------

```bash
$ pip install git+https://github.com/tchellomello/python-amcrest
$ eval "$(register-python-argcomplete amcrest-cli)"

To enable amcrest-cli autocomplete in the system:
$ sudo vi /etc/profile.d/amcrest-cli-autocomplete.sh
  eval "$(register-python-argcomplete amcrest-cli)"
```

Usage
=====

Module
------

```python
>>> from amcrest import AmcrestCamera

>>> amcrest = AmcrestCamera('192.168.0.1', 80, 'admin', 'password')
>>> camera = amcrest.camera

Check software information
>>> camera.software_information
'version=2.420.AC00.15.R\r\nBuildDate=2016-09-08'

Capture snapshot
>>> camera.snapshot(0, "/home/user/Desktop/snapshot00.jpeg")
<requests.packages.urllib3.response.HTTPResponse object at 0x7f84945083c8>

Capture audio
>>> camera.audio_stream_capture(httptype="singlepart", channel=1, path_file="/home/user/Desktop/audio.aac")
CTRL-C to stop the continuous audio flow or use a timer
```

Command Line
------------
```bash
$ man amcrest-cli

or

$ amcrest-cli --help

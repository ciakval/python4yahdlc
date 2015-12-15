# python4yahdlc

[![Build Status](https://travis-ci.org/SkypLabs/python4yahdlc.svg)](https://travis-ci.org/SkypLabs/python4yahdlc)

python4yahdlc is a Python bindings for the [yahdlc][1] library.

## Dependencies

To build and make the Python module work, you need the following elements :

 * Python 3
 * The **[setuptools][2]** package

### On Fedora

    yum install python3-setuptools

### On Debian

    aptitude install python3-setuptools

## Installation

    git clone git@github.com:SkypLabs/python4yahdlc.git
    cd python4yahdlc
    python3 setup.py install

## Usage

To generate a new HDLC data frame :

    from yahdlc import *

    frame = frame_data('hello world!')

To generate a new HDLC ACK frame with a specific sequence number :

    frame = frame_data('', FRAME_ACK, 3)

The highest sequence number is 7 and the following frame types are available :

* FRAME_DATA
* FRAME_ACK
* FRAME_NACK

Note that when you generate an ACK or NACK frame, the payload is useless.

To decode a received HDLC frame :

    data, type, seq_no = get_data(frame)

## License

This project is released under the [GPL version 3][3] license. The [yahdlc][1] library is released under the [MIT][4] license.

  [1]: https://github.com/bang-olufsen/yahdlc
  [2]: https://pypi.python.org/pypi/setuptools
  [3]: https://www.gnu.org/licenses/gpl.txt
  [4]: https://github.com/bang-olufsen/yahdlc/blob/master/LICENSE

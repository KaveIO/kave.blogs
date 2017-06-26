This describes the steps taken or changes made in order to migrate to Python 3.

Currently KTB installs Anaconda 4.1.1 with Python 3.5.2.
ROOT binaries were built against with version of python. Below is a summary of the key changes and challanges:

    2/3 Compatibility
        There were parts of the code which needed to be compatible with both version of python, as they were re-used during both installation and tests.
        Tests were modified so they now work with and require python 3. An error message is displayed when 2 is used.

    Syntax
        print statements/functions (and alike) were handled by switching to the Python 3 syntax and importing the _future_ module for use with Python2
        module path/names - switching from relative to absolute paths when importing modules (if necessary).

    string data types
    Most of the work needed was due to the difference between default python2 and 3 behaviour when handling strings (acsii vs utf-8)
    Most of the tests monitor stdout and stderr and perform string comparisons to determine the outcome.

    Testing
        Unit tests pass OK
        Installed test return OK status
        Local docker test report OK status
            Base image moved from ubuntu:14.04 to ubuntu:16.04
        Also manually tested on vanilla instances of CentOS7 and Ubuntu16 in:
            docker containers - official Centos and Ubuntu images
            AWS official marketplace AMIs






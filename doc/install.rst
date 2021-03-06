Installation Guide
==================

Prerequisites
-------------

* libzmq >= 2.1
* openssl
* libev
* libyaml

Easy Way
--------

We currently have only packages for Archlinux_. If it's your OS just
run::

    yaourt -S zerogw

The easy way is to use `zerogw bundle`_. It includes some dependencies.
Then you execute following steps::

    tar -xjf zerogw-bundle-0.5.9.tar.bz2
    cd zerogw
    ./waf configure --prefix=/usr
    ./waf build
    sudo ./waf install

.. _Archlinux: http://archlinux.org
.. _`zerogw bundle`: https://github.com/downloads/tailhook/zerogw/zerogw-bundle-0.5.9.tar.bz2

Hard Way
--------

To compile from source or to compile recent version from git you need
the following dependencies:

* python3_ needed for coyaml to build configuration parser
* libwebsite_ for handling http
* coyaml_ for handling configuration
* libzmq_ and libev_ of course
* libyaml_ for parsing configuration

For compiling coyaml, libwebsite and then zerogw itself you need to run
the following magick sequence of commands for each of them::

    ./waf configure --prefix=/usr
    ./waf build
    sudo ./waf install

For other tools see respective documentation.

.. _libwebsite: http://github.com/tailhook/libwebsite
.. _coyaml: http://github.com/tailhook/coyaml
.. _python3: http://python.org/
.. _libyaml: http://pyyaml.org/wiki/LibYAML
.. _libzmq: http://zeromq.org/
.. _libev: http://software.schmorp.de/pkg/libev.html

Verifying Install
-----------------

After install is completed you can run::

    zerogw

It should print few warnings on screen. Startup messages are printed as
warnings since they are important for installations where lower level
messages disabled. Also usually your mime-types is inconsistent (at
least in archlinux it is). But nevermind, just got to the browser and
check ``http://localhost:8000/hello``, you should see some greeting if
everything works.


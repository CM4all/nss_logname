nss_logname
===========

*nss_logname* is an glibc NSS module which pretends there is a
:file:`/etc/passwd` entry for the current uid named ``$LOGNAME``.
This should be installed in containers spawned by the process spawner.


Building nss_logname
--------------------

You need:

- a C++23 compliant compiler (e.g. gcc or clang)
- `Meson 1.2 <http://mesonbuild.com/>`__ and `Ninja <https://ninja-build.org/>`__

Get the source code::

 git clone --recursive https://github.com/CM4all/nss_logname.git

Run ``meson``::

 meson setup output

Compile and install::

 ninja -C output
 ninja -C output install


Building the Debian package
---------------------------

After installing the build dependencies, run::

 dpkg-buildpackage -rfakeroot -b -uc -us

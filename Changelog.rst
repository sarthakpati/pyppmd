================
PyPPMd ChangeLog
================

All notable changes to this project will be documented in this file.

`Unreleased`_
=============

Added
-----

Changed
-------

Fixed
-----

Deprecated
----------

Removed
-------

Security
--------

`v0.15.0`_
==========

* Now development status is Beta.

Added
-----

* Introduce PpmdCompressor and PpmdDecompressor class for stream compression.
* Introduce decompress_str() one-shot utility to return str object.

Changed
-------

* decompress() always return bytes object.

Deprecated
----------

* PPMd8: drop length mode for decompression and always use end mark mode.
* PPMd8: drop flush() method for decompression.

`v0.14.0`_
==========

Added
-----
* Introduce compress() and decompress() one-shot utility
  - compress() accept bytes-like object or string. When string, encode it to UTF-8 first.
  - decompress() has an argument encoding, if specified, it returns string.
* C: CFFI: Introduce End-Mark mode for PPMd8

Changed
-------
* C: Limit initial output buffer size as same as specified length.
* C: Allow python thread when decode/encode loop running.


`v0.13.0`_
==========

Added
-----
* Benchmark test to show performance

Changed
-------
* Change folder structures in source.
* Release resources on flush()

Fixed
-----
* Fix input buffer overrun(#8)

`v0.12.1`_
==========

Fixed
-----
* Fix dist of typing stubs


`v0.12.0`_
==========

Added
-----
* add PPMd varietion I (PPMd8)
  - Ppmd8Encoder, Ppmd8Decoder class
* MyPy typing stubs

Changed
-------
* switch to LGPLv2.1+ License
* Introduce flush() method for decode class.

Fixed
-----
* Fix build error on Windows.


`v0.11.1`_
==========

Fixed
-----
* Fix Packaging configuration

`v0.11.0`_
==========

Fixed
-----
* Better error handling for memory management.

Changed
-------
* Skip hypothesis tests on windows
* Limit hypothesis tests parameter under available memory.


v0.10.0
=======

* First Alpha

.. History links
.. _Unreleased: https://github.com/miurahr/py7zr/compare/v0.15.0...HEAD
.. _v0.15.0: https://github.com/miurahr/py7zr/compare/v0.14.0...v0.15.0
.. _v0.14.0: https://github.com/miurahr/py7zr/compare/v0.13.0...v0.14.0
.. _v0.13.0: https://github.com/miurahr/py7zr/compare/v0.12.1...v0.13.0
.. _v0.12.1: https://github.com/miurahr/py7zr/compare/v0.12.0...v0.12.1
.. _v0.12.0: https://github.com/miurahr/py7zr/compare/v0.11.1...v0.12.0
.. _v0.11.1: https://github.com/miurahr/py7zr/compare/v0.11.0...v0.11.1
.. _v0.11.0: https://github.com/miurahr/py7zr/compare/v0.10.0...v0.11.0

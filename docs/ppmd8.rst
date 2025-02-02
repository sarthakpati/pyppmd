.. _ppmd8:

Ppmd8 Objects
=============

Ppmd8Encoder and Ppmd8Decoder classes are intend to use
general purpose text compression.

It uses `end mark` of source, when output text has ``\x01\x00``,
decompression is end, and ``\x01`` raw data is escaped as ``\x01\x01``.
This is a similar way with RAR archiver but is not compatible.

.. class:: Ppmd8Encoder

    Encoder for PPMd Var.I.

.. py:method:: __init__(max_order: int, mem_size: int)

    The ``max_order`` parameter is between 2 to 64.
    ``mem_size`` is a memory size in bytes which the encoder use.

.. method:: Ppmd8Encoder.encode(data: Union[bytes, bytearray, memoryview])

    compress data, returning a bytes object containing copressed data.
    This data should be concatenated to the output produced by any
    preceding calls to the encode().
    Some input may be kept in internal buffer for later processing.

.. method:: Ppmd8Encoder.flush()

    All pending input is processed, and bytes object containing the remaining
    compressed output is returned. After calling flush(), the encode() method
    cannot be called again; the only realistic action is to delete the object.
    flush() method releases some resource the object used.


.. py:class:: Ppmd8Decoder

    Decoder for PPMd Var.I.

.. py:method:: __init__(max_order: int, mem_size: int)

    The ``max_order`` parameter is between 2 to 64.
    ``mem_size`` is a memory size in bytes which the encoder use.

    These parameters should as same as one when encode the data.

.. method:: Ppmd8Decoder.decode(data: Union[bytes, bytearray, memoryview], length: int)

   decode the given data and returns decoded data.
   When length is -1, maximum output data may be returned.

   If decoder got the end mark, decode() method automatically flush all data and close
   some resource. When reached to end mark, ``Ppmd8Decoder.eof`` member become True.

   When ``Ppmd8Decoder.needs_input`` is True, all input data is exhausted and
   need more input data to generate output. Otherwise, there are some data in internal
   buffer and reusable.

   The decoder may return data which size is smaller than specified length, that is
   because size of input data is not enough to decode.


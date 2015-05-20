Working with xls, xlsx, and ods formats
================================================================================

Work with physical file
-----------------------------------------------------------------------------

Have you attempted to do the following::

    >>> from pyexcel_io import save_data
    >>> data = [[1,2,3]]
    >>> save_data("test.xls", data)
    Traceback (most recent call last):
        ...
    NotImplementedError: The plugin for file type xls is not installed. Please install pyexcel-xls

Yes, you are recommended to install individual plugins. Here is what is needed
to do it successfuly::

    >>> from pyexcel_io import save_data
    >>> import pyexcel_xls
    >>> data = [[1,2,3]]
    >>> save_data("test.xls", data)

And you can also get the data back::

    >>> from pyexcel_io import get_data
    >>> data = get_data("test.xls")
    >>> data
    [[1.0, 2.0, 3.0]]


Work with memory file
-----------------------------------------------------------------------------

Here is the sample code to work with memory file::

    >>> from pyexcel_io import get_io
    >>> io = get_io("xls")
    >>> data = [[1,2,3]]
    >>> save_data(io, data, "xls")

The difference is that you have mention file type if you use :meth:`pyexcel_io.save_data`

And you can also get the data back::

    >>> data = get_data(io, "xls") 
    >>> data
    [[1.0, 2.0, 3.0]]

The same applies to :meth:`pyexcel_io.get_data`.


Other formats
-----------------------------------------------------------------------------

As illustrated above, you can start to play with pyexcel-xlsx, pyexcel-ods and
pyexcel-ods3 plugins.

.. testcode::
   :hide:

   >>> import os
   >>> os.unlink("test.xls")
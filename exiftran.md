To remove exif metadata:
===

    $ jpegtran -copy none in.jpg > out.jpg

Options:

 * `-copy`: The metadata to copy: `none` for no metadata, `all` to keep everything.

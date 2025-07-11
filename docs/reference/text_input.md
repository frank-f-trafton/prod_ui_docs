# Text Input

ProdUI's text input is mainly implemented as an internal library known as **LineEd**. This library comes in two variants: one for single-line text, and one for multiple lines. The latter's implementation is significantly more complex.

The barebones text input widget has its own (extremely simple) text input code.


## Limitations

The LineEd code should be sufficient for input widgets that contain a "modest" amount of text. For example, I have had no issues with about 5000 code points, but if I insert millions of bytes worth of text, I experience problems with responsiveness. Note also that portions of the text will be retained in LineEd's undo/redo history ledger.

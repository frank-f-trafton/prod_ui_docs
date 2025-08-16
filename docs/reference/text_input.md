# Text Input

The **LineEd** library provides most of ProdUI's text input functionality. It comes in two variants: one for single-line text, and one for multiple lines. The barebones text input widget has its own (extremely simple) text input code, which is not covered here.


## Relevant Files

All LineEd code is placed in the `shared` directory. `lgc_input_m.lua` and `lgc_input_s.lua` provide "widget-first" features, like functions to configure a widget for text input. The rest of the files are stored in `shared/line_ed`, with subdirectories for single-line and multi-line code. Of note are `line_ed_m.lua` and `line_ed_s.lua`, which implement the core LineEd objects.

The single and multi code is similar, but not entirely compatible, so take care not to mix their functions in one widget.

Generally, you only need to become familiar with this sorry rat's nest if 1) you are debugging a problem, 2) you want to build a new text input widget, or 3) you need to change ProdUI's text input behavior.


## Text Input Widgets

* `input/script_editor` (M): A multi-line text box with advanced text editing features.

* `input/text_box_multi` (M): The standard multi-line text box.

* `input/text_box_single` (S): The standard single-line text box.

* `wimp/combo_box` (S): A hybrid text box and drop-down menu.

* `wimp/number_box` (S): A text box that is specialized for entering numbers.


## Limitations

The LineEd code should be sufficient for input widgets that contain a "modest" amount of text. It won't cope well with users pasting in millions of code points, so consider imposing reasonable character limits on your text boxes. Note also that portions of the text will be retained in LineEd's undo/redo history ledger.

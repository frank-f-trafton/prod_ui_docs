# Themes

Themes define the UI's general look.

A ProdUI theme is a plain hierchical table of settings and references to other data. When applied, its contents are vetted and then transferred to the UI Context.

ProdUI ships with a default theme at `prod_ui/theme`, which can be loaded as a table with `uiRes.loadDirectoryAsTable()`. The result can be patched by mounting ZIP files on top of the theme's path. Or, you could make changes to the theme after loading it (and before applying it).


## Theme Components

### Boxes

TODO: Rename to edges?

Location: `theme/boxes`

Maps to: `context.resources.boxes`

Boxes provide common measurements for borders, margins and padding in widget skins.

Fields:

* `outpad {x1, y1, x2, y2}`: The intended amount of outer padding around the box. Sometimes used by the layout system. Does not affect the widget's width and height directly. Similar to "margin" in HTML/CSS.

* `border {x1, y1, x2, y2}`: An inward border that starts at the widget's edge. Usually precludes scroll bars, and may be used to designate a widget's draggable edges. Similar to "border" in HTML/CSS.

* `margin {x1, y1, x2, y2}`: Inward padding which begins at the border. Similar to "padding" in HTML/CSS.


### Fonts

Location: `theme/fonts`

Maps to: `context.resources.fonts` (as LÖVE Fonts)

Paths and settings for LÖVE Fonts.

Fields (Vector Fonts):

* `path`: The path to the font file, or `default` to use LÖVE's built-in Font.

* `size`: The font's size.

* `[fallbacks]`: An optional array of fallback font information:

	* `path`: The path to the fallback font.

	* `size`: The fallback font's size. (This should almost always match the main font's size.)


TODO: BMFont, ImageFont stuff


### Info

Location: `theme/info`

Maps to: `context.resources.info`

Info is a miscellaneous collection of settings.


#### Info: thimble_info

Contains parameters for how the "thimble" (widget keyboard focus) is represented.

TODO


#### Info: window_frames

Contains parameters for Window Frames.

TODO


### Labels

Location: `theme/labels`

Maps to: `context.resources.labels`

Text label styles for widgets.

Fields:

* `font`: The Font ID to use when measuring and rendering label text.

* `ul_color`: An independent underline color (in the form of {R, G, B, A}), or false to use the text color.

* `ul_h`: Underline height or thickness.


## Scroll Bar Data

Location: `theme/scroll_bar_data`

Maps to: `context.resources.scroll_bar_data`

Contains texture references, colors, and some settings for widget scroll bars.

Fields:

* `tquad_pixel`: Quad reference for a single white pixel. Used when drawing flat rectangles.

* `tq_arrow_down`, `tq_arrow_up`, `tq_arrow_left`, `tq_arrow_right`: Quad references for the arrow graphics on the scroll buttons.

* `render_body`: (Boolean) When true, the entire scroll bar body is drawn. Could be helpful if the buttons and trough do not fit snugly into the scroll bar's rectangular body.

* `body_color`: (Color tuple) The body's color.

* `col_trough`: (Color tuple) The trough's color.

* `shared`: A table of sub-settings for the following states: `idle`, `hover`, `press` and `disabled`:

	* `slice`: A slice reference for the scroll bar's thumb and buttons (one slice for both entities).

	* `col_body`: The color for the thumb and buttons.

	* `col_symbol`: The color for the arrow symbols on the buttons.


## Scroll Bar Styles

Location: `theme/scroll_bar_styles`

Maps to: `context.resources.scroll_bar_styles`

Style settings for widget scroll bars.

Fields:

* `has_buttons`: (Boolean) True if the scroll bars have buttons on the ends, which may be clicked to scroll the document in small increments.

* `trough_enabled`: (Boolean) True if the scroll bars have a clickable trough.

* `thumb_enabled`: (Boolean) True if the scroll bars have a clickable thumb.

* `bar_size`: The width of vertical scroll bars; the height of horizontal scroll bars.
* `button_size`: The desired height of buttons on vertical scroll bars; the desired width of buttons on horizontal scroll bars. (Buttons may be squished if there is not enough room.)
* `thumb_size_min`, `thumb_size_max`: The minimum and maximum length of the scroll bar thumb.

* `v_near_side`: (Boolean) Controls where vertical scroll bars are placed. true: right, false: left.

* `v_auto_hide`: (Boolean) When true, the vertical scroll bar is hidden when the viewport is large enough to show the document lengthwise.

* `v_button1_enabled`: (Boolean) True if the "up" button is enabled. (`has_buttons` must also be true).

* `v_button1_mode`: How the button scrolls when clicked. (TODO: elaborate.)

* `v_button2_enabled`: (Boolean) True if the "down" button is enabled. (`has_buttons` must also be true).

* `v_button2_mode`: How the button scrolls when clicked. (TODO: elaborate.)

* `h_near_side`: (Boolean) Controls where horitonzal scroll bars are placed. true: top, false: bottom.

* `h_auto_hide`: (Boolean) When true, the horizontal scroll bar is hidden when the viewport is large enough to show the document widthwise.

* `h_button1_enabled`: (Boolean) True if the "left" button is enabled. (`has_buttons` must also be true).

* `h_button1_mode`: How the button scrolls when clicked. (TODO: elaborate.)

* `h_button2_enabled`: (Boolean) True if the "right" button is enabled. (`has_buttons` must also be true).

* `h_button2_mode`: How the button scrolls when clicked. (TODO: elaborate.)


## Skins

Location: `theme.skins`

Maps to: `context.resources.skins`

Skins control the overall look of widgets.

*Skinners* are the rendering implementation; *skins* provide skinners with data.


## Textures

Location: `theme.textures`

Maps to: `context.resources.textures`

Links textures to the theme.

Fields:

* `path`: The path to the texture.

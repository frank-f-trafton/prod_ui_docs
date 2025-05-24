# Project Setup

Disable LÖVE Text input.

```lua
love.keyboard.setTextInput(false)
```

Text input should not be changed by user code while the ProdUI context is active. Widgets will turn text input on and off as they take and release keyboard focus. If left on all the time, there is a chance that keystrokes will generate conflicting `keypressed` and `textinput` events.

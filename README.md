# Gideros_ButtonPad
A simple helper class that allow you to easely create a grid of buttons

# Pad

Pad is a layout with buttons in it. By using it you can easely create grid of different buttons.

# Example

```lua
local pad = Pad.new{
	w = 300, h = 300, -- pixel pad size
	rows = 3, -- number of rows
	columns = 3, -- number of columns
	color = 0x272727, -- background color
	margin = 4, -- margin from pad's cornders
	innerMargin = 2 -- margin between buttons inside
}

pad:addButton{ 
	x = 0, -- 0 based layout x index
	y = 0, -- 0 based layout y index
	scaleX = 4, -- textfiled scale x
	scaleY = 4, -- textfiled scale x
	bgColor = 0x323232, -- button bg color
	txtColor = 0xffffff, -- button text color
	name = "Erase", -- button name
	text = "<"  -- text to display
}

function padClick(e)
	local name = e.name -- button name
	local btext = e.text -- button text
	print(name, btext)
end


-- handle click on button
pad:addEventListener("click", padClick)
stage:addChild(pad)
```

# Pad constructor (table):
		w (number): pixel width of the pad
		h (number): pixel height of the pad
		rows (number): number of rows 
		columns (number): number of columns
		texture (Texture): nine patch texture [optional]
		color (number): pad color [default: black]
		margin (number): margin (same for each side) [default: 0]
		innerMargin (number): button margin [default: 0]
    
# Pad "addButton" params (table):
		x, y (number): The 0-based indexes of the column/row the button must be placed into
		gridwidth (number): The number of column this button will take [default: 1]
		gridheight (number): The number of row this button will take [default: 1]
		<Button params>
    
# Button params (table):
		w (number): width of the button
		h (number): height of the button
		font (Font): font to use [optional]
		name (string): name of the button [optional]
		text (string): text to display [optional]
		texture (Texture): ninepatch texture to use [optional]
		txtColor (number): text color [default: black]
		bgColor (number): background color [default: black]
		offsetX (number): offset position by X [default: 0]
		offsetY (number): offset position by Y [default: 0]
		scaleX (number): text scale by Y [default: 1]
		scaleY (number): text scale by Y [default: 1]
# Label params:
		font (Font): font to use [optional]
		text (string): text to display [optional]
		color (number): text color [default: black]
		x (number): initial x position
		y (number): initial y position
		scaleX (number): text scale by X
		scaleY (number): text scale by Y

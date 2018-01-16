# Lynda:Learning vue.js


## Scoped slots
Scoped slots allow for custom a template to be used within existing components

When a componenetis used that has a scoped slot child, it will take the content from the data it's using and passit back up into the parent component allowing for it to be used in a new custom (temporary) template. 

This means that the main strokes of any layout can be created as components but leave 'spaces' (slots) for a custom, content sensitive layout. 

So one template could be a grid layout full of slots. This would allow us to pass in a custom layout/component for the tiles without requiring separate templates for each combination
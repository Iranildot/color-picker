# Color Picker
A color picker made using python and tkinter library

Overview:
SliderFunctions:

Manages the functionality related to the color slider, including calculating color positions based on RGB values, handling mouse events for color selection, and updating the UI accordingly.
GradientSlider (inherits from SliderFunctions):

Represents a graphical slider for selecting colors along a gradient. It uses methods from SliderFunctions to calculate color positions and manage UI events.
PickerFunctions:

Handles the core functionality for color picking, including converting color formats (RGB to hexadecimal and vice versa), calculating color positions, and updating the UI based on user input.
GradientPicker (inherits from PickerFunctions):

Implements a color gradient picker interface using methods from PickerFunctions. It allows users to select colors from a gradient canvas and updates corresponding color representations (hexadecimal and RGB).
DisplayFunctions:

Provides methods to update the display area with a chosen color. It's used by the Display class.
Display (inherits from DisplayFunctions):

Represents a display area that visually shows the selected color. It updates its background color based on user selections.
Key Methods and Functionality:
Color Conversion: Methods like convert_color_to_dict in SliderFunctions and PickerFunctions handle conversion between RGB and hexadecimal color formats.

Event Handling: Various methods (start_picking, pick_color, stop_picking, on_right_arrow, on_left_arrow, etc.) bind to mouse and keyboard events (<Button-1>, <B1-Motion>, <ButtonRelease-1>, <Right>, <Left>, <KeyPress>) to update color selections and UI components dynamically.

Drawing and UI Updates: The draw_slider and draw_gradient methods in GradientSlider and GradientPicker respectively use PIL to generate color gradient images and update the Tkinter canvas with these images.

Usage Example:
Below is an example of how you might create and use these classes to create a color picker interface:

python
Copiar código
import tkinter as tk
from PIL import Image, ImageTk

# Create the main Tkinter window
root = tk.Tk()
root.geometry("600x400")

# Create a GradientPicker instance
gradient_picker = GradientPicker(root, width=300, height=200)
gradient_picker.grid(row=0, column=0, padx=10, pady=10)

# Create a Display instance to show selected color
display = Display(root, width=100, height=50)
display.grid(row=0, column=1, padx=10, pady=10)

# Start the Tkinter event loop
root.mainloop()

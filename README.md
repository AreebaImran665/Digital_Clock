DIGITAL CLOCK USING PYTHON

---------------------------------------

This Python script creates a simple digital clock using the Tkinter library. The clock displays the current time in hours, minutes, and seconds, along with the current date. The time updates every 80 milliseconds to ensure it stays accurate.

---------------------------------------

Importing Required Modules

---------------------------------------

from time import strftime
from tkinter import Label, Tk
strftime from the time module is used to format date and time.
Label and Tk are imported from the tkinter module to create the GUI.

---------------------------------------

Creating the Main Window

---------------------------------------

window = Tk()
window.title("")
window.geometry("200x80")
window.configure(bg="green")  
window.resizable(False, False)
window = Tk(): Initializes the main application window.
window.title(""): Sets the window title to an empty string (no title).
window.geometry("200x80"): Sets the window size to 200 pixels wide and 80 pixels high.
window.configure(bg="green"): Sets the background color of the window to green.
window.resizable(False, False): Disables window resizing to keep the window size fixed.

---------------------------------------

Creating the Clock Label

---------------------------------------

clock_label = Label(
    window, bg="black", fg="cyan", font=("Arial", 30, "bold"), relief="flat"
)
clock_label.place(x=20, y=20)
A Label widget named clock_label is created:
window: Sets the parent of this label.
bg="black": Sets the background color of the label to black.
fg="cyan": Sets the text color of the label to cyan.
font=("Arial", 30, "bold"): Sets the font of the label text to Arial, size 30, in bold.
relief="flat": Sets the border style of the label to flat.
clock_label.place(x=20, y=20): Positions the clock_label widget at coordinates (20, 20) within the window.

---------------------------------------

Defining the Update Function

---------------------------------------

def update_label():
    """
    This function will update the clock every 80 milliseconds
    """
    current_time = strftime("%H: %M: %S\n %d-%m-%Y ")
    clock_label.configure(text=current_time)
    clock_label.after(80, update_label)
    clock_label.pack(anchor="center")
update_label(): A function that updates the clock_label widget with the current time and date.
current_time = strftime("%H: %M: %S\n %d-%m-%Y "): Gets the current time formatted as "Hour:Minute
\n Day-Month-Year".
clock_label.configure(text=current_time): Updates the clock_label text to the current time.
clock_label.after(80, update_label): Calls the update_label function again after 80 milliseconds, creating a loop to continuously update the time.
clock_label.pack(anchor="center"): Packs the clock_label widget into the window, centered in the available space.

---------------------------------------

Starting the Clock and Main Loop

---------------------------------------

update_label()
window.mainloop()
update_label(): Calls the update_label function for the first time to start the clock updates.
window.mainloop(): Starts the Tkinter event loop, which waits for events (like button clicks) and updates the GUI. The loop runs until the window is closed.

---------------------------------------

Usage

---------------------------------------

Run the script.
A window will appear displaying the current time and date.
The time will update every 80 milliseconds to stay accurate.
This simple clock can be customized further by changing the font, colors, window size, and update interval as needed.
 

---------------------------------------

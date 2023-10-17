# Music-Player
I created a mp3 music player in which one can play the song, pause it, resume it, and navigate from the current song to the next song as well as previous songs. using Python and its libraries. The first library that I used is Tkinter .

STEPS to develop this project:

1) Import important libraries
2) Create the project layout
3) Define play, pause, and other music player functions

Explanation:

First line imports the mixer module from pygame, then I import tkinter.

Next, I import the font module from the tkinter library. At last filedialog is imported which has many applications like opening a file, a directory, etc.

Tk() is a top level widget that is used to create the main application window.

The title() method is used to give a name to python mp3 player application which is displayed at the top.

mixer.init() is used to initialize the mixer module so that one can use it’s various functions in our application.

Listbox() widget is used to create a listbox in which one can store our songs.

I have passed various parameters, first is the root specifying that the widget should be placed in the python mp3 player window.
Then, bg is for background color, fg is for foreground color.
selectbackground and selectforeground basically change the background and the foreground color of a particular item upon selecting it.

grid() widget is a geometry manager which organizes the widgets properly in a grid-based fashion before placing it in the root window. columnspan=9 gives a space of 9 columns to our listbox widget.

Button() widget is used to create a button. We want the buttons in our main window so the input root is given. Then the text which will be displayed on the button is specified and at last in the command input a function is given which will be called when the button is clicked.

Menu() widget is displayed just under the title bar, it is used to conveniently access various operations. One can access Add songs and Delete songs for our playlist, upon clicking addsongs and deletesong functions are called respectively.

addsongs() is used to add songs in our listbox, filedialog.askopenfilenames() opens a dialog box corresponding to the folder whose path is provided. Then, we can select songs and store them in temp_song variable, after this I looped through the list to insert every item in the listbox.

deletesong() is used to delete a selected song, songs_list.curselection() function returns a tuple in which the first element is the index of the selected song. Then, .delete() function is used to delete the song corresponding to the index which is passed.

Play() function is used to play the selected song , I used the .get() method to get the selected song, then I loaded the song and play it using the next two lines.

Pause() function is used to pause the song, there is need to pass any argument to the mixer.music.pause() function.

Stop() function is used to stop the song, I used mixer.music.stop() function to stop the song.

songs_list.selection_clear(ACTIVE) is used to unselect the selected song from the listbox.

Resume() function is used to resume the song using mixer.music.unpause() function.

Previous() function is used to play the previous song in the listbox, songs_list.curselection() function returns a tuple in which the first element is the index of the selected song in python mp3 music player project. I stored it in a variable called previous_one, then I update its value to get the previous index by subtracting 1. 

Next, songs_list.get(previous_one) returns the previous song, I stored this value in temp2 after that I load this song and play it.
There can be a problem here, although the previous song would start playing but the selected song would not change. So, I rectified that with the help of the next three lines of code.

Next() function is implemented in a similar way as the previous function. Here, instead of subtracting 1, I added one apart from this step every other step is the same.

## Music Player
The prerequisites are as follows :

* Basic Python concepts
* Tkinter
To install the libraries, you can use pip installer from the cmd/Terminal:
``Pip install tkinter``

## Createmain.py

```
import pygame
from pygame import mixer
from tkinter import *
import os

def playsong():
    currentsong=playlist.get(ACTIVE)
    print(currentsong)
    mixer.music.load(currentsong)
    songstatus.set("Playing")
    mixer.music.play()

def pausesong():
    songstatus.set("Paused")
    mixer.music.pause()

def stopsong():
    songstatus.set("Stopped")
    mixer.music.stop()

def resumesong():
    songstatus.set("Resuming")
    mixer.music.unpause()    

root=Tk()
root.title('ProjectGurukul Music player project')

mixer.init()
songstatus=StringVar()
songstatus.set("choosing")

#playlist---------------

playlist=Listbox(root,selectmode=SINGLE,bg="DodgerBlue2",fg="white",font=('arial',15),width=40)
playlist.grid(columnspan=5)

os.chdir(r'C:\Users\BOSS\Desktop\MyPlaylist')
songs=os.listdir()
for s in songs:
    playlist.insert(END,s)

playbtn=Button(root,text="play",command=playsong)
playbtn.config(font=('arial',20),bg="DodgerBlue2",fg="white",padx=7,pady=7)
playbtn.grid(row=1,column=0)

pausebtn=Button(root,text="Pause",command=pausesong)
pausebtn.config(font=('arial',20),bg="DodgerBlue2",fg="white",padx=7,pady=7)
pausebtn.grid(row=1,column=1)

stopbtn=Button(root,text="Stop",command=stopsong)
stopbtn.config(font=('arial',20),bg="DodgerBlue2",fg="white",padx=7,pady=7)
stopbtn.grid(row=1,column=2)

Resumebtn=Button(root,text="Resume",command=resumesong)
Resumebtn.config(font=('arial',20),bg="DodgerBlue2",fg="white",padx=7,pady=7)
Resumebtn.grid(row=1,column=3)

mainloop()
```
## Libraries Used:

* Pygame: to play, pause, load, stop, and resume music.
* Tkinter: to develop GUI.
* os: to access the song folder.

## Functions Used:
* playsong: It loads the active song from the list and plays the required song. It gets executed when the user clicks on “play”.
* pausesong: It pauses the required song. It gets executed when the user clicks on “pause”.
* stopsong: It stops the required song. It gets executed when the user clicks on “stop”.
* resumesong: It resumes the required song. It gets executed when the user clicks on “resume”.

## Variables Used:
* root: the main GUI window.
* songstatus: it stores the status of the currently active song.
* playlist: It stores the name of all songs available at the specified location.
* Rest are play, pause, stop, and resume buttons.

## Music Player Output

![python-music-player](https://github.com/Naresh-Gudipalli/game/assets/110377660/617d2d8e-6fa9-4423-b730-e3e7ad8d21d7)

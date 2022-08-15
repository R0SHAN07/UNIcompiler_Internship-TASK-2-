# UNIcompiler_Internship
# TASK-2 (Youtube video Downloader) 
import tkinter
from pytube import YouTube
window=tkinter.Tk()
window.geometry('820x500')
window.title("Youtube Video Downloader")
l1=tkinter.Label(window,text="Youtube Video Downloader",bg='white',fg='red',font=("Ariel Bold",50)).pack()
l2=tkinter.Label(window,text="Paste your link here :",font='san-serif 15 bold').place(x=325,y=100)
url= tkinter.StringVar()
url_enter=tkinter.Entry(window,width=70,textvariable=url).place(x=200,y=150)
tkinter.Label(window,text="Download may take some time please be patient...",font='san-serif 15 bold').place(x=300,y=400)

def clicked():
  my_video=YouTube(str(url.get()))
  tkinter.Label(window,text=my_video.title)
  vid=my_video.streams.get_highest_resolution()
  vid.download()
  tkinter.Label(window,text="Your video is successfully downloaded",font='san-serif 15 bold').place(x=200,y=250)
  tkinter.Label(window,text="Thank you for using this application ")
tkinter.Button(window,text="Download",bg='red',fg='white',font='san-serif 15 bold',padx=2,command=clicked).place(x=350,y=200)
        
window.mainloop()

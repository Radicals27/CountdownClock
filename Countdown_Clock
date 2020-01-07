from datetime import *
from tkinter import *
import time

#Main function
def calc_time():

    #Get time and date from user-input via text boxes (e1 and e2, respectively)
    time = e1.get()
    date = e2.get()

    #Try/catch block to ensure time/date data is correct format
    try:
        year = int(date[4:8])
        month = int(date[2:4])
        day = int(date[0:2])
        hour = int(time[0:2])
        minute = int(time[2:4])
    except:
        print("ERROR: Check Time/Date fields.")

    #Then = future data, Now = the present date & time (ignoring microseconds)
    then = datetime(year, month, day, hour, minute, 0)  # Random date in the past
    now = datetime.now().replace(microsecond=0)

    #Check the time and date are the correct length (date = 8 digits, time = 4 digits)
    result_time = str(then - now)  #Where the actual magic happens (the calculation only takes 1 line!)
    time_length = len(e1.get()[0:])
    date_length = len(e2.get()[0:])

    if now > then:
        print("Date must be in the future.")

    if time_length != 4:
        print("Time needs to be 4 digits.")

    if date_length != 8:
        print("Date needs to be 8 digits.")

    else:
        label1.configure(text=result_time)
        label1.after(1000, calc_time)

def clicked():
    calc_time()

#GUI setup via Tkinter library
window = Tk()

window.title("Countdown Clock")
window.geometry('400x200+250+250')

Label(window, text="Time (HHMM)").grid(row=0)
Label(window, text="Date (DDMMYYYY)").grid(row=1)

e1 = Entry(window)
e1.grid(row=0, column=1)
e2 = Entry(window)
e2.grid(row=1, column=1)

btn = Button(window, text="Count Down", command=clicked)
btn.grid(row=2, column=1)

label1 = Label(window, text="Results here", font=("Courier", 16))
label1.grid(row=3, column=1, columnspan=3)

window.mainloop()  #This loop keeps looping and printing the new time remaining each second

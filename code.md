# https-github.com-shefali271993-shef
Projects
from __future__ import print_function

import string
from tkinter import *  #  interface to the Tk GUI toolkit
import tkinter as tk   #
import random
import time


width=17
height=17





global bx_score
bx_score = 0
bx_sc = 0
ramin =0
words = ['PHISHING','ANTIVIRUS', 'UPDATE', 'MALWARE', 'MALICIOUSURL', 'RANSOMWARE', 'HACKER']

grid = ["   ACJLHBNTYZXWRBNIH", "   ABCUPDATEABROHVXF", "   NJUFRHOHNVXSWAQUN", "   TMRNASOMWAREJWKKL", "   IQAAHACKERRTYUIOP", "   VMSLDFGHJKLZXCVBN", "   IPRTIWEASDFGTYYUI","   ROHPZCZXCVBNKMYBE","   USDILRIYVIJGDCEWE","   SXEASFGOHJGFDTVYI", "   SRUOBHSRUWUOKNVDE", "   QWEPOIIYTSRESASDV", "   MALWARENZXUKBJHGF", "   RFSHGFDSGASRYEBIN", "   LOCMARLAAMBRLGINE", "   GNIREENIGNELAICOS", "   NTCESFVHREAISJFNF"];


def open_window(title, message, color):
    pyr = Tk()
    pyr.geometry('350x200')
    pyr.title(title)
    pyr.configure(background = color)
    lbl = Label(pyr, text=message, bg=color, font=('arial',18))
    lbl.grid(column=2, row=1)
#    img = ImageTk.PhotoImage(Image.open("win.jpg"))
#    pyr.create_image(20,20, anchor=NW, image=img)
    pyr.mainloop()





def calculate_score():
    top= Toplevel()
    top.title('GAME HAS BEEN STARTED')
    header = Label(top,text="Find the words, please write the answer in Capital letters !!",font=('arial',18),fg="#659e9d").grid()

    for i in range(width):
         Label(top, text=' '.join(grid[i]), font=('gothic', 18, 'bold'), fg='#2a4537').grid()   #vitulize the letter, with size and font

    text_input = StringVar()    # to create  a Tkinter variable

    bx_sc = Label(top, text=('                            SCORE : ' + str(bx_score) + '                             '),bg='#656565',fg='white',font=('arial',15,'bold'))
    bx_sc.grid()



    
    ll1 = Label(top,text =("Timer:"))
    ll1.place(x=55, y = 50)
    def countdown(count):
    # change text in label
        mins, secs = divmod(count, 60)
        timeformat = '{:02d}:{:02d}'.format(mins, secs)
        print(timeformat, end='\r')
        label['text'] = timeformat
        
        

        if count > 0:
            # call countdown again after 1000ms (1s)
            root.after(1000, countdown, count-1)
        else:
            fail = Label(top,text =("Game Over"), font=('arial',18),fg="#bf1000")
            fail.place(x=35, y = 100)
#            root.after(30000, top.destroy())
#            text_box.grid(x = 60,y = 100)
#            text_box.insert("end-1c", "Try again!")

#root = tk.Tk()

    label = tk.Label(top)
    label.place(x=60, y=70)

    # call countdown first time
    countdown(210)
    # root.after(0, countdown, 5)

    top.grid()
    
    
    
    
 
    def btnClick():    #CREATE A BUTTEN to check the word
        global bx_score
        words2 =[]
        i =0
        x = user_ans.get()    #
        print(x)

        if x in words:
            #if x in words2:
               # print("the answer is not correct, Please try again")
          #else:
           # ans = "TRUE"
            passs = Label(top,text =("    correct entery "), font=('arial',18),fg="#352bc4" )
            passs.place(x=430, y = 480)
            print("correct entery")
               # words2[i] = x
              #  i= i+1
                #print("x value", x)
            bx_score += 10
            bx_sc.config(text=('                            SCORE : ' + str(bx_score) + '                             '))
            
#        elif x== " ":
#            print("please enter a word")
        else:
          #  print("current socre is",bx_score)
           # print("the answer is not correct, Please try again")
            passs = Label(top,text =("incorrect entery  ") ,  font=('arial',18),fg="#bf1000" )
            passs.place(x=430, y = 480)

           # open_window("Wrong", "Wrong answer, please try again", "#994240")
        #    ANS = "False"
        if bx_score >= 70:
            open_window("Right", "Congratulation WINNER you have found all words", "#67bdbf")
       # else:
           # open_window("Wrong", "Nope", "#ff0000")
        text_input.set("")

        

#&*&?
    user_ans = Entry(top, font=('helvetica', 30), bg='#a1c4c3', fg='#5b5b5b' ,bd=10, justify='center', textvariable=text_input, insertwidth=5)
    user_ans.grid()


    submit = Button(top,font=('helvetica',15,'bold'),text='submit your answer',padx=50,pady=8,bd=4,bg='#a1c4c3', fg='#5b5b5b',command= btnClick).grid()


    clue_title = Label(top, font=('helvetica', 15, 'bold'),
                  text="*     WordsHints    *", fg='#3E3F64').grid()
                
    clue1 = Label(top, font=('helvetica', 15, 'bold'),
    text="1. A software that is used to detect, remove and prevent virus to get in to the system, it is important to secure your computer ",fg='#574e51')
    clue1.place(x=2, y = 580)
    
    
    clue2 = Label(top, font=('helvetica', 15, 'bold'),
                  text="2. A kind of malicious software that is used to encrypt victim data, files and ask user to pay money to get it their data back.",fg='#574e51')
    clue2.place(x=2, y = 600)
    
    clue3 = Label(top, font=('helvetica', 15, 'bold'),
                     text="3. Someone who gain unauthorized access to a device, to harm, edit, or destroy the data .",fg='#574e51')
    clue3.place(x=2, y = 620)

    clue4 = Label(top, font=('helvetica', 15, 'bold'),
                  text="4. A method to get sensetive information such as username, passwords by sending email or text massages.",fg='#574e51')
    clue4.place(x=2, y = 640)

    clue5 =     Label(top,font=('helvetica',15,'bold'),justify='left',text="5. A bad link that is created by an attacker to comprmise victim machine ",fg='#574e51')
    
    clue5.place(x=2, y = 660)


    clue6 = Label(top, font=('helvetica', 15, 'bold'),
                  text="6. To bring your system up to date, it is important to do that because it inculde patches to some security holes  ",fg='#574e51')
    clue6.place(x=2, y = 680)

    clue7 = Label(top, font=('helvetica', 15, 'bold'),
                  text="7. A name that cover number of suspicious and malicious software such as spyware, ransomware, and viruses ",fg='#574e51')
    clue7.place(x=2, y = 700)

                  
            


    score = Label(top,).grid()





h=250
w=250

root=Tk()
root.title('WordSearchSecurity')

cnvas=tk.Canvas(root,height=h,width=w).grid()

frame=tk.Frame(root,bg='#c4a1b4',height=h,width=w)
frame.place(relwidth=1,relheight=1)

lb1=tk.Label(frame,font=('aharoni',35,'bold'),text='  Word-Search',fg='white',bg='#c4a1b4',anchor='center').grid(row=1,column=2)


start_game = tk.Button(frame,font=('helvetica',20,'bold'),text='START ',bg='#c4a1b4',command=lambda:calculate_score()).grid(row=3,column=2, padx=30, pady=10)

quit_game = tk.Button(frame,font=('helvetica',20,'bold'),text=' QUIT  ',bd=8,bg='#c4a1b4',command=lambda:root.destroy()).grid(row=5,column=2, padx=30, pady=10)

lb2=Label(root,text='Word-Search- security, Made by group #15 ',fg='white',bg='#8d8d8d').grid()
tk.mainloop()




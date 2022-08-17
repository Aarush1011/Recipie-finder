# Recipie-finder
import pandas as pd
import matplotlib.pyplot as mpy
import numpy as np
import pickle

rec=pd.read_csv("Recipes.csv")
mex=pd.read_csv("mexican.csv")
ita=pd.read_csv("italian.csv")
rec2=pd.read_fwf("recipes.txt")
from tkinter import *
root=Tk()
root.geometry('500x500')
label1=Label(root,text='Choose which cuisine')
label1.configure(font=(45))
label1.pack()
radio=StringVar()
radio2=StringVar()
m=Message(root)


def indian():
    def selection():
        global selectnv
        selectnv=str(radio.get())
    rb1=Radiobutton(root,text='Veg',variable=radio,value='V',command=selection)
    rb1.place(x=800,y=160)
    rb2=Radiobutton(root,text='Non-Veg',variable=radio,value='NV',command=selection)
    rb2.place(x=1000,y=160)
    def open1():
        top=Toplevel(root)
        top.geometry('500x500')
        if selectnv=='V':
            dff=pd.set_option('display.max_colwidth', 1500)
            m=Message(top,text=rec3.head(2))
            m.pack()
        elif selectnv=='NV':
            dff=pd.set_option('display.max_colwidth', 1500)
            m=Message(top,text=rec3.head())
            m.pack()
        top.mainloop()
    b=Button(root,text='ENTER',command=open1)
    b.place(x=900,y=550)
    def selection2():
        select2=str(radio2.get())
    print("You can order all the ingredients from bigbasket from our calculations, link - https://www.bigbasket.com/")
    rb1=Radiobutton(root,text='Crispy Dosa',variable=radio2,value='veg',command=selection2)
    rb1.place(x=800,y=250)
    rb2=Radiobutton(root,text='Idli',variable=radio2,value='veg2',command=selection2)
    rb2.place(x=800,y=300)
    rb3=Radiobutton(root,text='Chicken Tikka',variable=radio2,value='Non-Veg',command=selection2)
    rb3.place(x=800,y=350)
    rb4=Radiobutton(root,text='Butter Chicken',variable=radio2,value='Non-Veg2',command=selection2)
    rb4.place(x=800,y=400)
def mexican():
    def selection():
        global selectnv
        selectnv=str(radio.get())
    rb1=Radiobutton(root,text='Veg',variable=radio,value='V',command=selection)
    rb1.place(x=800,y=160)
    rb2=Radiobutton(root,text='Non-Veg',variable=radio,value='NV',command=selection)
    rb2.place(x=1000,y=160)
    def open2():
        top=Toplevel(root)
        top.geometry('500x500')
        if selectnv=='V':
            dff=pd.set_option('display.max_colwidth', 1500)
            m=Message(top,text=mex.head(1))
            m.pack()
        elif selectnv=='NV':
            dff=pd.set_option('display.max_colwidth', 1500)
            m=Message(top,text=mex.head(2))
            m.pack()
        top.mainloop()
    b=Button(root,text='ENTER',command=open2)
    b.place(x=900,y=550)
    def selection2():
        select2=str(radio2.get())
    print("You can order all the ingredients from amazon from our calculations, link - https://www.amazon.in/alm/storefront?almBrandId=ctnow")
    rb1=Radiobutton(root,text='7 layer burrito',variable=radio2,value='veg',command=selection2)
    rb1.place(x=800,y=250)
    rb2=Radiobutton(root,text='chimichanga',variable=radio2,value='veg2',command=selection2)
    rb2.place(x=800,y=300)
    rb3=Radiobutton(root,text='Chicken taco',variable=radio2,value='Non-Veg',command=selection2)
    rb3.place(x=800,y=350)
def italian():
    def selection():
        global selectnv
        selectnv=str(radio.get())
    rb1=Radiobutton(root,text='Veg',variable=radio,value='V',command=selection)
    rb1.place(x=800,y=160)
    rb2=Radiobutton(root,text='Non-Veg',variable=radio,value='NV',command=selection)
    rb2.place(x=1000,y=160)
    def open2():
        top=Toplevel(root)
        top.geometry('500x500')
        if selectnv=='V':
            dff=pd.set_option('display.max_colwidth', 1500)
            m=Message(top,text=ita.head(1))
            m.pack()
        elif selectnv=='NV':
            dff=pd.set_option('display.max_colwidth', 1500)
            m=Message(top,text=ita.head())
            m.pack()
        top.mainloop()
    b=Button(root,text='ENTER',command=open2)
    b.place(x=900,y=550)
    def selection2():
        select2=str(radio2.get())
    print("You can order all the ingredients from tata from our calculations, link - https://www.bigbasket.com/")
    rb1=Radiobutton(root,text='White Pasta',variable=radio2,value='veg',command=selection2)
    rb1.place(x=800,y=250)
    rb2=Radiobutton(root,text='Cheese Pizza',variable=radio2,value='veg2',command=selection2)
    rb2.place(x=800,y=300)
    rb3=Radiobutton(root,text='Pepperoni Pizza',variable=radio2,value='Non-Veg',command=selection2)
    rb3.place(x=800,y=350)
    rb4=Radiobutton(root,text='Chicken Pasta',variable=radio2,value='Non-Veg2',command=selection2)
    rb4.place(x=800,y=400)
indian=Button(root,text='INDIAN',command=indian)
indian.place(x=800,y=100)
mexican=Button(root,text='MEXICAN',command=mexican)
mexican.place(x=900,y=100)
italian=Button(root,text='ITALIAN',command=italian)
italian.place(x=1000,y=100)




root.mainloop()

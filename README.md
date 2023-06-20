import tkinter as tk
from tkinter import *
import os
from time import strftime

root = tk.Tk()
root.title("Relógio")
root.geometry("600x320")
root.maxsize(600, 320)
root.minsize(600, 320)
root.configure(background="#EDE6DB")

def get_saudacao():
    nome_usuario = os.getlogin()
    saudacao.config( text="Ola, " + nome_usuario)
def get_data():
    data_atual = strftime(" %a, %d %b %Y")
    data.config(text= data_atual)
def get_horas():
    horas_atual = strftime("%H:%M:%S")
    horas.config(text= horas_atual)
    horas.after(1000, get_horas)

tela= tk.Canvas(root, width=600, height=60, bg="#EDE6DB", bd=0, highlightthickness=0, relief="ridge")
tela.pack()
saudacao = Label (root, bg="#EDE6DB", fg="#417D7A", font=("Montserrat", 16))
saudacao.pack()
data = Label (root, bg="#EDE6DB", fg="#1D5C63", font=("Montserrat", 14))
data.pack(pady=2)
horas = Label (root, bg="#EDE6DB", fg="#1A3C40", font=("Montserrat", 64, "bold"))
horas.pack(pady=2)
get_horas()
get_saudacao()
get_data()
root.mainloop()

from tkinter import *

expr = ""
def appuyer(touche):
    if touche == "=":
        calculer()
        return
    global expr
    expr += str(touche)
    equation.set(expr)
    
def calculer():
    try:
        global expr
        total = str(eval(expr))
        equation.set(total)
        expr = total
    except:
        equation.set("Erreur")
        expr = ""

def effacer():
    global expr
    expr = ""
    equation.set("")


gui = Tk()
gui.configure(background="#FFF")
gui.title("Calculatrice")
gui.geometry("300x410")

equation = StringVar()
result = Label(gui, bg="#FFF", fg="#000", textvariable=equation, height=2, font=2)
result.grid(columnspan=4)
Boutons = [7, 8, 9, "*", 4, 5, 6, "-", 1, 2, 3, "+", 0, ".", "/", "="]
L = 1 
C = 0
for Bouton in Boutons:
    b = Label(gui, text=str(Bouton), bg="blue", fg="#FFF", height=4, width=10)
    b.bind("<Button-1>", lambda e, Bouton=Bouton: appuyer(Bouton))
    b.grid(row=L, column=C)
    C += 1 
    if C == 4:
        C = 0
        L += 1  
b = Label(gui, text="Effacer", bg="green", fg="#FFF", font=1, height=4, width=27)
b.bind("<Button-1>", lambda e: effacer())
b.grid(columnspan=4)
gui.mainloop()

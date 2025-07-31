# calculadorsimples.py
#calculadora simples 
from tkinter import *
from tkinter import ttk


#CORES
cor1 = "#1e1e1e"  #PRETO
cor2 = "#feffff" #white/branco
cor3 = "#38576b" #azul
cor4 = "#ECEFF1" #Cinzenta
cor5 = "#FFAB40" #Laranja


janela = Tk()
janela.title("Calculadora")
janela.geometry("300x300")
janela.config(bg=cor1)


frame_tela = Frame(janela, width=400, height=100,bg=cor3)
frame_tela.grid(row=0, column=0)


frame_corpo  = Frame(janela, width=400, height=300, bg=cor4)
frame_corpo.grid(row=1, column=0)


#variavel todos os valores
todos_valores= ''


# Função para receber valores
def entrar_valores(valor):
    global todos_valores
    todos_valores += str(valor)
    valor_visto.set(todos_valores)


#função limpar tela
def limpar_tela():
    global todos_valores
    todos_valores=""
    valor_visto.set("")




# Função para calcular
def calcular():
    global todos_valores
    try:
        resultado = str(eval(todos_valores))
        valor_visto.set(resultado)
        todos_valores = resultado
    except:
        valor_visto.set("Erro")
        todos_valores = ""
#variavel todos os valores
def calcular():
    global todos_valores
    resultado= eval(todos_valores)
    valor_visto.set(str(resultado))
    print(resultado)






#criar um label
valor_visto= StringVar()
valor_visto.set("0")
valor_texto=("resultado")


app_label = Label(frame_tela, textvariable=valor_visto, width=16, height=2, padx=7, relief=FLAT, anchor="e", bg=cor3, fg=cor2, font=("Arial", 20, "bold"))
app_label.place(x=0, y=0)


#criando blutton
#primeria fila
b_1= Button(frame_corpo,command=limpar_tela,text="C",width=17,height=2, bg=cor4 )
b_1.place(x=1,y=0)
b_2= Button(frame_corpo,command= lambda:entrar_valores("%"), text="%",width=10,height=2,bg=cor4 )
b_2.place(x=130,y=0)
b_3= Button(frame_corpo,command= lambda:entrar_valores("/"),text="/",width=16,height=2 ,bg=cor5)
b_3.place(x=210,y=0)


b_4= Button(frame_corpo,command= lambda:entrar_valores("7"),text="7",width=9,height=2, bg=cor4 )
b_4.place(x=1,y=40)
b_5= Button(frame_corpo,command= lambda:entrar_valores("8"),text="8",width=9,height=2,bg=cor4 )
b_5.place(x=70,y=40)
b_6= Button(frame_corpo,command= lambda:entrar_valores("9"),text="9",width=9,height=2,bg=cor4 )
b_6.place(x=140,y=40)
b_7= Button(frame_corpo,command= lambda:entrar_valores("*"),text="x",width=16,height=2 ,bg=cor5)
b_7.place(x=210,y=40)


b_8= Button(frame_corpo,command= lambda:entrar_valores("4"),text="4",width=9,height=2, bg=cor4 )
b_8.place(x=1,y=80)
b_9= Button(frame_corpo,command= lambda:entrar_valores("5"),text="5",width=9,height=2,bg=cor4 )
b_9.place(x=70,y=80)
b_10= Button(frame_corpo,command= lambda:entrar_valores("6"),text="6",width=9,height=2,bg=cor4 )
b_10.place(x=140,y=80)
b_11= Button(frame_corpo,command= lambda:entrar_valores("-"),text="-",width=16,height=2 ,bg=cor5)
b_11.place(x=210,y=80)


b_12= Button(frame_corpo,command= lambda:entrar_valores("1"),text="1",width=9,height=2, bg=cor4 )
b_12.place(x=1,y=120)
b_13= Button(frame_corpo,command= lambda:entrar_valores("2"),text="2",width=9,height=2,bg=cor4 )
b_13.place(x=70,y=120)
b_14= Button(frame_corpo,command= lambda:entrar_valores("3"),text="3",width=9,height=2,bg=cor4 )
b_14.place(x=140,y=120)
b_15= Button(frame_corpo,command= lambda:entrar_valores("+"),text="+",width=16,height=2 ,bg=cor5)
b_15.place(x=210,y=120)


b_16= Button(frame_corpo,command= lambda:entrar_valores("0"),text="0",width=17,height=2, bg=cor4 )
b_16.place(x=1,y=160)
b_17= Button(frame_corpo,command= lambda:entrar_valores("."),text=".",width=10,height=2,bg=cor4 )
b_17.place(x=130,y=160)
b_18= Button(frame_corpo,command= calcular,text="=",width=16,height=2 ,bg=cor5)
b_18.place(x=210,y=160)

janela.mainloop()


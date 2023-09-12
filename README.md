# calculatar
import tkinter as t
expression=""
def press(num):
    global expression
    expression=expression+str(num)
    equation.set(expression)
    
def equalpress():
    try:
        global expression
        total=str(eval(expression))
        equation.set(total)
        expression=""
    except:
        equation.set("Error")
        expression=""
        
def clear():
    global expression
    expression=""
    equation.set("")
    
    
if __name__=="__main__":
    r=t.Tk()
    r.configure(bg="gray")
    r.title("CALCULATAR")
    r.geometry("320x265")
    equation=t.StringVar()
expression_field=t.Entry(r,textvariable=equation)
expression_field.grid(columnspan=7,ipadx=97,ipady=20,)
    
button=t.Button(r,text="C",bg="gray",fg="red",width=10,height=2,command=clear).grid(row=1,column=0)
button1=t.Button(r,text="()",bg="gray",fg="light green",width=10,height=2,command=lambda: press("(  )")).grid(row=1,column=1)
button2=t.Button(r,text="%",bg="gray",fg="light green",width=10,height=2,command=lambda: press("%")).grid(row=1,column=2)
button3=t.Button(r,text="/",bg="gray",fg="light green",width=10,height=2,command=lambda: press("/")).grid(row=1,column=3)
button4=t.Button(r,text="7",bg="gray",fg="white",width=10,height=2,command=lambda: press(7)).grid(row=2,column=0)
button5=t.Button(r,text="8",bg="gray",fg="white",width=10,height=2,command=lambda: press(8)).grid(row=2,column=1)
button6=t.Button(r,text="9",bg="gray",fg="white",width=10,height=2,command=lambda: press(9)).grid(row=2,column=2)
button7=t.Button(r,text="X",bg="gray",fg="light green",width=10,height=2,command=lambda: press("*")).grid(row=2,column=3)
button8=t.Button(r,text="4",bg="gray",fg="white",width=10,height=2,command=lambda: press(4)).grid(row=3,column=0)
button9=t.Button(r,text="5",bg="gray",fg="white",width=10,height=2,command=lambda: press(5)).grid(row=3,column=1)
button10=t.Button(r,text="6",bg="gray",fg="white",width=10,height=2,command=lambda: press(6)).grid(row=3,column=2)
button11=t.Button(r,text="-",bg="gray",fg="light green",width=10,height=2,command=lambda: press("-")).grid(row=3,column=3)
button12=t.Button(r,text="1",bg="gray",fg="white",width=10,height=2,command=lambda: press(1)).grid(row=4,column=0)
button13=t.Button(r,text="2",bg="gray",fg="white",width=10,height=2,command=lambda: press(2)).grid(row=4,column=1)
button14=t.Button(r,text="3",bg="gray",fg="white",width=10,height=2,command=lambda: press(3)).grid(row=4,column=2)
button15=t.Button(r,text="+",bg="gray",fg="light green",width=10,height=2,command=lambda: press("+")).grid(row=4,column=3)
button16=t.Button(r,text="+/-",bg="gray",fg="white",width=10,height=2,command=lambda: press("+/-")).grid(row=5,column=0)
button17=t.Button(r,text="0",bg="gray",fg="white",width=10,height=2,command=lambda: press(0)).grid(row=5,column=1)
button18=t.Button(r,text=".",bg="gray",fg="white",width=10,height=2,command=lambda: press(".")).grid(row=5,column=2)
button19=t.Button(r,text="=",bg="green",fg="black",width=10,height=2,command=equalpress).grid(row=5,column=3)
r.mainloop()

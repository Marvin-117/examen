# examen
marvin Ismael Recinos Mazariegos 0907-19-6478
from tkinter import ttk
from tkinter import *

class Desk:
    def __init__(self, window):
        # Initializations
        
        #ancho
        ancho = 4000
        
        #alto
        alto = 3000
        
        
        self.wind = window

        #le asignamos el ancho y el alto 
        self.wind.geometry(str(ancho)+'x'+str(alto))

         
        self.wind.columnconfigure(0, weight=1)
        
        
        self.wind.title('El Marvin')
        
        #  un contenedor
        frame = LabelFrame(self.wind, text = "Examen")
        frame.grid(row = 0, column = 0, columnspan = 3, pady = 20)
        
        # etiqueta
        Label(frame, text = 'primer numero: ').place(x=80, y= 90)
        Label(frame, text = 'segundo numero: ').place(x=80, y= 90)
        Label(frame, text = 'tercer numero').place(x=80, y= 90)
        
        # input donde ingresar valores
        self.var1 = Entry(frame)
        self.var1.focus()
        self.var1.grid(row = 1, column = 1)
        
        # igual que arriba una etiqueta y un campo input para ingresar valores
        Label(frame, text = 'segundo numero: ').grid(row = 2, column = 0)
        self.var2 = Entry(frame)
        self.var2.grid(row = 2, column = 1)

        Label(frame, text = 'tercer numero: ').grid(row = 4, column = 0)
        self.var3 = Entry(frame)
        self.var3.grid(row = 4, column = 1)


        
        #boton para ejecutar la suma
        Button(frame, text = 'Sumar', command = self.sumar).place(x= 10, y= 5)

        #el boton de resta 
        Button(frame, text = 'Restar', command = self.Restar).place(x= 11, y= 6)

        # boton de multiplicacion 
        Button(frame, text = 'multiplicar', command = self.Multiplicacion)..place(x= 13, y= 8)

      

        #designamos un área para mensajes
        self.message = Label(text = '', fg = 'red')
        self.message.grid(row = 3, column = 0, columnspan = 2, sticky = W + E)
        
    #función para validar que los campos no esten en blanco
    def validation(self):
        return len(self.var1.get()) != 0 and len(self.var2.get()) != 0 and len(self.var3.get()) != 0
    
    # esta es la función que ejecuta la suma
    def sumar(self):
        if var1.get () == var2.get() == var3.get()
            resultado = float( self.var1.get() ) + float( self.var2.get() ) + float( self.var3.get()
            self.message['text'] = 'La suma de las 2 variables es: {}'.format(resultado)

        else:
            self.message['text'] = 'los campos son requeridos'
    
    # esta es la función que ejecuta la Resta
    def Restar(self):
        if self.validation():
            resultado = float( self.var1.get() ) - float( self.var2.get() )
            self.message['text'] = 'La Resta de las 2 variables es: {}'.format(resultado)
        else:
            self.message['text'] = 'los campos son requeridos'
    
    # esta es la función que ejecuta la multiplicacion 
    def Multiplicacion(self):
        if self.validation():
            resultado = float( self.var1.get() ) // float( self.var2.get() )
            self.message['text'] = 'La Multiplicacion  de las 2 variables es: {}'.format(resultado)
        else:
            self.message['text'] = 'los campos son requeridos'


#validamos si estamos en la aplicación inicial
if __name__ == '__main__':
    
    #asignamos la propiedad de tkinter a la variable window
    window = Tk()
    
    #en la variable app guardamos la clase Desk y le enviamos como parametro la ventana 
    app = Desk(window)

    #ejecutamos un mainloop para que se ejecute la ventana
    window.mainloop()

import platform
import os
import time
def LimpiarPantalla():
    
    time.sleep(2)
    if platform.system()=='Windows':
        os.system('cls')
    else:
        os.system('clear')

def Menu():
    print("MENU PRINCIPAL:")
    print("1) Lista Alumnos")
    print("2) Lista Entrenadores")
    print("3) Lista Padres")
    print("4) Inventario Balones")
    print("5) Inventario Petos")
    print("6) Inventario Conos")
    print("7) Inventario Redes")

def main():
    class Alumno:
        def __init__(self,nombre,edad,dorsal,posicion):
            self.nombre=nombre
            self.edad=edad
            self.dorsal=dorsal
            self.posicion=posicion
        def DarNombre(self):
            return self.nombre
        def DarEdad(self):
            return self.edad
        def DarDorsal(self):
            return self.dorsal
        def DarPosicion(self):
            return self.posicion
        def __str__(self) -> str:
            return "El alumno %s de edad %s con el dorsal %s tiene la posición %s" % (self.nombre,self.edad,self.dorsal,self.posicion)
    class Entrenador:
        def __init__(self,nombre,edad,CantJ,categoria):
            self.nombre=nombre
            self.edad=edad
            self.cantj=CantJ
            self.categoria=categoria
        def DarNombre(self):
            return self.nombre
        def DarEdad(self):
            return self.edad
        def DarCant(self):
            return self.cantj
        def DarCategoria(self):
            return self.categoria
        def __str__(self) -> str:
            return "El entrenador %s de edad %s cuenta con %s jugadores en la categoria %s" % (self.nombre,self.edad,self.cantj,self.categoria)
    class Padre:
        def __init__(self,nombre,edad,categoria,dorsal):
            self.nombre=nombre
            self.edad=edad
            self.categoria=categoria
            self.dorsal=dorsal
        def DarNombre(self):
            return self.nombre
        def DarEdad(self):
            return self.edad
        def DarCategoria(self):
            return self.categoria
        def DarDorsal(self):
            return self.dorsal
        def __str__(self) -> str:
            return "El padre %s de edad %s tiene a su hijo en la categoria %s con el dorsal %s" % (self.nombre,self.edad,self.categoria,self.dorsal)
    class Balon:
        def __init__(self,marca,numero,material,color):
            self.marca=marca
            self.numero=numero
            self.material=material
            self.color=color
        def DarMarca(self):
            return self.marca
        def DarNumero(self):
            return self.numero
        def DarMaterial(self):
            return self.material
        def DarColor(self):
            return self.color
        def __str__(self) -> str:
            return "Este balón %s numero %s de material %s es de color %s" % (self.marca,self.numero,self.material,self.color)
    class Peto:
        def __init__(self,marca,color,dorsal):
            self.marca=marca
            self.color=color
            self.dorsal=dorsal
        def DarMarca(self):
            return self.marca
        def DarColor(self):
            return self.color
        def DarDorsal(self):
            return self.dorsal
        def __str__(self) -> str:
            return "Este peto de marca %s y de color %s tiene el dorsal %s" % (self.marca,self.color,self.dorsal)
    class Cono:
        def __init__(self,marca,color,tamaño):
            self.marca=marca
            self.color=color
            self.tamaño=tamaño
        def DarMarca(self):
            return self.marca
        def DarColor(self):
            return self.color
        def DarTamaño(self):
            return self.tamaño
        def __str__(self) -> str:
            return "Este cono de marca %s y de color %s es de tamaño %s" % (self.marca,self.color,self.tamaño)
    class Red:
        def __init__(self,marca,color,diseño):
            self.marca=marca
            self.color=color
            self.diseño=diseño
        def DarMarca(self):
            return self.marca
        def DarColor(self):
            return self.color
        def DarDiseño(self):
            return self.diseño
        def __str__(self) -> str:
            return "Esta red de marca %s y de color %s tiene diseño de %s" % (self.marca,self.color,self.diseño)
    ListaAlumnos=[]
    ListaEntrenadores=[]
    ListaPadres=[]
    ListaBalones=[]
    ListaPetos=[]
    ListaConos=[]
    ListaRedes=[]
    print("Bienvenido a tu programa diseñado para una Academia de Fútbol")
    f=0
    while f == 0:
        print("1.Entrenador.\n2.Alumno.\n3.Padre de familia.")
        usuario=input("Selecciona el usuario que eres: ").lower()
        if usuario =="1" or usuario == "entrenador":
            n=0
            while n==0:
                Menu()
                elec=int(input("¿A que deseas acceder?: "))
                if elec==1:
                    cantN=int(input("Digita la cantidad de estudiantes que deseas ingresar: "))
                    i=0
                    while cantN!=i:
                        i+=1
                        print(f"ALUMNO #{i} ")
                        ListaAlumnos.append(Alumno(
                            str(input("Digite su nombre: ")),
                            int(input("Digite su edad: ")),
                            int(input("Digite su dorsal: ")),
                            str(input("Digite su posición: "))
                            ))
                        print("")
                elif elec==2:
                    cantN=int(input("Digita la cantidad de entrenadores que deseas ingresar: "))
                    i=0
                    while cantN!=i:
                        i+=1
                        print(f"ENTRENADOR #{i}: ")
                        ListaEntrenadores.append(Entrenador(
                            str(input("Digite su nombre: ").lower),
                            int(input("Digite su edad: ")),
                            int(input("Digite su cantidad de jugadores: ")),
                            str(input("Digite su categoria entrenada: "))
                            ))
                        print("")
                elif elec==3:
                    cantN=int(input("Digita la cantidad de padres que deseas ingresar: "))
                    i=0
                    while cantN!=i:
                        i+=1
                        print(f"PADRE #{i}: ")
                        ListaPadres.append(Padre(
                            str(input("Digite su nombre: ")),
                            int(input("Digite su edad: ")),
                            str(input("Digite la categoria de su hijo: ")),
                            int(input("Digite el dorsal de su hijo: "))
                            ))
                        print("")
                elif elec==4:
                    cantN=int(input("Digita la Cantidad de balones que deseas ingresar: "))
                    i=0
                    while cantN!=i:
                        i+=1
                        print(f"BALON #{i}: ")
                        ListaBalones.append(Balon(
                            str(input("Digite la marca del balon: ")),
                            int(input("Digite el número del balon: ")),
                            str(input("Digite el material del balón: ")),
                            str(input("Digite el color del balón: "))
                            ))
                        print("")
                elif elec==5:
                    cantN=int(input("Digita la Cantidad de petos que deseas ingresar: "))
                    i=0
                    while cantN!=i:
                        i+=1
                        print(f"PETO #{i}: ")
                        ListaPetos.append(Peto(
                            str(input("Digite la marca del peto: ")),
                            str(input("Digite el color del peto: ")),
                            int(input("Digite el dorsal que lleva el peto: "))
                            ))
                        print("")
                elif elec==6:
                    cantN=int(input("Digita la Cantidad de conos que deseas ingresar: "))
                    i=0
                    while cantN!=i:
                        i+=1
                        print(f"CONO #{i}: ")
                        ListaConos.append(Cono(
                            str(input("Digite la marca del cono: ")),
                            str(input("Digite el color del cono: ")),
                            str(input("Digite el tamaño del cono: "))
                            ))
                        print("")
                elif elec==7:
                    cantN=int(input("Digita la Cantidad de redes que deseas ingresar: "))
                    i=0
                    while cantN!=i:
                        i+=1
                        print(f"RED #{i}: ")
                        ListaRedes.append(Red(
                            str(input("Digite la marca de la red: ")),
                            str(input("Digite el color de la red: ")),
                            str(input("Digite el diseño de la red: "))
                            ))
                        print("")
                else:
                    print("Esta opcion es invalida")
                    input("")
                    LimpiarPantalla()

                stad=(input(f"¿Desea continuar añadiendo objetos al programa? S(Sí)/N(No)?: ")).lower()    
                if stad=="s":
                    n=0
                    LimpiarPantalla()
                elif stad=="n":
                    n=2
                    LimpiarPantalla()
                else:
                    print("Esa opción no existe, vuelve a intentarlo")
                    LimpiarPantalla()
            n = 0
            while n==0:
                print("Te encuentras en la sección de visualización de listas")
                Menu()
                elec=int(input("¿Que lista deseas ver?: "))
                if elec==1:
                    print("LISTA ALUMNOS: ")
                    i=0
                    cantN=len(ListaAlumnos)
                    while i!=cantN:
                        print(ListaAlumnos[i])
                        i+=1
                    print("")
                    print("")
                elif elec==2:
                    print("LISTA ENTRENADORES: ")
                    i=0
                    cantN=len(ListaEntrenadores)
                    while i!=cantN:
                        print(ListaEntrenadores[i])
                        i+=1
                    print("")
                    print("")
                elif elec==3:
                    print("LISTA PADRES: ")
                    i=0
                    cantN=len(ListaPadres)
                    while i!=cantN:
                        print(ListaPadres[i])
                        i+=1
                    print("")
                    print("")
                elif elec==4:
                    print("LISTA BALONES: ")
                    i=0
                    cantN=len(ListaBalones)
                    while i!=cantN:
                        print(ListaBalones[i])
                        i+=1
                    print("")
                    print("")
                elif elec==5:
                    print("LISTA PETOS: ")
                    i=0
                    cantN=len(ListaPetos)
                    while i!=cantN:
                        print(ListaPetos[i])
                        i+=1
                    print("")
                    print("")
                elif elec==6:
                    print("LISTA CONOS: ")
                    i=0
                    cantN=len(ListaConos)
                    while i!=cantN:
                        print(ListaConos[i])
                        i+=1
                    print("")
                    print("")
                elif elec==7:
                    print("LISTA REDES: ")
                    i=0
                    cantN=len(ListaRedes)
                    while i!=cantN:
                        print(ListaRedes[i])
                        i+=1
                    print("")
                    print("")
                else:
                    print("Esa opción no existe")
                stad=(input("¿Desea continuar viendo las listas? S(Sí)/N(No)?: "))
                if stad.lower() == "s":
                    n=0
                    LimpiarPantalla()
                elif stad.lower() == "n":
                    n=2
                    LimpiarPantalla()
                else:
                    print("Esa opción no existe, vuelve a intentarlo")
                    LimpiarPantalla()


        elif usuario == "2" or usuario == "alumno":
            n=0
            while n==0:
                print("Te encuentras en la sección de visualización de listas")
                Menu()
                elec=int(input("¿Que lista deseas ver?: "))
                if elec==1:
                    print("LISTA ALUMNOS: ")
                    i=0
                    cantN=len(ListaAlumnos)
                    while i!=cantN:
                        print(ListaAlumnos[i])
                        i+=1
                    print("")
                    print("")
                elif elec==2:
                    print("LISTA ENTRENADORES: ")
                    i=0
                    cantN=len(ListaEntrenadores)
                    while i!=cantN:
                        print(ListaEntrenadores[i])
                        i+=1
                    print("")
                    print("")
                elif elec==3:
                    print("LISTA PADRES: ")
                    i=0
                    cantN=len(ListaPadres)
                    while i!=cantN:
                        print(ListaPadres[i])
                        i+=1
                    print("")
                    print("")
                elif elec==4:
                    print("LISTA BALONES: ")
                    i=0
                    cantN=len(ListaBalones)
                    while i!=cantN:
                        print(ListaBalones[i])
                        i+=1
                    print("")
                    print("")
                elif elec==5:
                    print("LISTA PETOS: ")
                    i=0
                    cantN=len(ListaPetos)
                    while i!=cantN:
                        print(ListaPetos[i])
                        i+=1
                    print("")
                    print("")
                elif elec==6:
                    print("LISTA CONOS: ")
                    i=0
                    cantN=len(ListaConos)
                    while i!=cantN:
                        print(ListaConos[i])
                        i+=1
                    print("")
                    print("")
                elif elec==7:
                    print("LISTA REDES: ")
                    i=0
                    cantN=len(ListaRedes)
                    while i!=cantN:
                        print(ListaRedes[i])
                        i+=1
                    print("")
                    print("")
                else:
                    print("Esa opción no existe")
                stad=(input("¿Desea continuar viendo las listas? S(Sí)/N(No)?: "))
                if stad.lower() == "s":
                    n=0
                    LimpiarPantalla()
                elif stad.lower() == "n":
                    n=2
                    LimpiarPantalla()
                else:
                    print("Esa opción no existe, vuelve a intentarlo")
                    LimpiarPantalla()
            
        elif usuario  == "3" or usuario == "padre de familia":
            n=0
            while n==0:
                print("Te encuentras en la sección de visualización de listas")
                Menu()
                elec=int(input("¿Que lista deseas ver?: "))
                if elec==1:
                    print("LISTA ALUMNOS: ")
                    i=0
                    cantN=len(ListaAlumnos)
                    while i!=cantN:
                        print(ListaAlumnos[i])
                        i+=1
                    print("")
                    print("")
                elif elec==2:
                    print("LISTA ENTRENADORES: ")
                    i=0
                    cantN=len(ListaEntrenadores)
                    while i!=cantN:
                        print(ListaEntrenadores[i])
                        i+=1
                    print("")
                    print("")
                elif elec==3:
                    print("LISTA PADRES: ")
                    i=0
                    cantN=len(ListaPadres)
                    while i!=cantN:
                        print(ListaPadres[i])
                        i+=1
                    print("")
                    print("")
                elif elec==4:
                    print("LISTA BALONES: ")
                    i=0
                    cantN=len(ListaBalones)
                    while i!=cantN:
                        print(ListaBalones[i])
                        i+=1
                    print("")
                    print("")
                elif elec==5:
                    print("LISTA PETOS: ")
                    i=0
                    cantN=len(ListaPetos)
                    while i!=cantN:
                        print(ListaPetos[i])
                        i+=1
                    print("")
                    print("")
                elif elec==6:
                    print("LISTA CONOS: ")
                    i=0
                    cantN=len(ListaConos)
                    while i!=cantN:
                        print(ListaConos[i])
                        i+=1
                    print("")
                    print("")
                elif elec==7:
                    print("LISTA REDES: ")
                    i=0
                    cantN=len(ListaRedes)
                    while i!=cantN:
                        print(ListaRedes[i])
                        i+=1
                    print("")
                    print("")
                else:
                    print("Esa opción no existe")
                stad=(input("¿Desea continuar viendo las listas? S(Sí)/N(No)?: "))
                if stad.lower() == "s":
                    n=0
                    LimpiarPantalla()
                elif stad.lower() == "n":
                    n=2
                    LimpiarPantalla()
                else:
                    print("Esa opción no existe, vuelve a intentarlo")
                    LimpiarPantalla()
        stad=(input(f"¿Desea cambiar de usuario? S(Sí)/N(No)?: ")).lower()    
        if stad=="s":
            f=0
            LimpiarPantalla()
        elif stad=="n":
            f=2
            LimpiarPantalla()
        else:
            print("Esa opción no existe, vuelve a intentarlo")
            LimpiarPantalla()
    
    
if __name__=="__main__":
    main()

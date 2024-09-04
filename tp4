class JugadorDeFutbol:
    def __init__(self, nombre, edad, posicion, goles, premios):
        self.nombre = nombre
        self.edad = edad
        self.posicion = posicion
        self.goles = goles
        self.premios = premios

    def actualizar_informacion(self, nombre=None, edad=None, posicion=None):
        if nombre is not None:
            self.nombre = nombre
        if edad is not None:
            self.edad = edad
        if posicion is not None:
            self.posicion = posicion
        self.actualizacion_estadisticas()

    def calcular_promedio_goles(self, partidos_jugados):
        if partidos_jugados == 0:
            return 0
        return self.goles / partidos_jugados

    def es_goleador(self, umbral_goles):
        return self.goles >= umbral_goles

    def agregar_premio(self, premio):
        self.premios.append(premio)
        self.actualizacion_estadisticas()

    def eliminar_premio(self, premio):
        if premio in self.premios:
            self.premios.remove(premio)
            self.actualizacion_estadisticas()

    def actualizacion_informacion(self):
        return {
            'nombre': self.nombre,
            'edad': self.edad,
            'posicion': self.posicion,
            'goles': self.goles,
            'premios': self.premios
        }

    def actualizacion_estadisticas(self):
        print(f"Estadísticas actualizadas del jugador {self.nombre}.")

def main():
    jugadores = {}

    while True:
        print("\n¿Qué te gustaría hacer?")
        print("1. Crear un nuevo jugador de fútbol")
        print("2. Mostrar la información de un jugador existente")
        print("3. Actualizar la información de un jugador existente")
        print("4. Calcular el promedio de goles por partido de un jugador")
        print("5. Verificar si un jugador es un goleador")
        print("6. Agregar un premio o reconocimiento a un jugador")
        print("7. Eliminar un premio o reconocimiento de un jugador")
        print("8. Salir")

        opcion = input("Seleccione una opción (1-8): ")

        if opcion == '1':
            nombre = input("Ingrese el nombre del jugador: ")
            edad = int(input("Ingrese la edad del jugador: "))
            posicion = input("Ingrese la posición del jugador: ")
            goles = int(input("Ingrese la cantidad de goles del jugador: "))
            premios = input("Ingrese los premios del jugador (separados por coma): ").split(",")
            jugadores[nombre] = JugadorDeFutbol(nombre, edad, posicion, goles, premios)
            print(f"Jugador {nombre} creado exitosamente.")
        
        elif opcion == '2':
            nombre = input("Ingrese el nombre del jugador: ")
            if nombre in jugadores:
                informacion = jugadores[nombre].actualizacion_informacion()
                print(f"Información del jugador {nombre}: {informacion}")
            else:
                print("Jugador no encontrado.")
        
        elif opcion == '3':
            nombre = input("Ingrese el nombre del jugador: ")
            if nombre in jugadores:
                nuevo_nombre = input("Ingrese el nuevo nombre del jugador (deje en blanco para no cambiar): ")
                nueva_edad = input("Ingrese la nueva edad del jugador (deje en blanco para no cambiar): ")
                nueva_posicion = input("Ingrese la nueva posición del jugador (deje en blanco para no cambiar): ")
                jugadores[nombre].actualizar_informacion(
                    nombre=nuevo_nombre if nuevo_nombre else None,
                    edad=int(nueva_edad) if nueva_edad else None,
                    posicion=nueva_posicion if nueva_posicion else None
                )
                print(f"Información del jugador {nombre} actualizada.")
            else:
                print("Jugador no encontrado.")
        
        elif opcion == '4':
            nombre = input("Ingrese el nombre del jugador: ")
            if nombre in jugadores:
                partidos_jugados = int(input("Ingrese la cantidad de partidos jugados: "))
                promedio_goles = jugadores[nombre].calcular_promedio_goles(partidos_jugados)
                print(f"Promedio de goles de {nombre}: {promedio_goles}")
            else:
                print("Jugador no encontrado.")
        
        elif opcion == '5':
            nombre = input("Ingrese el nombre del jugador: ")
            if nombre in jugadores:
                umbral_goles = int(input("Ingrese el umbral de goles para ser considerado goleador: "))
                es_goleador = jugadores[nombre].es_goleador(umbral_goles)
                print(f"El jugador {nombre} {'es' if es_goleador else 'no es'} goleador.")
            else:
                print("Jugador no encontrado.")
        
        elif opcion == '6':
            nombre = input("Ingrese el nombre del jugador: ")
            if nombre in jugadores:
                premio = input("Ingrese el nombre del premio a agregar: ")
                jugadores[nombre].agregar_premio(premio)
                print(f"Premio {premio} agregado al jugador {nombre}.")
            else:
                print("Jugador no encontrado.")
        
        elif opcion == '7':
            nombre = input("Ingrese el nombre del jugador: ")
            if nombre in jugadores:
                premio = input("Ingrese el nombre del premio a eliminar: ")
                jugadores[nombre].eliminar_premio(premio)
                print(f"Premio {premio} eliminado del jugador {nombre}.")
            else:
                print("Jugador no encontrado.")
        
        elif opcion == '8':
            print("Saliendo del programa.")
            break
        
        else:
            print("Opción no válida, por favor seleccione una opción del 1 al 8.")

if __name__ == "__main__":
    main()

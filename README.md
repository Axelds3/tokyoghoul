class Personaje:
    def __init__(self, nombre, especie, alias, afiliaciones, descripcion, imagen_url):
        self.nombre = nombre
        self.especie = especie
        self.alias = alias
        self.afiliaciones = afiliaciones
        self.descripcion = descripcion
        self.imagen_url = imagen_url

personajes = [
    Personaje("Ken Kaneki", "Ghoul", ["Eyepatch", "One-Eyed Ghoul"], ["Anteiku", "Aogiri Tree"], "Protagonista principal de Tokyo Ghoul.", "https://example.com/images/ken_kaneki.jpg"),
    Personaje("Touka Kirishima", "Ghoul", ["Rabbit"], ["Anteiku", "Goat"], "Amiga de Kaneki y miembro activo de la resistencia Ghoul.", "https://example.com/images/touka_kirishima.jpg"),
    # Añade más personajes aquí según sea necesario
]

def obtenerPersonajes():
    return [vars(p) for p in personajes]

def principal():
    print("Bienvenido a la API de Tokyo Ghoul")
    print("Endpoint Disponible:")
    print("- GET /personajes -> Obtener lista de personajes")
    
    while True:
        print("Ingrese la solicitud (GET /personajes):")
        solicitud = input().strip()

        if solicitud == "GET /personajes":
            print(obtenerPersonajes())
        else:
            print("Solicitud inválida. Intente de nuevo.")

if __name__ == "__main__":
    principal()


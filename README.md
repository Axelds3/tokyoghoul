git init
# tokyoghoul
git add .
git commit -m "Initial commit"
git remote add origin <url-del-repositorio-en-github>
git push -u origin master
class Personaje:
    def __init__(self, nombre, especie, alias, afiliaciones, descripcion, imagen_url):
        self.nombre = nombre
        self.especie = especie
        self.alias = alias
        self.afiliaciones = afiliaciones
        self.descripcion = descripcion
        self.imagen_url = imagen_url

class Lugar:
    def __init__(self, nombre, ubicacion, descripcion):
        self.nombre = nombre
        self.ubicacion = ubicacion
        self.descripcion = descripcion

personajes = [
    Personaje("Ken Kaneki", "Ghoul", ["Eyepatch", "One-Eyed Ghoul"], ["Anteiku", "Aogiri Tree"], "Protagonista principal de Tokyo Ghoul.", "https://example.com/images/ken_kaneki.jpg"),
    Personaje("Touka Kirishima", "Ghoul", ["Rabbit"], ["Anteiku", "Goat"], "Amiga de Kaneki y miembro activo de la resistencia Ghoul.", "https://example.com/images/touka_kirishima.jpg")
]

lugares = [
    Lugar("Anteiku", "Tokyo", "Café dirigido por ghouls que sirve como refugio para ghouls pacíficos."),
    Lugar("Aogiri Tree Hideout", "Bajo tierra en Tokyo", "Base de operaciones de Aogiri Tree, una organización Ghoul extremista.")
    # Más lugares...
]


def obtenerPersonajes():
    return [vars(p) for p in personajes]

def obtenerLugares():
    return [vars(l) for l in lugares]

def principal():
    print("Bienvenido a la API de Tokyo Ghoul")
    print("Endpoints Disponibles:")
    print("- GET /personajes -> Obtener lista de personajes")
    print("- GET /lugares -> Obtener lista de lugares")
    
    while True:
        print("Ingrese la solicitud (GET /personajes o GET /lugares):")
        solicitud = input().strip()

        if solicitud == "GET /personajes":
            print(obtenerPersonajes())
        elif solicitud == "GET /lugares":
            print(obtenerLugares())
        else:
            print("Solicitud inválida. Intente de nuevo.")

if __name__ == "__main__":
    principal()

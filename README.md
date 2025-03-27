def registrar_vertices(vertices):
    """Registra vértices en el arreglo de vértices."""
    try:
        x = float(input("Ingrese la coordenada X: "))
        y = float(input("Ingrese la coordenada Y: "))
        z = float(input("Ingrese la coordenada Z: "))
        vertices.append((x, y, z))
        print("Vértice registrado con éxito.")
    except ValueError:
        print("Entrada inválida. Asegúrese de ingresar números.")

def registrar_caras(caras, vertices):
    """Registra caras en el arreglo de caras."""
    try:
        num_vertices = int(input("Ingrese el número de vértices de la cara: "))
        if num_vertices < 3:
            print("Una cara debe tener al menos 3 vértices.")
            return
        
        cara = []
        for i in range(num_vertices):
            vertice_idx = int(input(f"Ingrese el índice del vértice {i+1}: "))
            if vertice_idx < 0 or vertice_idx >= len(vertices):
                print("Índice de vértice inválido.")
                return
            cara.append(vertice_idx)
        caras.append(cara)
        print("Cara registrada con éxito.")
    except ValueError:
        print("Entrada inválida. Asegúrese de ingresar números enteros.")

def imprimir_figura(vertices, caras):
    """Imprime la estructura de la figura."""
    print("\nVértices:")
    for i, vertice in enumerate(vertices):
        print(f"  Vértice {i}: {vertice}")
    print("\nCaras:")
    for i, cara in enumerate(caras):
        print(f"  Cara {i}: {cara}")

def menu():
    """Menú principal del programa."""
    vertices = []
    caras = []
    
    while True:
        print("\n--- Menú ---")
        print("1. Registrar vértice")
        print("2. Registrar cara")
        print("3. Imprimir figura")
        print("4. Salir")
        
        opcion = input("Seleccione una opción: ")
        
        if opcion == '1':
            registrar_vertices(vertices)
        elif opcion == '2':
            registrar_caras(caras, vertices)
        elif opcion == '3':
            imprimir_figura(vertices, caras)
        elif opcion == '4':
            break
        else:
            print("Opción inválida. Intente de nuevo.")

if __name__ == "__main__":
    menu()
    

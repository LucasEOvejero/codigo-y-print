# print def ordenarDiccionario(diccionario_par, clave, descendente=True):
    if not isinstance(diccionario_par, dict) or clave not in diccionario_par:
        return None

    diccionario_ordenado = {}
    lista_indices_ordenados = sorted(range(len(diccionario_par[clave])), key=lambda x: diccionario_par[clave][x], reverse=descendente)

    for key, values in diccionario_par.items():
        diccionario_ordenado[key] = [values[i] for i in lista_indices_ordenados]

    return diccionario_ordenado


def listaEnteros(inicio, tamanio):
    return list(range(inicio, inicio + tamanio))


def dividirDosNumeros(dividendo, divisor):
    cociente = dividendo // divisor
    resto = dividendo % divisor
    return cociente, resto


class ClaseAnimal:
    def __init__(self, especie, color):
        self.Edad = 0
        self.Especie = especie
        self.Color = color

    def CumplirAnios(self):
        self.Edad += 1
        return self.Edad


def claseAnimal(especie, color):
    return ClaseAnimal(especie, color)


def exponente(numero, exponente):
    return numero ** exponente


def listaPrimos(desde, hasta):
    if not isinstance(desde, int) or not isinstance(hasta, int) or desde <= 0 or hasta <= 0:
        return None

    if hasta < desde:
        return []

    primos = []
    for num in range(desde, hasta + 1):
        if num > 1:
            for i in range(2, num):
                if num % i == 0:
                    break
            else:
                primos.append(num)

    return primos


def listaRepetidos(lista):
    if not isinstance(lista, list):
        return None

    lista_sin_repetir = list(set(lista))
    lista_tuplas = [(item, lista.count(item)) for item in lista_sin_repetir]

    return lista_tuplas


# Pruebas
dicc = {
    'clave1': ['c', 'a', 'b'],
    'clave2': ['casa', 'auto', 'barco'],
    'clave3': [1, 2, 3]
}
print(ordenarDiccionario(dicc, 'clave1'))  # Debe retornar {'clave1': ['a', 'b', 'c'], 'clave2': ['auto', 'barco', 'casa'], 'clave3': [2, 3, 1]}

print(listaEnteros(10, 5))  # Debe retornar [10, 11, 12, 13, 14]

print(dividirDosNumeros(10, 3))  # Debe retornar (3, 1)

animal = claseAnimal('perro', 'blanco')
print(animal.CumplirAnios())  # Debe retornar 1
print(animal.CumplirAnios())  # Debe retornar 2
print(animal.CumplirAnios())  # Debe retornar 3

print(exponente(10, 3))  # Debe retornar 1000

print(listaPrimos(7, 15))  # Debe retornar [7, 11, 13]
print(listaPrimos(100, 99))  # Debe retornar []
print(listaPrimos(1, 7))  # Debe retornar [1, 2, 3, 5, 7]

print(listaRepetidos([]))  # Debe retornar []
print(listaRepetidos(['hola', 'mundo', 'hola', 13, 14]))  # Debe retornar [('hola', 2), ('mundo', 1), (13, 1), (14, 1)]
print(listaRepetidos([1, 2, 2, 4]))  # Debe retornar [(1, 1), (2, 2), (4, 1)]

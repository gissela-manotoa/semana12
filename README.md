# semana12
#FUNCION 
def calcular_temperatura_promedio(datos):
    
    promedios = {}
    
    for ciudad, temperaturas in datos.items():
        total_temperaturas = sum(sum(semana) for semana in temperaturas)
        cantidad_dias = sum(len(semana) for semana in temperaturas)
        promedios[ciudad] = total_temperaturas / cantidad_dias if cantidad_dias > 0 else 0

    return promedios

# Datos de ejemplo: 3 ciudades con temperaturas registradas durante 4 semanas (7 días por semana)
datos_temperaturas = {
    "Ciudad A": [
        [22, 24, 20, 23, 25, 21, 22],  # Semana 1
        [23, 26, 24, 22, 25, 27, 23],  # Semana 2
        [21, 22, 23, 20, 19, 22, 24],  # Semana 3
        [26, 28, 25, 27, 26, 24, 23],  # Semana 4
    ],
    "Ciudad B": [
        [30, 32, 31, 29, 30, 31, 32],  # Semana 1
        [29, 28, 30, 31, 32, 30, 29],  # Semana 2
        [33, 34, 32, 31, 30, 32, 33],  # Semana 3
        [28, 27, 29, 30, 28, 27, 29],  # Semana 4
    ],
    "Ciudad C": [
        [15, 16, 14, 15, 17, 16, 15],  # Semana 1
        [14, 15, 13, 14, 15, 16, 14],  # Semana 2
        [16, 17, 15, 14, 16, 15, 14],  # Semana 3
        [18, 19, 17, 16, 18, 17, 16],  # Semana 4
    ],
}

# Llamada a la función y muestra de resultados
promedios = calcular_temperatura_promedio(datos_temperaturas)
for ciudad, promedio in promedios.items():
    print(f"{ciudad}: {promedio:.2f}°C")


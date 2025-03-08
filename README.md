# semana12
tareasemana12 matriz
import numpy as np

# Definir las ciudades, días de la semana y semanas
ciudades = ["Ciudad A", "Ciudad B", "Ciudad C"]
dias_semana = ["Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo"]
semanas = 4  # Supongamos que tenemos 4 semanas

# Crear una matriz 3D de temperaturas aleatorias entre 15 y 30 grados para cada ciudad y día
temperaturas = np.random.randint(15, 31, (len(ciudades), len(dias_semana), semanas))

# Calcular el promedio de temperaturas por ciudad y semana
promedio_temperaturas = []

for i in range(len(ciudades)):
    for j in range(semanas):
        promedio = np.mean(temperaturas[i, :, j])  # Promedio de los 7 días de la semana
        promedio_temperaturas.append((ciudades[i], f'Semana {j+1}', promedio))

# Mostrar los promedios
print("Promedio de temperaturas por ciudad y semana:")
for ciudad, semana, promedio in promedio_temperaturas:
    print(f"{ciudad} - {semana}: {promedio:.2f}°C")

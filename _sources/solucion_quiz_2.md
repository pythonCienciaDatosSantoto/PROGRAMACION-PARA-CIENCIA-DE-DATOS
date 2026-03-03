# ✅ Soluciones - Guía de Práctica de Fundamentos de Python

Aquí encontrarás las **soluciones propuestas** y sus respectivas **explicaciones detalladas** para cada uno de los 5 ejercicios de práctica.

---

## 🧩 Ejercicio 1: Sistema de Descuentos en Caja

### 🧠 Código propuesto
```python
try:
    edad = int(input("Ingrese su edad: "))
    valor_compra = float(input("Ingrese el valor de la compra: "))

    descuento = 0.0
    if edad < 18:
        descuento = 0.15
    elif 18 <= edad <= 65:
        if valor_compra > 100000:
            descuento = 0.10
    else:
        descuento = 0.20

    valor_final = valor_compra * (1 - descuento)

    if descuento > 0:
        print(f"Su compra tiene un descuento del {int(descuento * 100)}%. El total a pagar es: ${valor_final:,.2f}")
    else:
        print(f"No aplica ningún descuento. El total a pagar es: ${valor_compra:,.2f}")

except ValueError:
    print("Error: Por favor, ingrese un valor numérico válido para la edad y la compra.")
```

### 💡 Explicación
Se usan condicionales anidados para clasificar los descuentos según la edad y monto de compra. El bloque `try-except` hace robusto el programa ante errores de entrada no numérica.

---

## 🧩 Ejercicio 2: Clasificador de Notas

### 🧠 Código propuesto
```python
notas = [4.5, 2.8, 3.9, 1.5, 4.8, 3.0, 5.0, 2.1, 3.3]
aprobados = []
reprobados = []

for nota in notas:
    if nota >= 3.0:
        aprobados.append(nota)
    else:
        reprobados.append(nota)

print(f"Estudiantes aprobados: {len(aprobados)}")
print(f"Notas de aprobados: {aprobados}")
print(f"Estudiantes reprobados: {len(reprobados)}")
print(f"Notas de reprobados: {reprobados}")
```

### 💡 Explicación
Se recorren las notas y se clasifican con `append()` usando un `if`. Se reporta la cantidad y contenido de cada grupo.

---

## 🧩 Ejercicio 3: Gestión de Inventario de Cafetería

### 🧠 Código propuesto
```python
inventario = {"Café Americano": 20, "Té Chai": 15}

while True:
    print("\n--- Menú de Inventario ---")
    print("1. Añadir/Actualizar producto")
    print("2. Consultar inventario")
    print("3. Salir")

    opcion = input("Seleccione una opción: ")

    if opcion == '1':
        nombre = input("Nombre del producto: ")
        try:
            cantidad = int(input("Cantidad: "))
            inventario[nombre] = cantidad
            print(f"Producto '{nombre}' añadido/actualizado.")
        except ValueError:
            print("Error: La cantidad debe ser un número entero.")

    elif opcion == '2':
        print("\n--- Inventario Actual ---")
        if not inventario:
            print("El inventario está vacío.")
        else:
            for producto, stock in sorted(inventario.items()):
                print(f"{producto}: {stock} unidades")

    elif opcion == '3':
        print("Saliendo del sistema.")
        break
    else:
        print("Opción no válida. Por favor, intente de nuevo.")
```

### 💡 Explicación
El `while True` mantiene el menú activo hasta que el usuario elige salir. Se gestionan entradas con `input()` y el diccionario se actualiza directamente.

---

## 🧩 Ejercicio 4: Reporte de Asistentes Únicos

### 🧠 Código propuesto
```python
registros = [("Ana", 101), ("Juan", 102), ("Pedro", 103), ("Ana", 101), ("Maria", 104), ("Juan", 102)]

asistentes_unicos = set(registros)

print(f"Número de asistentes únicos: {len(asistentes_unicos)}")

lista_final_nombres = sorted([nombre for nombre, _ in asistentes_unicos])
print(f"Lista final de asistentes: {lista_final_nombres}")
```

### 💡 Explicación
Se usa un `set` para eliminar duplicados automáticamente. Luego, se extraen los nombres únicos con comprensión de listas y se ordenan con `sorted()`.

---

## 🧩 Ejercicio 5: Calculadora de Promedio Robusta

### 🧠 Código propuesto
```python
notas = []

while True:
    entrada = input("Ingrese una nota (o 'fin' para terminar): ")
    if entrada.lower() == 'fin':
        break
    try:
        nota_valida = float(entrada)
        notas.append(nota_valida)
    except ValueError:
        print("Error: Por favor, ingrese un número válido.")

if notas:
    promedio = sum(notas) / len(notas)
    print(f"El promedio de las notas es: {promedio}")
else:
    print("No se ingresaron notas válidas para calcular el promedio.")
```

### 💡 Explicación
Se garantiza que solo se usen entradas válidas. El promedio se calcula únicamente si hay notas válidas, evitando errores como división por cero.

---

---

<div style="display: flex; justify-content: space-between; margin-top: 2rem;">

<a href="quiz_conocimientos_2.html" style="padding: 10px 20px; background-color: #6d28d9; color: white; text-decoration: none; border-radius: 8px;">
⬅️ Volver al Quiz
</a>

</div>

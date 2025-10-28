#!/usr/bin/env python3
# Calculadora básica de línea de comandos

def sumar(a, b): return a + b
def restar(a, b): return a - b
def multiplicar(a, b): return a * b
def dividir(a, b):
    if b == 0:
        raise ValueError("No se puede dividir por cero.")
    return a / b

operaciones = {
    "1": ("Sumar", sumar),
    "2": ("Restar", restar),
    "3": ("Multiplicar", multiplicar),
    "4": ("Dividir", dividir),
}

def main():
    print("Calculadora simple")
    for k, v in operaciones.items():
        print(f"{k}. {v[0]}")
    opcion = input("Elige una operación: ").strip()
    if opcion not in operaciones:
        print("Opción inválida.")
        return
    try:
        a = float(input("Primer número: "))
        b = float(input("Segundo número: "))
        resultado = operaciones[opcion][1](a, b)
        print(f"Resultado: {resultado}")
    except ValueError as e:
        print("Error:", e)

if __name__ == "__main__":
    main()

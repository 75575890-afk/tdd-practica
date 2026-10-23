# Práctica TDD - Semana 10

Construcción de Software - Universidad Continental

Integrantes:
- Eduardo Puma Ccorimanya

## Qué es TDD

TDD (Test-Driven Development) es una forma de programar en la que primero se
escribe el test y después el código. Se trabaja en ciclos cortos de tres pasos:

1. **Red**: se escribe un test para algo que todavía no existe. Al correrlo, falla.
2. **Green**: se escribe el código mínimo para que ese test pase.
3. **Refactor**: se mejora el código o se agregan tests de refuerzo sin cambiar
   lo que hace, verificando que todo siga en verde.

## Cómo lo aplicamos

### Ejercicio 1: FizzBuzz
Construimos la función `fizzbuzz(n)` en 5 ciclos:
1. Números normales: retorna el número como texto.
2. Fizz: divisibles entre 3.
3. Buzz: divisibles entre 5.
4. FizzBuzz: divisibles entre 15. Aquí el test falló porque 15 entraba primero
   al caso del 3, así que movimos esa condición arriba.
5. Refactor: test con `subTest` que revisa varios números a la vez.

### Ejercicio 2: Validador de contraseñas
Construimos `validar_password(pwd)` con un ciclo por cada regla:
1. Mínimo 8 caracteres.
2. Al menos una mayúscula.
3. Al menos una minúscula.
4. Al menos un dígito.
5. Al menos un carácter especial (!@#$%^&*).
6. Refactor: tests integrales para una contraseña válida, una con varios errores
   y varios casos con `subTest`.

En cada ciclo hicimos un commit en la fase Red y otro en la fase Green, así el
historial muestra cómo fue creciendo el código.

## Estructura

    tdd-practica/
    ├── fizzbuzz/
    │   ├── __init__.py
    │   ├── fizzbuzz.py
    │   └── test_fizzbuzz.py
    ├── validador/
    │   ├── __init__.py
    │   ├── validador.py
    │   └── test_validador.py
    ├── .gitignore
    └── README.md

## Cómo correr los tests

Desde la carpeta `tdd-practica`:

    python -m unittest discover -v

Resultado: 14 tests, todos en OK.
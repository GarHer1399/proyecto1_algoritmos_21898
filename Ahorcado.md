Se presenta el codigo para el juego de Ahorcado en los lenguajes de programacion solicitados y pseudocodigo.

**PSEUDOCODIGO**

*INICIO DEL JUEGO:*
Elegir una palabra  ["COMPUTACION"]
Inicializar variables:
INTENTOS RESTANTES = 6
PALABRA ADIVINADA = "______"  

MIENTRAS INTENTOS RESTANTES > 0 Y PALABRA ADIVINADA CONTIENE "_":
Mostrar PALABRA ADIVINADA
Mostrar "INTENTOS RESTANTES:", INTENTOS RESTANTES
Obtener una LETRA INGRESADA POR EL USUARIO

 *SI LA LETRA ESTÁ EN LA PALABRA SECRETA:*
 Actualizar PALABRA ADIVINADA con la LETRA(S) ADIVINADA(S)
Mostrar "¡CORRECTO! LA LETRA ESTÁ EN LA PALABRA."

*EN CASO CONTRARIO:*
Restar 1 a INTENTOS RESTANTES
Mostrar "INCORRECTO. LA LETRA NO ESTÁ EN LA PALABRA."

*MOSTRAR EL RESULTADO DEL JUEGO:*
*SI PALABRA ADIVINADA NO CONTIENE "_":*
Mostrar "¡FELICIDADES! HAS ADIVINADO LA PALABRA:", PALABRA ADIVINADA

*EN CASO CONTRARIO:*
Mostrar "PERDISTE. LA PALABRA SECRETA ERA:", PALABRA SECRETA

FIN

---------------------------------------------------------------------------------------------------------------------------------------
# Inicia el proceso

**PYTHON**

import random

palabras = ["computacion"]

palabraSecreta = random.choice(palabras)

intentosMaximos = 6
intentosRestantes = intentosMaximos
letrasAdivinadas = ["_"] * len(palabraSecreta)
haAdivinado = False

while intentosRestantes > 0 and not haAdivinado:
    print("Palabra a adivinar:", " ".join(letrasAdivinadas))
    print("Intentos restantes:", intentosRestantes)

    letra = input("Ingresa una letra: ").lower()

    if len(letra) == 1 and letra.isalpha():
        letraAdivinada = False
        for i in range(len(palabraSecreta)):
            if palabraSecreta[i] == letra:
                letrasAdivinadas[i] = letra
                letraAdivinada = True

        if letraAdivinada:
            print("¡Correcto! La letra está en la palabra.")
        else:
            print("Incorrecto. La letra no está en la palabra.")
            intentosRestantes -= 1

        if "".join(letrasAdivinadas) == palabraSecreta:
            haAdivinado = True
            print("¡Felicidades! Has adivinado la palabra:", palabraSecreta)

# Mostrar el resultado del juego
if not haAdivinado:
    print("Perdiste. La palabra secreta era:", palabraSecreta)
---------------------------------------------------------------------------------------------------------------------------------------------

**C++**

#include <iostream>
#include <string>
#include <ctime>

using namespace std;

int main() {
    string palabraSecreta = "computacion";

    int intentosMaximos = 6;
    int intentosRestantes = intentosMaximos;
    string letrasAdivinadas(palabraSecreta.length(), '_');
    bool haAdivinado = false;

    while (intentosRestantes > 0 && !haAdivinado) {
        cout << "Palabra a adivinar: " << letrasAdivinadas << endl;
        cout << "Intentos restantes: " << intentosRestantes << endl;

        char letra;
        cout << "Ingresa una letra: ";
        cin >> letra;

        bool letraAdivinada = false;
        for (int i = 0; i < palabraSecreta.length(); i++) {
            if (palabraSecreta[i] == letra) {
                letrasAdivinadas[i] = letra;
                letraAdivinada = true;
            }
        }

        if (letraAdivinada) {
            cout << "¡Correcto! La letra esta en la palabra." << endl;
        } else {
            cout << "La letra no esta en la palabra." << endl;
            intentosRestantes--;
        }

        if (palabraSecreta == letrasAdivinadas) {
            haAdivinado = true;
            cout << "¡Felicidades! Has adivinado la palabra: " << palabraSecreta << endl;
        }
    }

    if (!haAdivinado) {
        cout << "Perdiste. La palabra secreta era: " << palabraSecreta << endl;
    }

    return 0;
}


Se presenta el codigo para obtener los posibles Triples Pitagoricos en los lenguajes de programacion solicitados y pseudocodigo.

**PSEUDOCODIGO**


INICIO

"TRIPLES DE PITÁGORAS"
DECLARAR VARIABLES COMO NUMEROS ENTEROS, (A,B,C Y CONTADOR)

PARA A DESDE 1 HASTA 500:
PARA B DESDE 1 HASTA 500:
PARA C DESDE 1 HASTA 500:
           
SI (A * A + B * B) = C * C ENTONCES

CUANDO SE CUMPLA EL TRIPLE DE PITAGORAS ESCRIBIR
"Triple de Pitágoras:", A, ",", B, ",", C
CUANDO SE ESCRIBA UN RESULTADO SUMAR 1 EN EL CONTADOR DE COMBINACIONES
contador <- contador + 1

CUANDO SE ENCUENTREN TODAS LAS COMBINACIONES ESCRIBIR

 "TOTAL DE TRIPLES DE PITÁGORAS:", contador


FIN

---------------------------------------------------------------------------------------------------------------------------------------
# Inicia el proceso

**PYTHON**


```python
print("A continuación verán la lista de números enteros que cumplen con un triple pitagórico")
print()
contador = 0   # Para saber el número de posibles combinaciones

for A in range(1, 501):
    for B in range(1, 501):
        for C in range(1, 501):
            if A**2 + B**2 == C**2:      #Ecuación pitagórica 
                print(f"El grupo de enteros cumple la condición: {A}  {B}  = {C}")
                print()
                contador += 1

print(f"El total de triples de Pitágoras es: {contador}")
print()


---------------------------------------------------------------------------------------------------------------------------------------------

**C++**


#include <iostream>

int main() {
    std::cout << "A CONTINUACION VERAN LA LISTA DE NUMEROS ENTEROS QUE CUMPLEN CON UN TRIPLE PITAGORICO" << std::endl;
    std::cout << std::endl;

    int contador = 0;   // PARA SABER EL NUMERO DE POSIBLES COMBINACIONES

    for (int A = 1; A <= 500; A++) {
        for (int B = 1; B <= 500; B++) {
            for (int C = 1; C <= 500; C++) {
                if (A*A + B*B == C*C) {  // ECUACION PITAGORICA 
                    std::cout << "El Grupo de Enteros Cumple La Condición: " << A << "  " << B << "  = " << C << std::endl;
                    std::cout << std::endl;
                    contador++;
                }
            }
        }
    }

    std::cout << "EL TOTAL DE TRIPLES DE PITAGORAS ES: " << contador << std::endl;
    std::cout << std::endl;

    return 0;
}

# Actividad 1: representación de tokens de CompInt en C

## Identificación
- Matrícula: 10240041
- Nombre completo: DIEGO DECIDERIO GARCÍA
- Asignatura: Programación de Sistemas
- Actividad: 1

## Descripción
Programa en C que carga lexemas, los representa mediante enum y struct,
los almacena en un arreglo y muestra un resumen de categorías.

## Estructura
- inspector_tokens.c: código fuente.
- pruebas/: archivos de entrada.
- .gitignore: excluye ejecutables, objetos y archivos generados.

## Compilación
gcc -std=c11 -Wall -Wextra -Wpedantic inspector_tokens.c -o inspector_tokens

## Ejecución
./inspector_tokens pruebas/valido.tokens

## Casos de prueba
- **válido**: 12 tokens, estado 0
- **frontera 63**: ID de 63 caracteres, estado 0
- **frontera 64**: rechazo, estado 2
- **capacidad**: 33 tokens, rechazo, estado 2
- **confusión**: print→PRINT, printx→ID, estado 0
- **desconocido**: @ → DESCONOCIDO, estado 1
- **inexistente**: error de apertura, estado 2
- **regresión**: int, x, ; → estado 0
- **modificación**: while→WHILE, whilex→ID, estado 0

## Resultados
Todos los casos obligatorios y la modificación producen las salidas y
estados de salida esperados. Compilación sin advertencias ni errores.

## URL del repositorio
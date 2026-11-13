# Integrated-Itinerary-and-Fare-Engine---Metro-System-of-the-Valle-de-Aburra

## Team Mmbers

- Sebastian Ramirez Muñoz
- Santiago Taborda Garcia

## Project Description

This project implements an integrated itinerary and fare engine for the Metri System of the Valle de Aburra using C++17

It models different transport modes and passenger profiles, calculates fares, applies the integration rules, and generates reports using STL algorithms

## Requirements

- C++17 compiler
- g++

## How to Compile and Run

Compile the program using:

```bash
g++ -std=c++17 -Wall -Wextra -o practice main.cpp
```

Run the prograsm:

```bash
./practice
```

## Preguntas de defensa

### 1. ¿Por qué el destructor de la clase base debe ser virtual?

Si el destructor de "TransportMode" no es virtual, eliminar un objeto de una clase derivada mediante un puntero de la clase base puede provocar un comportamiento indefinido. El destructor de la clase derivada podría no ejecutarse correctamente.

Declarar el destructor como virtual garantiza que se llame al destructor correcto cuando se utiliza el polimorfismo. Esto es importante porque la clase "Network", almacena los modos de transporte utilizando "std::unique_ptr<TransportMode>".

### 2. ¿Por qué es preferible una clase abstracta con funciones virtuales puras en lugar de una enumeración y una estructura switch?

Una clase abstracta permite que cada modo de transporte implemente su propio comportamiento mediante funciones virtuales. Esto hace que el código sea más flexible y permite utilizar el polimorfismo.

Con una enumeración y una estructura "switch", agregar un nuevo modo de transporte requeriría modificar la lógica condicional en varios lugares. En cambio, con el polimorfismo, los nuevos modos pueden implementar su propio comportamiento sin necesidad de modificar el código existente que utiliza la clase base.

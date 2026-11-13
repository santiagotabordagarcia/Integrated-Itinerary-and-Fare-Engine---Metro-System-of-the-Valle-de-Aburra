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

## Defence Questions

### 1. Why must the base class desctructor be virtual?

If the destructor of TransportMode is not virtual, deleting a derived object through a base-class pointer can cause undefined behavior. The derived class destructor may not be called correctly

Declaring the destructor as virtual ensures that the correct destructor is called when using polymorphism. This is important because the Network class stores transport modes using std::unique_ptr<TransportMode>.

### 2. Why is an abstract class with pure virtual functions preferable to an enumeration and a switch statement?

An abstract class allows each transport mode to implements its own behavior through virtual functions. This makes the code more flexible and supports polymorphism.

With an enumeation and a switch statement, adding a new transport mode would require modifying the conditional logic in several places. With polymorphism, new modes can implement their own behavior without changing the existing code that uses the base class.

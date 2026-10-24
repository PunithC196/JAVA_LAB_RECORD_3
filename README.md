# LAB 3 – OOPS using Java

**Name:** Punith C
**USN:** 1BF25CS196
**Topic:** Abstract classes, abstract methods and method overriding

This folder contains the two Java programs from LAB 3, along with the lab record document and its screenshots.

## Contents

| File | Description |
|---|---|
| `AbstractEmployee.java` | Abstract class `Employee` with `HR` and `Manager` subclasses that each print their own salary |
| `EnergyManagement.java` | Abstract class `EnergyResource` with `SolarEnergy` and `WindEnergy` subclasses that calculate efficiency |
| `LAB-3-OOPS-JAVA.docx` | Lab record: code screenshots, explanations, output screenshots, verification |
| `LAB-3-OOPS-JAVA-images.zip` | The five trimmed screenshots used in the record, numbered in order |

## Requirements

- Java Development Kit (JDK) installed, with `javac` and `java` available in the command line
- Windows Command Prompt, or any terminal

Check your setup with:

```
javac -version
java -version
```

## How to run

Open Command Prompt and move into the project folder:

```
cd C:\Users\admin\Desktop\1BF25CS196-OOPS-JAVA
```

### Program 1: AbstractEmployee

```
javac AbstractEmployee.java
java AbstractEmployee
```

Expected output:

```
--- Employee Salary Details ---
HR Salary: Rs. 50,000 per month
Manager Salary: Rs. 85,000 per month
--------------------------------
```

### Program 2: EnergyManagement

```
javac EnergyManagement.java
java EnergyManagement
```

Expected output:

```
--- Solar Details ---
ID: SOL-101
Name: EcoSolar Array
Energy: 1200.0 KW
Solar Efficiency: 24.0%

--- Wind Details ---
ID: WIND-202
Name: GaleForce Turbines
Energy: 2400.0 KW
Wind Efficiency: 30.0%
```

## How the programs work

### AbstractEmployee

- `Employee` is an abstract class with one abstract method, `salary()`.
- `HR` and `Manager` extend `Employee` and override `salary()` with their own amounts.
- `main` stores both objects in `Employee` variables and calls `salary()`, so the same call gives a different result for each object (polymorphism).

### EnergyManagement

- `EnergyResource` is an abstract class holding `sourceId`, `sourceName` and `energyGenerated` as `protected` fields.
- It has an abstract `calculateEfficiency()` and a normal `displayDetails()`.
- `SolarEnergy` calculates efficiency as `(energyGenerated / 5000) * 100`; `WindEnergy` uses `8000` instead.
- Each subclass overrides `displayDetails()`, calls `super.displayDetails()` first, then prints its own efficiency line.

## Concepts covered

- Abstraction (abstract classes and methods)
- Inheritance (`extends`)
- Method overriding (`@Override`)
- Constructor chaining (`super(...)`)
- Encapsulation with `protected` fields
- Runtime polymorphism

## Notes

- Each file name must match its `public` class (`AbstractEmployee.java`, `EnergyManagement.java`).
- Run with `java ClassName`, without the `.java` extension. Typing just `AbstractEmployee.java` at the prompt does not run the program; it only opens the file in the default editor.
- Efficiency capacities (5000 and 8000) are written directly in the code. Move them into variables if you want to change them easily.

*This project has been created as part of the 42 curriculum by rmanzana*

# C++ Module 03 — Inheritance

## Description

Fourth module of the 42 C++ piscine. It introduces **inheritance** through a family of robots: a base `ClapTrap` class and several derived classes that reuse and extend it, ending with the famous **diamond problem** and its solution, virtual inheritance.

All the code follows the **C++98** standard and compiles with `c++ -Wall -Wextra -Werror -std=c++98`.

## Exercises

| Exercise | Program | Description |
|---|---|---|
| `ex00` — Aaaaand... OPEN! | `ClapTrap` | The base `ClapTrap` class, with a name, hit points, energy points and attack damage, and the actions `attack()`, `takeDamage()` and `beRepaired()`. Attacking and repairing cost energy, and a robot with no hit points or energy can't act. |
| `ex01` — Serena, my love! | `ScavTrap` | `ScavTrap` **inherits** from `ClapTrap` with different stats, its own `attack()` message and a special ability, `guardGate()`. Shows the **construction / destruction chaining** order: base first on construction, derived first on destruction. |
| `ex02` — Repetitive work | `FragTrap` | `FragTrap`, another derived class with its own stats and the `highFivesGuys()` ability. |
| `ex03` — Now it's weird! | `DiamondTrap` | `DiamondTrap` inherits from **both** `ScavTrap` and `FragTrap`. Without care, it would contain two copies of `ClapTrap`; **virtual inheritance** makes them share a single one. It takes stats from both parents and has a `whoAmI()` function that prints its own name and its `ClapTrap` name. |

## Key concepts

- **Inheritance:** `class ScavTrap : public ClapTrap`, reusing the base class's attributes and functions.
- **`protected` members:** accessible to derived classes, but not from outside.
- **Constructor and destructor chaining** in inheritance hierarchies.
- **Function hiding / redefinition** in derived classes.
- **Multiple inheritance and the diamond problem**, solved with **virtual inheritance** (`class ScavTrap : virtual public ClapTrap`).
- Compiling with `-Wshadow` / `-Wno-shadow` to detect attributes with the same name in different classes.

## Instructions

Each exercise has its own `Makefile`:

```bash
cd ex03
make
./DiamondTrap
```

`make clean`, `make fclean` and `make re` are available in every exercise.

## Resources

- [cplusplus.com — Inheritance](https://cplusplus.com/doc/tutorial/inheritance/)
- [LearnCpp.com — Order of construction of derived classes](https://www.learncpp.com/cpp-tutorial/order-of-construction-of-derived-classes/)
- [isocpp.org FAQ — Multiple and virtual inheritance](https://isocpp.org/wiki/faq/multiple-inheritance)
- [Diamond problem — Wikipedia](https://en.wikipedia.org/wiki/Multiple_inheritance#The_diamond_problem)

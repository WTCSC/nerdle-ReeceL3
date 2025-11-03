# Nerdle - Math Equation Guessing Game

Nerdle is a command-line game inspired by Wordle, where you guess 8-character mathematical equations instead of words. Sharpen your math skills while having fun trying to solve equations in limited attempts!

---

## Table of Contents

- [Overview](#overview)  
- [Gameplay](#gameplay)  
- [Installation](#installation)  
- [Running the Game](#running-the-game)  
- [Decision tree](#game-structure)   

---

## Overview

In Nerdle, the player attempts to guess a randomly generated math equation of the form:


- Each equation is exactly 8 characters long.  
- Players have **6 attempts** to guess the correct equation.  
- Feedback is provided after each guess using color-coded hints:
  - **Green**: Correct character in the correct position  
  - **Yellow**: Correct character but in the wrong position  
  - **Gray**: Character not in the equation  

---

## Gameplay

1. Start the game, and a random equation is generated.  
2. Enter guesses in the exact 8-character format (e.g., `12+34=46`).  
3. After each guess, feedback will guide you:
   - `G` (green) = correct position  
   - `Y` (yellow) = correct character, wrong position  
   - `B` (gray) = character not present  

4. Continue guessing until you solve the equation or run out of attempts.  
5. After the game ends, you can choose to play again.

**Example:**

Target equation: `12+34=46`  
Guess: `15+35=50`  

Feedback:


---

## Installation

1. Ensure Python 3.7+ is installed on your system.  
2. Clone this repository:

```
git clone https://github.com/yourusername/nerdle.git
cd nerdle 
```
# How to run

1. Open your terminal and type 
```
python nerdle.py
```
# Decision tree
```
                 ┌─────────────────────────────┐
                 │ Start: Generate Equation     │
                 └─────────────┬───────────────┘
                               │
                               ▼
                  ┌─────────────────────────┐
                  │ Choose Random Operation │
                  └─────────┬───────────────┘
                            │
        ┌───────────┬───────┴───────┬───────────┐
        ▼           ▼               ▼           ▼
   Addition        Subtraction   Multiplication Division
        │              │             │           │
        ▼              ▼             ▼           ▼
Generate num1, num2 Generate num1, num2  Generate num1,num2 Generate num1,num2
and result         (num1>num2?)       and result   (num1*num2)
        │              │             │           │
        ▼              ▼             ▼           ▼
  Equation =      Equation =     Equation =   Equation =
  num1+num2=result num1-num2=res  num1*num2=res num1/num2=res
        │              │             │           │
        └─────┬────────┴─────────────┴───────────┘
              │
              ▼
     Is equation 8 chars long?
              │
       ┌──────┴───────┐
       │ Yes          │ No
       ▼              ▼
  Return Equation  Retry with new operation
```
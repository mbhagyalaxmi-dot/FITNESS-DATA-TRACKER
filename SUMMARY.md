# Project Summary: Fitness Data Tracker (PS No. 70)

**Institution:** Rungta International Skills University — B.Tech CSE
**File:** `fitness_tracker.py`
**Language:** Python 3 (with optional Matplotlib)

## Purpose

A menu-driven console application that lets a user log daily steps and calories, measure progress against a 10,000-step daily goal, compute BMI, and plot step history.

## Design Overview

- **Data storage:** two parallel lists, `steps_list` and `calories_list`, where index `i` holds Day `i+1`. Data lives in memory for the session.
- **Constant:** `GOAL = 10000` steps per day.
- **Structure:** small single-purpose helper functions for input and calculations, separate menu-action functions for output, and a `main()` loop for the menu.

## Features

1. **Add record:** validates steps and calories, saves them, and reports the day number, whether the goal was met, and the percentage of the goal reached.
2. **Weekly summary:** average steps, total calories, best day (with its steps), and goal days out of total days.
3. **BMI calculator:** BMI = weight / height², classified as Underweight (<18.5), Normal (<25), Overweight (<30), or Obese (30+).
4. **Bar chart:** Matplotlib bar chart of daily steps with a red dashed goal line.
5. **Exit:** ends the program.

## Key Implementation Points

- `read_whole_number` uses `str.isdigit()` to reject negatives, decimals, and letters, returning `None` on bad input.
- `read_positive_float` uses `try/except ValueError` and requires a value greater than zero.
- Matplotlib is imported inside `try/except ImportError`, so the program runs without it and only option 4 shows an install hint.
- Both values are validated before either list is appended, so the two lists always stay the same length.
- Empty-data cases (summary and chart) show a friendly message instead of crashing on `max()` or division by zero.

## Concepts Demonstrated

- Functions and modular design
- Lists and list comprehensions / generator expressions
- Conditional logic and loops
- Input validation and exception handling
- f-string formatting
- Third-party library use (Matplotlib)
- The `if __name__ == "__main__"` entry point

## Limitations and Possible Improvements

- Data is lost on exit; saving to a CSV or JSON file would make it persistent.
- Records are not tied to calendar dates.
- The summary covers all entered days, not strictly a 7-day window.
- Calories could also be charted or compared against a target.
- Weight and height are not remembered between BMI calculations.

## How to Run

```bash
pip install matplotlib
python fitness_tracker.py
```

# Fitness Data Tracker (PS No. 70)

**Rungta International Skills University — B.Tech CSE**

A simple menu-driven command-line program in Python that helps you track daily steps and calories, review your weekly progress, calculate BMI, and visualize your activity with a bar chart.

## Features

| Option | Feature | Description |
|--------|---------|-------------|
| 1 | Add record | Enter steps and calories for the day; checks progress against the 10,000-step goal |
| 2 | Summary | Shows average steps, total calories, best day, and number of goal days |
| 3 | BMI | Calculates BMI from weight (kg) and height (m) and gives the category |
| 4 | Chart | Displays a Matplotlib bar chart of daily steps with a goal line |
| 5 | Exit | Quits the program |

## Requirements

- Python 3.7 or later
- Matplotlib (only needed for the chart, option 4)

```bash
pip install matplotlib
```

The program still runs without Matplotlib. Only option 4 needs it, and the program prints install instructions if it is missing.

## How to Run

```bash
python fitness_tracker.py
```

## Usage

```
===== Fitness Data Tracker =====
1. Add record
2. Summary
3. BMI
4. Chart
5. Exit
Menu option:
```

### Example session

```
Menu option: 1
Steps: 12000
Calories: 2100
Record saved for Day 1. Goal achieved: Yes (120.00% of goal)

Menu option: 1
Steps: 7500
Calories: 1900
Record saved for Day 2. Goal achieved: No (75.00% of goal)

Menu option: 2
Average steps: 9750.00 | Total calories: 4000 | Best day: Day 1 (12000 steps) | Goal days: 1/2

Menu option: 3
Weight (kg): 70
Height (m): 1.75
BMI: 22.86 | Category: Normal
```

## BMI Categories

| BMI | Category |
|-----|----------|
| Below 18.5 | Underweight |
| 18.5 to 24.9 | Normal |
| 25 to 29.9 | Overweight |
| 30 and above | Obese |

## Input Validation

- Steps and calories must be non-negative whole numbers (negatives, decimals, and letters are rejected).
- Weight and height must be positive numbers.
- Invalid entries show a clear message, and nothing is saved.
- Summary and chart options warn you if no records exist yet.

## Code Structure

- **Helper functions:** `read_whole_number`, `read_positive_float`, `average_steps`, `total_calories`, `best_day`, `goal_days`, `calculate_bmi`
- **Menu actions:** `add_record`, `show_summary`, `show_bmi`, `show_chart`
- **Main loop:** `main()` displays the menu and dispatches the chosen option

## Notes

- Data is stored in memory only and is cleared when the program exits.
- The daily step goal is set by the `GOAL` constant (default 10,000).

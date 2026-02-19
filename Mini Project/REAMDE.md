# 🧮 Python Calculator

A terminal-based calculator built in Python that supports basic arithmetic operations along with statistical functions — all driven by user input with robust type casting and error handling.

---

## 📋 Features

| Option | Operation | Description |
|--------|-----------|-------------|
| `1` | Addition (`+`) | Sum of two numbers |
| `2` | Subtraction (`-`) | Difference of two numbers |
| `3` | Multiplication (`*`) | Product of two numbers |
| `4` | Division (`/`) | Quotient of two numbers (division-by-zero protected) |
| `5` | Percentage (`%`) | Calculate X% of a value |
| `6` | Mean | Average of a list of numbers |
| `7` | Median | Middle value of a list of numbers |
| `8` | Mode | Most frequently occurring value |
| `9` | Average | Alias for Mean |
| `0` | Exit | Quit the calculator |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.x (no external libraries required — uses the built-in `statistics` module)

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/python-calculator.git

# Navigate into the project directory
cd python-calculator
```

### Run the Calculator

```bash
python calculator.py
```

---

## 🖥️ Usage

After launching, you'll see a menu. Enter the number corresponding to your desired operation and follow the prompts.

```
=============================================
        PYTHON CALCULATOR
=============================================
Operations:
  1. Addition          (+)
  2. Subtraction       (-)
  3. Multiplication    (*)
  4. Division          (/)
  5. Percentage        (%)
  6. Mean
  7. Median
  8. Mode
  9. Average (same as Mean)
  0. Exit
=============================================

Choose an operation (0-9): 6
Enter numbers separated by spaces: 10 20 30 40
Mean/Average of [10.0, 20.0, 30.0, 40.0] = 25.0
```

### Input Types

- **Arithmetic operations** — prompts for two individual numbers
- **Statistical operations** — prompts for a space-separated list of numbers (e.g., `10 20 30 40`)
- **Percentage** — prompts for a base value and a percentage

---

## 🛡️ Error Handling

- **Invalid input** — catches `ValueError` and re-prompts the user instead of crashing
- **Division by zero** — displays a clear error message and returns to the menu
- **No unique mode** — gracefully handles `statistics.StatisticsError` when multiple values tie for mode
- **Empty input** — prompts again if no numbers are provided for statistical operations

---

## 📁 Project Structure

```
python-calculator/
│
├── calculator.py   # Main calculator script
└── README.md       # Project documentation
```

---

## 🧠 Concepts Demonstrated

- User input handling with `input()`
- Type casting using `float()` and `map()`
- Control flow with `while` loops and `if/elif/else`
- Exception handling with `try/except`
- Python's built-in `statistics` module (`mean`, `median`, `mode`)
- Modular code design with reusable functions

---

## 🙋 Author

**Your Name**  
[GitHub](https://github.com/your-username) • [LinkedIn](https://linkedin.com/in/your-profile)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

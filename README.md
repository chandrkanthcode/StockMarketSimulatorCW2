# StockMarketSimulatorCW2
Stock Market Order Matching Simulator

Overview

This project implements a **stock market order matching simulator** in C++. The program simulates how trade orders in a stock market are processed, handling both **buy** and **sell** orders with market and limit prices.

The program reads input from a file, processes the orders according to priority rules, and writes the results to an output file.

Features

1. Handles **buy** and **sell** orders.
2. Supports **limit orders** and **market orders**.
3. Prioritizes orders based on:
   - Order type (market orders > limit orders).
   - Price (higher for buy, lower for sell).
   - Arrival time (earlier orders have higher priority).
     4

. Processes partial matches and residual orders. 5. Outputs executed transactions and unexecuted orders.

File Structure

.
├── main.cpp # Main program source code
├── makefile # Build automation file
├── inputX.txt # Sample input files (e.g., input4.txt)
├── output.txt # Corresponding output files
└── README.md # Project documentation

---

How to Compile and Run

Compilation

To compile the program, use the provided `makefile`. Run the following command in the terminal:

TERMINAL
make

This will generate an executable named `main`.

Execution\*\*
Run the program by specifying the input file:

TERMINAL
./main inputX.txt

The program processes the orders in `inputX.txt` and writes the results to `output.txt`.

Input Format

- The first line contains the **last traded price** (a floating-point number).
- Each subsequent line represents an order:

  <OrderID> <Type> <Quantity> [<Price>]

  Where:

  - `<OrderID>`: Unique alphanumeric string.
  - `<Type>`: `B` (Buy) or `S` (Sell).
  - `<Quantity>`: Number of shares (integer).
  - `<Price>`: Limit price (optional; market orders omit this).

Example Input

1100.00
bob1 S 1 1200.00
cathie1 B 1000
elon S 1000 1100.00

Output Format

- Executed orders are listed with details of the buyer, seller, quantity, and price.
- Unexecuted orders are listed at the end.

Example Output

order cathie1 1 shares purchased at price 1200.00
order bob1 1 shares sold at price 1200.00
order cathie1 999 shares purchased at price 1100.00
order elon 999 shares sold at price 1100.00
order elon 1 shares unexecuted

Dependencies

- **Compiler**: Requires `g++` supporting C++11 or later.
- **make**: To build the project using the makefile.

---

Cleaning Up

To remove the compiled files, run:

TERMINAL
make clean

Testing

Sample input files (`inputX.txt`) and expected outputs (`output.txt`) are included to verify the program's correctness. Run the program with different inputs to test various cases.

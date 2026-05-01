# Bank Demonetization Tracker — Max Heap | Python 🏦💰

A Python-based DSA solution to track Rs. 2000 note deposits across banks during 
India's 2023 demonetization. Implements a custom Max Heap from scratch to manage, 
query, and remove bank denomination records efficiently with file-based I/O and 
robust error handling.

---

## 🧩 Problem Statement

RBI announced the withdrawal of Rs. 2000 notes starting May 23, 2023. Banks needed 
a system to track deposited and exchanged notes. This solution:

1. Lists bank name & Rs. 2000 note count for **May** and **June**
2. Calculates **total notes** deposited across all banks per month
3. Adds new bank records and finds the **bank with maximum deposits** per month
4. Calculates the **total amount collected** across both months
5. **Removes top 2 banks** with highest May deposits from the heap
6. Prints the **Max Heap tree** for both months

---

## 🧠 Data Structure — Max Heap

A **Max Heap** is implemented from scratch (no `heapq` library) with the following 
operations:

| Operation | Method | Time Complexity |
|-----------|--------|----------------|
| Build Max Heap | `max_heap_build()` | O(n log n) |
| Heapify | `max_heapify()` | O(log n) |
| Get Maximum | `heap[0]` | O(1) |
| Remove Maximum | `max_heap_pop()` | O(log n) |
| Display | `write_bank_details()` | O(n) |
| Read Input | `read_bank_details()` | O(n) |
| Total Count | Sum loop | O(n) |

### Why Max Heap?
- Finding the bank with maximum denomination count is **O(1)** — always at root
- Removing the maximum and restructuring costs only **O(log n)**
- Alternative (sorted stack) would cost **O(n²)** to build

---

## 📂 File Format

### Input — `input.txt`
```
Bank name, note count, month
Bank1, 16578, may
Bank2, 48927, may
...
Bank1, 83763, June
...
New Bank details:
Bank11, 671862, May
Bank11, 3893, June
```

### Output — `output.txt`
```
May month details:
Bank1, 16578
...

June month details:
Bank1, 83763
...

Total Rs 2000 note count for May & June month: '453818' & '450017'

Added new bank details:
Bank11, 671862, May
...
Maximum notes deposited in Bank11: 671862 for May month...
Maximum notes deposited in Bank10: 101010 for June month...

Total amount that collected so far in all the banks: 'Rs 3241602000'

May month details: (after removing top 2)
Bank6, 89027
...

June month details:
Bank10, 101010
...
```

---

## ⚠️ Error Handling

Invalid records are skipped with a console warning:
```
Record - 'Bank12,,' was skipped as denomination count is expected to be positive integer.
Record - 'Bank14, -12, may' was skipped as denomination count is expected to be positive integer.
```

Handled cases:
- Missing denomination count
- Negative denomination count
- Non-integer denomination count
- Empty heap underflow on pop
- File not found

---

## 🛠️ Setup & Usage

### Prerequisites
- Python 3.7+

### Run

```bash
git clone https://github.com/PriyankaMenghare/Bank-Demonetization-Tracker-MaxHeap-Python.git
cd Bank-Demonetization-Tracker-MaxHeap-Python

# Place input.txt in the same directory
python demonetization.py

# Output will be written to output.txt
```

---

## 📁 File Structure

```
Bank-Demonetization-Tracker-MaxHeap-Python/
├── demonetization.py   # Main solution
├── input.txt           # Sample input file
├── output.txt          # Sample output file
└── README.md
```

---

## 📝 License

MIT License — for academic use.

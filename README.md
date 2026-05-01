#  Algorithm Visualizer — Greedy & Dynamic Programming

> A project demonstrating classic algorithm techniques through interactive visualizations.
> Subject: Coding Skills (206) — CCC Submission
> Srm University,ap

---

## 👥 Team Members

* Abiramasree K- AP24110011197
* M. Sri Soumitha — AP24110011395
* S. Keerthi — AP24110011365
* K. Nandini — AP24110011363
* Om Keerthana Bhavani — AP24110011229

---

##  Project Overview

This project implements and visualizes two fundamental algorithm paradigms:

| Algorithm      | Type                | Problem                       |
| -------------- | ------------------- | ----------------------------- |
| Task Scheduler | Greedy              | Job Sequencing with Deadlines |
| 0/1 Knapsack   | Dynamic Programming | Max value within capacity     |

### Interfaces:

*  Web Interface (`index.html`)
*  Python CLI (`src/main.py`)

---

## 📁 Folder Structure

```
algorithm-project/
├── src/
│   ├── scheduler.py
│   ├── knapsack.py
│   ├── visualizer.py
│   └── main.py
├── tests/
├── index.html
├── sample_input.json
├── requirements.txt
└── README.md
```

---

##  Web Interface

* Open `index.html` in browser
* Add jobs/items manually
* Click buttons to run algorithms
* View:

  * Greedy schedule + profit
  * Knapsack selected items
  * DP table visualization

---

##  CLI Usage

### Install dependencies

```bash
pip install -r requirements.txt
```

### Run project

```bash
python src/main.py --input sample_input.json --chart
```

### Run specific algorithm

```bash
python src/main.py --mode greedy --input sample_input.json
python src/main.py --mode knapsack --input sample_input.json
```

### Run tests

```bash
python tests/test_scheduler.py
python tests/test_knapsack.py
```

---

## Greedy Algorithm — Task Scheduler

### Idea

Select jobs with **maximum profit first** and assign them to the **latest available slot**.

### Steps

1. Sort jobs by profit (descending)
2. Create slots up to max deadline
3. Assign each job to latest free slot
4. Skip if no slot available

### Example

| Job | Deadline | Profit |
| --- | -------- | ------ |
| J1  | 2        | 100    |
| J2  | 1        | 19     |
| J3  | 2        | 27     |

**Output:**

* Slot1 → J3
* Slot2 → J1
* Profit = 127

### Complexity

* Time: `O(n log n)`
* Space: `O(d)`

---

##  Dynamic Programming — 0/1 Knapsack

### Idea

Build a DP table to store maximum value for each capacity.

### Recurrence

```
dp[i][w] = max(
    dp[i-1][w],
    dp[i-1][w-weight[i]] + value[i]
)
```

### Example

Items:

* Phone (1, 60)
* Book (2, 40)
* Watch (1, 50)

Capacity = 3

**Result:**

* Selected → Phone + Watch
* Value = 110

### Complexity

* Time: `O(n × W)`
* Space: `O(n × W)`

---

##  Greedy vs DP

| Feature  | Greedy       | DP                  |
| -------- | ------------ | ------------------- |
| Approach | Local choice | Global optimization |
| Speed    | Fast         | Slower              |
| Optimal  | Not always   | Always              |
| Use case | Scheduling   | Knapsack            |

---

##  Test Cases

### Greedy

* Basic scheduling → Profit = 127
* Single slot → max profit job selected
* Empty input → handled

### Knapsack

* Basic → Value = 22
* Zero capacity → Value = 0
* All items fit → all selected

---

##  Output

* Gantt Chart (Greedy)
* DP Table (Knapsack)
* Comparison charts

---

##  Technologies

* Python
* matplotlib
* HTML, CSS
* JavaScript

---

##  References

* CLRS — Greedy & DP
* GeeksforGeeks

---

##  Conclusion

This project demonstrates how different algorithm paradigms solve optimization problems and highlights when to use Greedy vs Dynamic Programming.

---

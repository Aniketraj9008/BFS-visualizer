# 🧠 Missionaries and Cannibals Problem

A classic **Artificial Intelligence state-space search problem** that demonstrates how search algorithms can be used to find a valid sequence of actions from an initial state to a goal state while satisfying a set of constraints.

---

## 📌 Problem Statement

The **Missionaries and Cannibals Problem** consists of:

* 3 Missionaries
* 3 Cannibals
* 1 Boat
* 2 Banks of a river

The objective is to safely transport everyone from the **starting bank** to the **destination bank**.

### 🚤 Boat Constraints

* The boat can carry a maximum of **2 people** at a time.
* The boat must carry at least **1 person**.
* The boat can only move when there are people on it.
* The boat must be operated from the bank where it is currently located.

### ⚠️ Safety Constraint

On either bank:

> If missionaries are present, the number of missionaries must never be less than the number of cannibals.

In other words:

```text
Missionaries = 0
OR
Missionaries >= Cannibals
```

This rule must be satisfied on **both sides of the river** after every move.

---

## 🎯 Objective

Find a sequence of valid boat movements that transfers all:

```text
3 Missionaries
3 Cannibals
```

from the initial bank to the destination bank without violating any of the constraints.

The goal state is:

```text
Left Bank:   0 Missionaries, 0 Cannibals
Right Bank:  3 Missionaries, 3 Cannibals
```

---

## 🧩 State Representation

A state can be represented using:

```text
(M, C, B)
```

Where:

* `M` → Number of missionaries on the starting/left bank
* `C` → Number of cannibals on the starting/left bank
* `B` → Position of the boat

For example:

```text
(3, 3, L)
```

represents the initial state:

```text
Left Bank:   3 Missionaries, 3 Cannibals
Right Bank:  0 Missionaries, 0 Cannibals
Boat:        Left
```

The goal state is:

```text
(0, 0, R)
```

---

## 🔍 State-Space Search

The problem can be modeled as a **state-space search problem**.

Each valid configuration of missionaries, cannibals, and the boat represents a **state**.

A movement of the boat creates a transition from one state to another.

### Initial State

```text
(3, 3, L)
```

### Goal State

```text
(0, 0, R)
```

### Possible Boat Movements

The boat can transport:

```text
1 Missionary
1 Cannibal
2 Missionaries
2 Cannibals
1 Missionary + 1 Cannibal
```

Each movement is checked to ensure that the resulting state is valid.

---

## 🧠 Algorithm

The solution uses **search techniques from Artificial Intelligence** to explore possible states and find a valid path from the initial state to the goal state.

The general process is:

```text
Initial State
      ↓
Generate Possible Moves
      ↓
Check State Validity
      ↓
Remove Invalid / Visited States
      ↓
Generate Next States
      ↓
Repeat
      ↓
Reach Goal State
```

### State Validation

A state is considered valid when:

1. The number of missionaries is between 0 and 3.
2. The number of cannibals is between 0 and 3.
3. The boat is on a valid bank.
4. Cannibals never outnumber missionaries on a bank where missionaries are present.
5. The boat never carries more than two people.
6. The boat always carries at least one person.

---

## 📂 Project Structure

The project structure depends on the implementation. A typical structure is:

```text
Cannibals-and-Missionaries-problem/
│
├── README.md
├── main.py
└── ...
```

If your repository contains multiple source files, they can be organized according to their responsibilities, such as:

```text
Cannibals-and-Missionaries-problem/
│
├── README.md
├── main.py
├── solver.py
└── requirements.txt
```

---

## ▶️ How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/Aniketraj9008/Cannibals-and-Missionaries-problem.git
```

### 2. Navigate to the Project

```bash
cd Cannibals-and-Missionaries-problem
```

### 3. Run the Program

If the project is implemented in Python:

```bash
python main.py
```

> If your main Python file has a different name, replace `main.py` with the appropriate filename.

---

## 💡 Example Solution

One valid solution can be represented as a sequence of states:

```text
Initial
(3M, 3C, L)

        ↓

(3M, 1C, R)

        ↓

(3M, 2C, L)

        ↓

(3M, 0C, R)

        ↓

(3M, 1C, L)

        ↓

(1M, 1C, R)

        ↓

(2M, 2C, L)

        ↓

(0M, 2C, R)

        ↓

(0M, 3C, L)

        ↓

(0M, 1C, R)

        ↓

(0M, 2C, L)

        ↓

(0M, 0C, R)
```

The exact output may vary depending on the search strategy and implementation.

---

## 📊 Complexity

The problem has a relatively small finite state space because there are only three missionaries, three cannibals, and two possible boat positions.

For a general implementation, the computational cost depends on the search algorithm used.

### Breadth-First Search

If BFS is used:

* **Time Complexity:** `O(V + E)`
* **Space Complexity:** `O(V)`

Where:

* `V` = number of valid states
* `E` = number of valid transitions

BFS is particularly useful when we want to find the **shortest sequence of moves**.

---

## ✨ Features

* 🧠 AI-based state-space problem solving
* 🚤 River-crossing simulation
* ✅ Valid-state checking
* 🔄 State transition generation
* 🎯 Goal-state detection
* ♻️ Avoidance of repeated states
* 📈 Demonstrates classical AI search concepts

---

## 🛠️ Technologies Used

Depending on the implementation:

* **Python**
* **Artificial Intelligence**
* **State-Space Search**
* **Graph Traversal**
* **Breadth-First Search / Search Algorithms**

---

## 📚 AI Concepts Demonstrated

This project demonstrates several important Artificial Intelligence concepts:

### 1. State Representation

Representing a real-world problem as a collection of states.

### 2. State Space

All possible configurations of missionaries, cannibals, and the boat form the state space.

### 3. Operators / Actions

Boat movements act as operators that transform one state into another.

### 4. Goal Test

A state is checked to determine whether all missionaries and cannibals have successfully crossed the river.

### 5. Constraint Satisfaction

Invalid states are rejected when the safety constraint is violated.

### 6. Search

A search algorithm explores the state space to find a path from the initial state to the goal.

---

## 🎓 Learning Outcomes

After completing this project, you can understand:

* How real-world problems can be modeled as state-space problems.
* How AI search algorithms explore possible solutions.
* How constraints can be used to eliminate invalid states.
* How graph traversal can be applied to problem solving.
* How to prevent repeated-state exploration.
* How to find a valid path from an initial state to a goal state.

---

## 🚀 Future Improvements

The project can be extended by adding:

* [ ] Graphical User Interface (GUI)
* [ ] Animated river-crossing visualization
* [ ] BFS and DFS comparison
* [ ] A* search implementation
* [ ] Interactive user-controlled mode
* [ ] Number of states explored
* [ ] Execution-time comparison
* [ ] Shortest-path visualization
* [ ] Support for different numbers of missionaries and cannibals
* [ ] Interactive state-space graph

---

## 🤝 Contributing

Contributions are welcome!

To contribute:

```bash
git fork
```

Create a new branch:

```bash
git checkout -b feature/new-feature
```

Make your changes and commit them:

```bash
git add .
git commit -m "Add new feature"
```

Push the branch:

```bash
git push origin feature/new-feature
```

Then create a Pull Request.

---

## 📄 License

This project is created for **educational and academic purposes**.

You are free to modify and improve the project for learning purposes.

---

## 👨‍💻 Author

**Aniket Raj**

B.Tech Student
SRM Institute of Science and Technology, Chennai

### 🔗 GitHub

[Aniket Raj's GitHub Repository](https://github.com/Aniketraj9008/Cannibals-and-Missionaries-problem?utm_source=chatgpt.com)

---

## ⭐ Support

If you found this project useful for learning Artificial Intelligence and search algorithms, consider giving the repository a ⭐.

# Connect 4 AI with Minimax, Alpha-Beta, and Bidirectional Search 🎮🤖

![Connect 4 Demo](demo-gif-url)  
*A strategic AI opponent for Connect 4 using advanced search algorithms, developed for Benha University's AI course.*

---

## 🏫 Project Overview  
**University**: Benha University, Faculty of Engineering (Shoubra)  
**Department**: Communications and Computer Engineering  
**Course**: Artificial Intelligence  

**Objective**:  
Develop an unbeatable Connect 4 AI using:  
- **Minimax** with heuristic evaluation  
- **Alpha-Beta Pruning** for optimization  
- **Iterative Deepening** for real-time decisions  
- **Bidirectional Search** (theoretical exploration in report)  

---

## ⚙️ Features  
### 🎮 **Connect 4 Game**  
- **Interactive GUI**: Play vs AI or watch AI vs AI.  
- **Three AI Modes**:  
  - `Minimax`: Optimal but slower.  
  - `Alpha-Beta`: 2-10x faster than Minimax.  
  - `Iterative Deepening`: Balances speed and depth.  
- **Real-time Stats**: Move count, time elapsed, and algorithm details.  

### 🔍 **Bidirectional Search Report**  
- Theoretical analysis of bidirectional search in pathfinding (e.g., GPS routing).  
- Comparison with unidirectional BFS (time complexity: `O(b^d/2)` vs `O(b^d)`).  

### 🛠️ **Expert System**  
- Separate Prolog-based car diagnosis system (see [related project](#-related-projects)).  

---

## 🧠 Algorithms  
### 1. **Minimax**  
- **Optimal Play**: Evaluates all possible moves up to a depth limit.  
- **Heuristic**: Prioritizes wins/blocks (`±100 pts`), 2-in-a-row (`+10 pts`), and center control (`+3 pts`).  

### 2. **Alpha-Beta Pruning**  
- **Optimization**: Prunes irrelevant branches, preserving Minimax's optimality.  
- **Efficiency**: Reduces search time by 50-90%.  

### 3. **Iterative Deepening Alpha-Beta**  
- **Adaptive**: Progressively increases depth within time limits.  
- **Best for Real-Time**: Guarantees a move even if interrupted.  

```python
def alphabeta(node, depth, alpha, beta, maximizing_player):
    if depth == 0 or node.is_terminal():
        return heuristic(node)
    for move in node.valid_moves():
        new_node = node.apply(move)
        score = alphabeta(new_node, depth-1, alpha, beta, False)
        alpha = max(alpha, score) if maximizing_player else min(beta, score)
        if alpha >= beta: break  # Prune!
    return alpha
```

---

## 💻 Installation  
### Requirements  
- Python 3.8+  
- Pygame: `pip install pygame`  

### Steps  
1. Clone the repository:  
   ```bash
   git clone https://github.com/your-repo/connect4-ai.git
   cd connect4-ai
   ```
2. Run the game:  
   ```bash
   python Gui.py
   ```

---

## 🕹️ Usage  
1. **Main Menu**:  
   - `Human vs AI`: Play against the AI.  
   - `AI vs AI`: Watch two algorithms compete.  
2. **Algorithm Selection**:  
   - Choose between Minimax, Alpha-Beta, or Iterative Deepening.  
3. **Gameplay**:  
   - Click a column to drop your disc (Red).  
   - AI (Yellow) responds automatically.  

![Game Screenshot](screenshot-url)  

---

## 👩‍💻 Team  

 - Malak Mounir Abdellatif
 - Razan Ahmed Fawzy
 - Nourhan Farag Mohamed
 - Farida Waheed Abdelbary     
 - Nour Hesham Elsayed      

---

## 🔗 Related Projects  
1. [Car Diagnosis Expert System](https://github.com/your-repo/car-diagnosis-expert-system)  
   - Prolog-based rule engine for car troubleshooting.  
2. [Bidirectional Search Report](Bidirectional_search_algorithm_report.pdf)  
   - Theoretical analysis of bidirectional pathfinding.  

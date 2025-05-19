# astar_example
✅ Initialization
Start at A
g = 0, h = 6 → f = 6
Open = [(A, f=6)]
Closed = []

🔹 Step 1: Expand A
Neighbors:

B: g = 2, h = 5 → f = 7

C: g = 1, h = 5 → f = 6

✅ Open = [(C, f=6), (B, f=7)]
✅ Closed = [A]

🔹 Step 2: Expand C
Neighbors: D, E

D: g = 1 + 5 = 6, h = 4 → f = 10

E: g = 1 + 5 = 6, h = 2 → f = 8

✅ Open = [(B, f=7), (E, f=8), (D, f=10)]
✅ Closed = [A, C]

🔹 Step 3: Expand B
Neighbors: D, H

D: g = 2 + 2 = 4 (better than 6) → f = 4 + 4 = 8 ✅ UPDATE

H: g = 2 + 2 = 4, h = 6 → f = 10 ✅ VALID OPTION

✅ Open = [(D, f=8), (E, f=8), (H, f=10)]
✅ Closed = [A, C, B]

🔹 Step 4: Expand D
Neighbors: E, G

E: g = 4 + 3 = 7 < current g(E)=6? ❌ skip

G: g = 4 + 1 = 5, h = 3 → f = 8 ✅

✅ Open = [(E, f=8), (G, f=8), (H, f=10)]
✅ Closed = [A, C, B, D]

🔹 Step 5: Expand E
Neighbors: F, G

F: g = 6 + 2 = 8, h = 0 → f = 8 ✅ GOAL

G: g = 6 + 1 = 7, h = 3 → f = 10 (worse than current G=5) ❌ skip

✅ Open = [(G, f=8), (H, f=10), (F, f=8)]
✅ Closed = [A, C, B, D, E]

🔹 Step 6: Expand G
Neighbors: H

H: g = 5 + 2 = 7, h = 6 → f = 13 (worse than existing f=10) ❌ skip

✅ Open = [(F, f=8), (H, f=10)]
✅ Closed = [A, C, B, D, E, G]

🔹 Step 7: Expand F — GOAL REACHED 🎉
Total cost g = 8
Trace back: F ← E ← C ← A

✅ Final Path: A → C → E → F

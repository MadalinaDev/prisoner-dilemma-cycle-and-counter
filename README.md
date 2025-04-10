# Cycle and Counter

## How "Cycle and Counter" Works

### Part 1 – Single Match Function

#### Cycle Structure
- The algorithm uses a fixed cycle of **6 rounds**.
- In every cycle:
  - **Round 6:** Plans a defection.
  - **Rounds 1–5:** Normally cooperates.

#### Punishment Mechanism
- After completing at least one full cycle (6 rounds), the algorithm reviews the opponent’s moves in the previous cycle.
- **If the opponent’s cooperation rate is low** (fewer than 3 cooperative moves out of 6), it punishes by defecting in the current cycle even during rounds that normally would be cooperative.

#### Endgame Tactic
- When the total number of rounds is known, the algorithm **defects in the final round** to maximize points.

---

### Part 2 – Tournament Function with Opponent Selection

#### Current Match Decision
- Applies the same cycle logic for the current opponent:
  - Uses the cycle phase (every 6th move is a planned defection).
  - Checks the previous 6 moves (if available) to decide whether to punish.

#### Choosing the Next Opponent
- Scans through match histories (from the dictionary of opponents).
- **Selects the opponent with the highest cooperation ratio** (provided they haven’t reached the 200‑round limit).
- If there is an opponent with an empty history (i.e., not yet played), it selects that opponent to build a cooperative relationship.

# Collusion-Theory-Auction


## 🎯 Overview

This project simulates **cartel behavior in second-price sealed-bid auctions**, a real-world application of auction theory in game theory. We study how a cartel, led by a central figure (cartel leader), can manipulate auction outcomes by incentivizing other bidders to join a collusive group.

The goal is to:
- Analyze whether forming a cartel is beneficial to the members and the leader.
- Determine the optimal payment (`k`) the leader should offer to avoid losses.
- Compare cartel vs non-cartel strategies through simulation.

---

## 📦 Features

- 🎲 Simulates second-price sealed-bid auctions with up to 500 rounds.
- 👥 Models cartel behavior and leader/member dynamics.
- 📉 Evaluates profit/loss outcomes for cartel members vs non-members.
- 🔄 Includes alternate **rotating cartel leader** strategy.
- 📊 Outputs key insights like optimal `k`, average utility, and more.

---

## 🧪 Simulation Parameters

- **Auction type:** Second-price sealed-bid
- **Bidders:** `t` total (mix of cartel and independent)
- **Cartel Members (`m`)**: Paid `k` units by cartel leader to collude
- **Valuation distribution:** Normal (`μ = 62.5`, `σ = 2.5`), bounded [50, 75]
- **Budget distribution:** Uniform between [200, 300]

---

## 🧠 Strategies Implemented

### ✅ Fixed Leader Cartel Strategy

1. Cartel leader offers `k` units to members.
2. Cartel members bid internally to pick a winner.
3. Winner’s bid is submitted to the main auction.
4. If cartel wins:
   - Leader pays second-highest bid (`Pa`) and gives the item to internal winner.
   - Winner pays leader `max(Pa, Pc)` where `Pc` is the second-highest cartel bid.
   - **Leader’s profit** = `Pc - Pa - mk` (if positive)

### 🔁 Rotating Leader Strategy

- The **lowest bidder** becomes cartel leader in each round.
- Reduces risk on a single player.
- Simulation shows higher average utility for members.

---

## 📊 Key Results

| Metric | Value |
|--------|-------|
| Avg Utility (Cartel Member) | 3.053 |
| Avg Utility (Non-Cartel) | 2.344 |
| Avg Utility (Independent, No Cartel) | 2.112 |
| Cutoff value of `k` | 0.074 units |

- 📈 **Larger cartels** (more members) → higher utility for the leader.
- 📉 **More total bidders** (with same cartel ratio) → lower leader utility.

---



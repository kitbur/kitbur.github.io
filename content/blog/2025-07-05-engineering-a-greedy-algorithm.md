---
title: "Engineering a Greedy Algorithm"
date: 2025-07-05
description: "How I built a custom algorithm to solve an optimization problem with tight restrictions."
tags: ["JavaScript", "Algorithms"]
draft: false
---

While building a [budgeting calculator](/projects/aideen-audit) for a video game, I encountered a classic optimization challenge: given a target value and multiple dynamic purchase options with different regional costs and one-time bonuses, find the most efficient combination.

## The Algorithm: Multi-Pass Greedy Strategy

So many factors at play led me to a solution with three distinct passes.

### Pass 1: Claim High-Value Bonuses

First, sort available items by size and prioritize any bonuses, which double the amount of currency gained once only for each purchase option.

```javascript
const sortedPacks = [...basePacks].sort((a, b) => b.baseJades - a.baseJades);
```

And then ensure that highest-value opportunities are utilized first.

```javascript
if (bonusesAvailable[bonusKey] && remainingJades >= bonusValue) {
    totalCost += pack.cost;
    remainingJades -= bonusValue;
    purchaseList[`${pack.name}_bonus`] = 1;
    bonusesAvailable[bonusKey] = false;
}
```

By checking if there is enough of the remaining target to justify the doubled bonus, we avoid wasteful purchases while securing the best deals.

### Pass 2: Standard Greedy Selection

With bonuses claimed, the rest of the calculation uses standard, greedy logic:

```javascript
if (remainingJades >= pack.baseJades) {
    const numPacks = Math.floor(remainingJades / pack.baseJades);
    totalCost += numPacks * pack.cost;
    remainingJades -= numPacks * pack.baseJades;
    purchaseList[pack.name] = (purchaseList[pack.name] || 0) + numPacks;
}
```

Take as many of the largest denomination as possible, then move to the next size down. The `Math.floor` calculation ensures that we do not overshoot our target.

### Pass 3: Handle Remainder Efficiently

Then comes the remainder. It is important for the calculator to not be wasteful, so the final pass eliminates excess purchases by finding the smallest item that covers any remaining amount:

```javascript
if (remainingJades > 0) {
    const coveringPack = [...sortedPacks].reverse()
        .find(pack => pack.baseJades >= remainingJades);
    
    if (coveringPack) {
        totalCost += coveringPack.cost;
        purchaseList[coveringPack.name] = (purchaseList[coveringPack.name] || 0) + 1;
    }
}
```

## Why This Approach Works

This algorithm succeeds because it separates concerns: handle the special cases first, then fall back to standard optimization. The three-pass structure makes the logic explicit and debuggable, while the sorted iteration ensures predictable behavior with minimal waste.
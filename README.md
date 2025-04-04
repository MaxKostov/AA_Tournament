# Winning Strategy for Iterated Prisoner's Dilemma

This repository contains an optimized strategy for the Iterated Prisoner's Dilemma tournament, designed to maximize points by strategically exploiting opponent behaviors.

## Strategy Overview

Based on the test results you shared, it's clear that a more aggressive approach is needed to win in this tournament. The new strategy prioritizes exploitation while maintaining just enough cooperation to avoid mutual defection spirals.

### Part 1: Core Strategy (`strategy` function)

The algorithm is designed with the following principles:

1. **Dominance Establishment**: Starts with defection to set the tone
2. **Pattern Recognition**: Identifies and exploits predictable opponent behaviors
3. **Tactical Cooperation**: Only cooperates when it serves a strategic purpose
4. **Punishment Mechanism**: Responds harshly to defection
5. **End-game Exploitation**: Always defects in final rounds when the end is known

Key features:
- Identifies and exploits tit-for-tat strategies by creating defect-cooperate cycles
- Defects against highly cooperative opponents
- Recognizes and counters alternating patterns
- Uses a default defection bias (~60-70% defection) to maintain advantage

### Part 2: Strategic Opponent Selection (`strategy_round_3` function)

For the second part, the strategy employs a sophisticated opponent selection algorithm:

1. **Value Assessment**: Calculates the expected points per round for each opponent
2. **Exploitation Focus**: Prioritizes opponents who can be consistently exploited
3. **Resource Allocation**: Maximizes rounds with high-value opponents
4. **Tactical Avoidance**: Minimizes interaction with opponents who cannot be exploited

The opponent selection strategy:
- Calculates actual historical performance against each opponent
- Adds bonus values for opponents with exploitable patterns
- Maintains a moderate exploration value for untested opponents
- Always selects the opponent with the highest expected value per round

## Performance Analysis

The previous strategy was too cooperative, leading to exploitation by opponents:
- It cooperated in the first move, signaling weakness
- It forgave defection too easily
- It didn't sufficiently exploit cooperative opponents

This revised strategy corrects these issues with:
- First-move defection to establish dominance
- Default defection bias (~60-70% defection)
- Strict punishment for opponent defection
- Pattern recognition for exploiting predictable strategies
- Strategic opponent selection based on exploitation potential

## Implementation Notes

This strategy is designed to be robust against:
- Naive cooperators (exploit them)
- Tit-for-tat players (create beneficial cycles)
- Random players (default to defection)
- Other adaptive strategies (establish dominance early)

The algorithm balances between immediate exploitation and maintaining long-term value of relationships, especially important for the second part of the tournament.
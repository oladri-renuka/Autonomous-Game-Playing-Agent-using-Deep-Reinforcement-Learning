# Autonomous Game Playing Agent using Deep Reinforcement Learning

A reinforcement learning implementation that creates an intelligent game-playing agent using Proximal Policy Optimization (PPO) and innovative self-play techniques. The agent learns complex strategic gameplay patterns through neural network-based policy learning, achieving competitive performance without any pre-programmed game knowledge.

## Unique Solution Approach

**The breakthrough in this project lies in the pure self-play learning paradigm combined with dynamic opponent selection.** Unlike traditional game AI that relies on minimax algorithms, opening books, or hand-crafted evaluation functions, this agent discovers winning strategies entirely through reinforcement learning. The key innovation is training against a diverse pool of its own previous versions, creating a curriculum that naturally progresses from basic rule-following to advanced strategic thinking. This approach enables the agent to develop sophisticated tactical patterns—such as creating multiple threats simultaneously and recognizing defensive priorities—without any human-designed game knowledge.

## Project Overview

This project implements a board game playing agent that learns through reinforcement learning rather than traditional game tree search methods. The agent uses self-play training to discover winning strategies and defensive patterns, progressing from random play to strategic mastery over 5000 training episodes.

### Key Features

- **Deep Reinforcement Learning**: PPO algorithm with neural network policy
- **Self-Play Training**: Agent improves by playing against previous versions of itself
- **Action Masking**: Ensures only valid moves are considered during training
- **Comprehensive Evaluation**: Testing against random, rule-based, and MCTS opponents
- **Training Analytics**: Detailed logging of performance metrics and learning progress

## Technical Implementation

### Architecture
- **Neural Network**: 3-layer fully connected network (256→128→64 hidden units)
- **Policy Network**: Outputs action probabilities with masked invalid moves
- **Value Network**: Shared architecture with separate value head for state evaluation

### Training Methodology
- **Algorithm**: Proximal Policy Optimization (PPO)
- **Self-Play**: Agent trains against copies of itself from different training stages
- **Reward Structure**: Win (+20), Loss (-20), Draw (0), Invalid move (-20), plus time-based rewards
- **Episodes**: 5000 training episodes with performance tracking every 100 episodes

## Performance Results

### Final Evaluation (200 games each):
- **vs Random Opponent**: 78% win rate
- **vs Rule-based AI**: Variable performance based on opponent difficulty
- **Training Stability**: 100% valid move rate maintained throughout training
- **Learning Curve**: Consistent improvement from ~56% to 78% win rate

### Training Metrics
- Average reward progression from 21.7 to 28.0 over 5000 episodes
- Win rate stabilized around 60-70% during self-play training
- Zero invalid moves in final 3000+ episodes

## Key Technical Decisions

### Why PPO?
- Stable policy updates compared to other policy gradient methods
- Good sample efficiency for this type of discrete action space
- Proven effectiveness in game-playing domains

### Self-Play Strategy
- Maintains pool of opponent agents from different training checkpoints
- Prevents overfitting to specific opponent strategies
- Enables discovery of complex strategic patterns

### Reward Design
- Sparse rewards (win/loss) supplemented with time-based incentives
- Penalty for invalid moves to ensure rule compliance
- Balanced to encourage both offensive and defensive play

## Alternative Approaches Tested

### What Worked Well
- Self-play training proved highly effective for strategic learning
- Action masking eliminated invalid move exploration
- PPO provided stable and consistent learning

### Challenges Encountered
- Initial reward tuning required several iterations
- Balancing exploration vs exploitation in self-play opponents

### Comparative Analysis
- Attempted phased training with specialized opponents (less effective)
- Experimented with MCTS-PPO hybrid (added complexity without benefit)
- Simple self-play approach ultimately proved most reliable

## Competition Context

This project was developed for a Kaggle simulation competition, demonstrating practical application of reinforcement learning to competitive game-playing scenarios. The focus was on creating an agent capable of strategic thinking and adaptation without domain-specific knowledge.

## License

MIT License - Feel free to use and modify for educational and research purposes.


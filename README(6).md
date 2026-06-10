# Neuroevolution Research Lab

A browser-based neural network bot simulation where autonomous agents evolve over time using neuroevolution, novelty search, and MAP-Elites-inspired behavioural diversity.

The project turns a simple neural bot canvas demo into a research-oriented experiment platform. Bots are treated as experiments: each one has a neural controller, receives a fitness score, and contributes behavioural data. The best and most interesting bots are selected, crossed over, mutated, archived, and refined across generations.

## Demo Concept

Bots spawn in a 2D world and attempt to reach target goals while avoiding obstacles. Each bot is controlled by a small neural network. Over many generations, the population improves through evolutionary selection.

The simulation does not only reward the highest-scoring bot. It can also preserve unusual or diverse behaviours, making it useful for experimenting with evolutionary AI ideas.

## Features

- Neural network controlled bots
- Population-based evolution
- Mutation and crossover
- Elitism to preserve top performers
- Objective fitness scoring
- Novelty search mode
- Hybrid objective + novelty search
- MAP-Elites-style behaviour archive
- Curriculum learning with harder stages
- Obstacles and target sequences
- Champion replay mode
- Fitness history graph
- Behaviour archive heatmap
- Exportable JSON research logs
- Fully browser-based
- No build tools required

## Search Modes

### Objective Search

Bots are selected mainly by task performance. This rewards agents that reach targets, avoid penalties, and move efficiently.

### Novelty Search

Bots are rewarded for behaving differently from previous bots. This can help prevent the population from getting stuck in one early strategy.

### Hybrid Search

Combines objective performance with novelty. This is the default mode and is useful because it balances progress with exploration.

## How It Works

Each bot receives inputs such as:

- Current position
- Current velocity
- Direction to target
- Distance to target
- Nearest obstacle direction
- Nearest obstacle distance
- Current trial progress

The neural network outputs movement controls for the bot.

At the end of each trial, the system calculates:

- Fitness score
- Target score
- Coverage of the world
- Efficiency
- Smoothness
- Wall collisions
- Obstacle collisions
- Novelty score
- Behaviour descriptor

The next generation is created using:

- Elite preservation
- Parent selection
- Neural network crossover
- Random mutation
- MAP-Elites archive sampling

## Controls

| Control | Description |
|---|---|
| Search Mode | Switch between objective, novelty, and hybrid evolution |
| Novelty Weight | Adjust how much behavioural novelty affects selection |
| Mutation Rate | Control how often neural weights mutate |
| Simulation Speed | Run the experiment faster or slower |
| Pause / Resume | Stop or continue the simulation |
| Replay Champion | Replay the best evolved bot so far |
| Export Research Log | Download experiment data as a JSON file |
| Reset Experiment | Restart the full simulation |

## Visual Guide

- Blue bots: current population
- Yellow bot: current best or champion bot
- Green circles: target goals
- Red circles: obstacles
- Right heatmap: MAP-Elites behaviour archive
- Fitness graph: best fitness over generations

## Research Ideas Included

This project is inspired by several evolutionary computation concepts.

### Neuroevolution

Instead of training a neural network with backpropagation, the network weights are evolved across generations.

### Novelty Search

Some agents are rewarded for being behaviourally different rather than only directly successful. This can help discover strategies that normal optimisation may ignore.

### MAP-Elites

The system keeps a grid of high-performing bots across different behaviour types. This means the project does not only remember one best solution; it stores a collection of different useful strategies.

### Curriculum Learning

As bots improve, the world becomes harder by adding more targets and obstacles.

## Exported Research Logs

The `Export Research Log` button downloads a JSON file containing:

- Current configuration
- Generation number
- Curriculum stage
- Best fitness
- Best score
- Best genome
- Behaviour archive data
- MAP-Elites cells
- Fitness history

This makes it easier to compare different experiment settings.

## Running Locally

Open the HTML file directly in a browser:

```bash
open neuroevolution_research_lab_fixed.html
```

Or just double-click the file.

Because the project uses p5.js from a CDN, an internet connection is recommended unless you download p5.js locally.

## File Structure

```text
neuroevolution-research-lab/
├── index.html
└── README.md
```

Recommended setup:

1. Rename the HTML file to `index.html`
2. Add this README as `README.md`
3. Upload both files to GitHub Pages or any static web host

## Possible Future Improvements

- Add save/load champion genome
- Add multiple environment presets
- Add comparison mode for different search algorithms
- Add graph export as CSV
- Add species tracking
- Add NEAT-style topology evolution
- Add multiple bot body types
- Add sensor visualisation rays
- Add multi-objective Pareto ranking
- Add localStorage experiment saves
- Add replay timeline controls
- Add deterministic seed input for repeatable experiments

## Tech Stack

- HTML
- CSS
- JavaScript
- p5.js

## Why This Project Is Interesting

This project is more than a simple animation. It demonstrates how simple agents can become more capable through evolutionary pressure, mutation, selection, and behavioural diversity.

It is useful for learning about:

- Artificial intelligence
- Evolutionary algorithms
- Neural networks
- Emergent behaviour
- Simulation design
- Research visualisation
- Browser-based experiments

## License

This project can be used, modified, and expanded for learning, experimentation, and creative coding projects.

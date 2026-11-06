# BlocksWorld

Decision support and AI algorithms in Java, applied to the classic *Blocks World* problem: blocks stacked on piles, rearranged to reach a goal configuration.

Built as the capstone project of a university course on decision support and artificial intelligence.

## What's inside

| Package | Topic | Content |
|---|---|---|
| `modelling` | Modelling | Variables, boolean variables, constraints (difference, implication, unary) |
| `planning` | Planning | BFS, DFS, Dijkstra and A* planners, with Blocks World heuristics |
| `cp` | Constraint programming | Backtracking and MAC solvers, arc consistency, variable/value heuristics |
| `datamining` | Knowledge extraction | Apriori and brute-force association rule mining on boolean databases |
| `blocksworld` | Blocks World | Problem instances (regular, increasing, with actions/constraints) and executables |

## Build and run

Requires Java 17+. The libraries in `lib/` (Blocks World model, generator and tests) were provided for the course.

```bash
javac -cp "lib/*" -d bin $(find src -name "*.java")
java -cp "bin:lib/*" blocksworld.Executable
```

The main executable asks what to simulate:

1. **a plan**: find a sequence of moves from an initial state to a goal
2. **a solution**: find a configuration satisfying the constraints
3. **knowledge extraction**: mine association rules from generated states

Each part can also be run on its own: `blocksworld.PlanningExecutable`, `blocksworld.CPExecutable`, `blocksworld.DataminingExecutable`, `blocksworld.ModellingExecutable`.

With [Ant](https://ant.apache.org/): `ant compile`, `ant runMain`.

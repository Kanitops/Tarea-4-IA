# Repository Guidelines

## Project Structure & Module Organization
This repository contains two main notebooks:
- `Tarea 4 - RL - Q-Learning (1).ipynb` — Original template with questions
- `Tarea 4 - RL - Q-Learning - Solucion.ipynb` — **Working notebook with solutions** (use this one)

Supporting materials: `tarea4-IA-2025 (1).pdf` (instructions), `rubrica-tarea-IA-RL (1).xlsx` (rubric), and `requirements.txt` (dependencies). Configuration assets like `.gitignore` belong at the repository root.

## Build, Test, and Development Commands
```bash
# Setup environment (first time only)
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# Interactive development
jupyter lab "Tarea 4 - RL - Q-Learning - Solucion.ipynb"

# Run notebook programmatically (from VS Code or terminal)
# Note: Use Python 3.13+ (current: 3.13.7)
.venv/bin/jupyter nbconvert --to notebook --execute \
    "Tarea 4 - RL - Q-Learning - Solucion.ipynb" \
    --output "Tarea 4 - RL - Ejecutado.ipynb"

# Export to HTML for sharing
.venv/bin/jupyter nbconvert --to html \
    "Tarea 4 - RL - Q-Learning - Solucion.ipynb" \
    --output report.html
```

## Coding Style & Naming Conventions
Follow PEP 8 with four-space indentation, `snake_case` for functions, and `UPPER_SNAKE_CASE` for constants such as `ZOMBIE` or `BLOCK`. Keep emoji tokens that define the grid so renders stay consistent across cells. Prefer pure Python and NumPy utilities already imported; new helpers should accept deterministic seeds and include short docstrings describing state transitions.

## Testing Guidelines
Re-run the “Ambiente” and “Agente” sections top-to-bottom after any edit, making sure cells reset the random seeds (`random.seed(42); np.random.seed(42)`) before evaluations. When adding functions, create validation cells that pit the updated policy against corner maps (blocked doors, missing keys) and log cumulative reward tables for quick diffing. If you introduce standalone modules, add lightweight `pytest` cases under `tests/` mirroring notebook scenarios so automation can reuse them later.

## Commit & Pull Request Guidelines
The repo currently lacks history, so adopt concise Conventional Commit prefixes (`feat:`, `fix:`, `docs:`) and mention the touched notebook cell range when relevant, e.g., `feat: extend door logic (cells 12-18)`. Pull requests should include: purpose, summary of behavioural impact (reward deltas, runtime), screenshots of the rendered grid, and references to rubric items addressed. Always attach the executed notebook (`build/agent-run.ipynb` or HTML export) so reviewers can replicate results without re-running.

# Repository Guidelines

## Project Structure & Module Organization
All runnable code lives in `Tarea 4 - RL - Q-Learning (1).ipynb`, which contains the environment setup, agent logic, and experiment cells. Keep supporting instructions in `tarea4-IA-2025 (1).pdf` and evaluation criteria in `rubrica-tarea-IA-RL (1).xlsx`; never overwrite these source documents—drop new references beside them. Configuration assets such as `.gitignore` and notebook checkpoints belong at the repository root so the notebook can import resources using relative paths without extra sys.path tweaks.

## Build, Test, and Development Commands
Use `jupyter lab "Tarea 4 - RL - Q-Learning (1).ipynb"` for interactive development; keep kernels on Python 3.12 to match the existing metadata. Run the full pipeline headlessly with `jupyter nbconvert --to notebook --execute "Tarea 4 - RL - Q-Learning (1).ipynb" --output build/agent-run.ipynb` to catch regressions before committing. Export polished artefacts for sharing via `jupyter nbconvert --to html "Tarea 4 - RL - Q-Learning (1).ipynb" --output build/report.html`.

## Coding Style & Naming Conventions
Follow PEP 8 with four-space indentation, `snake_case` for functions, and `UPPER_SNAKE_CASE` for constants such as `ZOMBIE` or `BLOCK`. Keep emoji tokens that define the grid so renders stay consistent across cells. Prefer pure Python and NumPy utilities already imported; new helpers should accept deterministic seeds and include short docstrings describing state transitions.

## Testing Guidelines
Re-run the “Ambiente” and “Agente” sections top-to-bottom after any edit, making sure cells reset the random seeds (`random.seed(42); np.random.seed(42)`) before evaluations. When adding functions, create validation cells that pit the updated policy against corner maps (blocked doors, missing keys) and log cumulative reward tables for quick diffing. If you introduce standalone modules, add lightweight `pytest` cases under `tests/` mirroring notebook scenarios so automation can reuse them later.

## Commit & Pull Request Guidelines
The repo currently lacks history, so adopt concise Conventional Commit prefixes (`feat:`, `fix:`, `docs:`) and mention the touched notebook cell range when relevant, e.g., `feat: extend door logic (cells 12-18)`. Pull requests should include: purpose, summary of behavioural impact (reward deltas, runtime), screenshots of the rendered grid, and references to rubric items addressed. Always attach the executed notebook (`build/agent-run.ipynb` or HTML export) so reviewers can replicate results without re-running.

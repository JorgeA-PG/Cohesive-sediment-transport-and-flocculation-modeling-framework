# AGENTS.md

## Project purpose

This repository implements a cohesive-sediment transport and
flocculation modeling framework for a current bottom boundary layer.

## Scientific requirements

- Preserve total suspended-sediment mass.
- Preserve physical units and array dimensions.
- Do not change model equations unless explicitly requested.
- Separate code refactoring from changes to the scientific model.
- Compare all modified results against the original implementation.
- Use explicit numerical tolerances when comparing floating-point results.

## MATLAB development rules

- Put automated tests in `tests/`.
- Put profiling and timing scripts in `benchmarks/`.
- Put reproducible execution scripts in `scripts/`.
- Put explanations and development documentation in `docs/`.
- Avoid `cd` inside reusable functions.
- Prefer explicit file paths using `fullfile`.
- Avoid hidden global state.
- Preallocate arrays where practical.
- Document units and dimensions for important variables.
- Make small, focused changes.
- Do not modify the `main` branch directly.
- Do not commit generated result folders such as `fd_2.20/`.

## Verification requirements

Before completing a code change:

1. Run all relevant MATLAB tests.
2. Verify mass conservation.
3. Compare `d16`, `d50`, and `d84`.
4. Compare `wav_ws`, `wav_d`, and `wav_fdens`.
5. Compare the sediment concentration profile.
6. Run the affected benchmark.
7. Inspect the Git diff.
8. Confirm that no unrelated files changed.
# Pólya-Szegő Lean 4 Formalization Benchmark

823 problems from Pólya & Szegő's *Problems and Theorems in Analysis* (Parts I–III), evaluated across 8 formalization systems.

## Dataset

- **`problems.json`** — 823 problems with unique IDs (`P1_20` = Part One Problem 20, `P2_20` = Part Two Problem 20), problem text, and book solutions
- **`arbiter_results.json`** — Semantic correctness verdicts from Claude Opus 4.6 for each model's formalization

## Task

Each system receives a problem statement and the book's solution, and must produce a Lean 4 theorem statement using Mathlib that faithfully captures the mathematical content. The arbiter evaluates semantic correctness — whether the Lean code says the same thing as the math — not whether it compiles.

## Results (March 2026)

| Model | Correct | Total | Accuracy |
|-------|--------:|------:|---------:|
| GPT-5.4 | 398 | 467 | **85.2%** |
| Gemini 3.1 Pro | 539 | 732 | **73.6%** |
| Aristotle | 35 | 52 | **67.3%** |
| Claude Sonnet 4.6 | 417 | 821 | **50.8%** |
| Kimi K2.5 | 268 | 819 | **32.7%** |
| GLM-5 | 182 | 821 | **22.2%** |
| DeepSeek v3 | 152 | 821 | **18.5%** |
| MiniMax M2.5 | 132 | 819 | **16.1%** |

Total evaluated varies per model due to API failures.

## Notes

- Problems are numbered within each Part. Problem 20 appears in all three Parts with entirely different content. The `id` field disambiguates.
- The book's solutions in the OCR have some quality issues (mismatched problem/solution pairs for ~5% of entries, particularly in Part One problems 38–80).
- Aristotle's 67.3% semantic accuracy coexists with a 97.6% proof completion rate — it proves theorems fluently but sometimes proves the wrong one.

## Citation

If you use this benchmark, please cite:

```
Pólya-Szegő Lean 4 Formalization Benchmark
https://github.com/igorrivin/polya-szego-benchmark
March 2026
```

## License

Problem texts are from Pólya & Szegő (1925), in the public domain. Benchmark data and evaluations are released under CC-BY-4.0.

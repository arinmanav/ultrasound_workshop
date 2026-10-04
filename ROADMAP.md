# Roadmap

Progress against the order in section 14 of [CURRICULUM.md](CURRICULUM.md). A
module counts as complete when it meets the checklist in
[docs/module-template.md](docs/module-template.md).

## Stages

| Stage | Modules, in order | Status |
| --- | --- | --- |
| 0 | Repository foundation: plan, module template, conventions, tooling | Complete |
| 1 | 82, 84 | Not started |
| 2 | 1, 2, 3, 4, 8 | Not started |
| 3 | 9–18, with the wave simulator of the Course A project after 13 | Not started |
| 4 | 5, 6, 7, 19–29, 88, then the rest of the Course A project | Not started |
| 5 | 31, 32, 33, 34, 87 | Not started |
| 6 | 51, 60, 53, 61, 63, 52, 54, 55, 56, 57, 59, 62, then the Course C project | Not started |
| 7 | 64–71, 58, 72–76, with the Course D projects after 71 and 73 | Not started |
| 8 | 35, 36, 30, 37–50, then the Course B project | Not started |
| 9 | 83, 77–81, 85, 86, then the capstone | Not started |
| 10 | 89–100 | Not started |

## Next

Module 82, prototyping languages.

## Points to settle when the modules are written

The topic lists of the plan leave four things open. Each is settled in the
module named.

- **Discrete Fourier transform.** No topic list names it, and modules 8, 20
  and 23 need it. Module 2 introduces it with the other transforms.
- **Hankel transform.** It uses Bessel functions, which module 4 teaches.
  Module 2 introduces the transform through its integral form, and module 4
  returns to it.
- **Training a neural network.** No module teaches the basics before modules
  64 and 66 use them. Module 82 introduces the training loop with PyTorch, and
  module 66 builds the first network.
- **Channel-data formats.** Module 80 teaches them, but the benchmark data of
  module 54 has to be loaded long before. Module 54 teaches the loaders it
  needs.

## Calibration

The plan estimates 6 to 10 hours of study per module. The time taken to work
through the first modules is recorded here once it has been measured, and the
estimate for the remaining modules is revised if needed.

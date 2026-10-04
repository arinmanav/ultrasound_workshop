# Module template

Every technical module has the six elements defined in section 4 of
[CURRICULUM.md](../CURRICULUM.md): concept, derivation, implementation, coding
exercise, reading and interview questions. This page fixes where each element
lives and what it must contain, so that all modules read the same way.
Notation, units and code style are set in [conventions.md](conventions.md).

## Files

A module is a folder `modules/NNN-short-title/`, where `NNN` is the module
number from the plan, zero-padded to three digits.

| File | Elements | Contents |
| --- | --- | --- |
| `README.md` | 5 | Overview, learning objectives, prerequisites, contents and reading list |
| `lesson.md` | 1, 2 | Concept and derivation |
| `implementation.md` | 3, 4 | Implementation notes and the coding exercise |
| `interview.md` | 6 | Interview questions with model answers |
| `notebook.ipynb` | all | Walkthrough that runs the reference implementation |
| `figures/` | all | Figures exported by the notebook, as PNG and SVG |

The reference implementation of a coding exercise is not stored in the module
folder. It goes into the shared libraries, so that later modules can import it:

| Location | Contents |
| --- | --- |
| `src/usip/` | Python package |
| `tests/` | Python tests (pytest) |
| `matlab/+usip/` | MATLAB package |
| `matlab/tests/` | MATLAB tests (`matlab.unittest`) |

Modules without a derivation or a coding exercise (most of Parts 12 and 13)
omit the files they do not need and say so in their `README.md`.

## What each file contains

### `README.md`

```markdown
# Module NNN: Title

One paragraph: what the module covers and where it sits in the imaging chain.

## Learning objectives

Four to eight statements of what the learner can derive, explain or build
afterwards. Each one is checked by the exercise or by an interview question.

## Prerequisites

Earlier modules, by number, and the specific results used from each.

## Contents

Links to lesson.md, implementation.md, interview.md and notebook.ipynb, with
one line on each.

## Reading

One textbook section and one or two primary papers, each with a sentence on
what to read it for. Further reading is listed separately and kept short.
```

### `lesson.md`

- **Concept.** The idea in plain terms with the physical or engineering
  intuition, before any equation. A reader who stops here should be able to
  explain the idea to a colleague.
- **Derivation.** The mathematics from first principles. State every
  assumption where it is used and give the range of validity of each result.
  Define each symbol on first use. Number the equations that later sections,
  the code or the interview answers refer to.

### `implementation.md`

- **Implementation.** How the result is built in software or hardware, and
  what a product constrains: compute, memory, noise, cost, regulation. Map each
  function of the reference implementation to the equation it implements.
- **Coding exercise.** The task, the function signatures to implement, how to
  run the tests in Python and in MATLAB, and extension tasks. The tests define
  when the exercise is complete.

### `interview.md`

Five to ten questions with model answers. Mix conceptual questions, short
derivations and practical or debugging questions. A model answer is what a
strong candidate would say in one to two minutes, including the numbers. The
questions are collected into the question bank of module 93.

### `notebook.ipynb`

A walkthrough that imports the reference implementation, reproduces every
simulated or numerically evaluated value quoted in the lesson, and exports
the figures. It does not implement the algorithms of the module again: it
calls `usip` and adds only the analysis needed to measure and plot the
results. It is committed without outputs
(see [conventions.md](conventions.md)).

## Completion checklist

A module is complete when:

- [ ] Each learning objective is covered by the lesson and checked by the
      exercise or an interview question.
- [ ] Every result in the derivation states its assumptions and range of
      validity, and uses the symbols in [conventions.md](conventions.md).
- [ ] The Python and MATLAB implementations have tests with independently
      derived expected values, the tests pass, and the two implementations
      agree numerically on a common case.
- [ ] The notebook runs from top to bottom in a fresh kernel, reproduces the
      values quoted in the lesson and exports the figures.
- [ ] Each reading entry has been checked against the source.
- [ ] There are five to ten interview questions with model answers.
- [ ] [ROADMAP.md](../ROADMAP.md) is updated.

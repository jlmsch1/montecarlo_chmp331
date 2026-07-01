# GenAI-Assisted Monte Carlo Simulation for Enzyme Kinetics

This repository contains companion materials for the manuscript:

**A GenAI-Assisted Classroom Activity for Exploring Enzyme Kinetics, Fitting Methods, and Experimental Design with Monte Carlo Simulation**

Jeffrey L. Mills  
Rochester Institute of Technology

## Overview

This classroom activity uses GenAI-assisted Python code generation to help students explore Michaelis-Menten enzyme kinetics, Monte Carlo simulation, fitting-method comparison, parameter uncertainty, and experimental design.

Students use Python-based simulations to generate synthetic enzyme-kinetics data, add controlled noise, and compare recovered kinetic parameters using:

- nonlinear Michaelis-Menten regression
- Lineweaver-Burk analysis
- Eadie-Hofstee analysis
- Hanes-Woolf analysis

The activity emphasizes that obtaining a numerical fit is not the same as obtaining a reliable kinetic parameter. Students compare how noise, substrate-concentration range, data density, and sampling design affect estimates of \(K_M\) and \(V_{\max}\).

A second instructional goal is critical evaluation of GenAI-generated code. GenAI is used as a computational scaffold, not as an answer source. Students are asked to verify that generated code implements the intended kinetic model, simulation parameters, fitting methods, and substrate-concentration design.

## Intended audience

This activity was designed for an upper-division undergraduate **Physical Chemistry for the Life Sciences** course, but it may also be useful in:

- biochemistry
- enzymology
- analytical chemistry
- physical chemistry
- chemical education courses involving data analysis
- courses introducing scientific computing, uncertainty, or model fitting

Students should have prior exposure to the Michaelis-Menten equation and basic enzyme-kinetics plots. Prior Python experience is helpful but not required.

## Estimated class time

### Full implementation

The activity was implemented in a **75-minute class period**.

A typical timeline is:

| Time | Activity |
|---:|---|
| 0–5 min | Pre-activity survey and framing |
| 5–15 min | Instructor introduction to Monte Carlo simulation and experimental noise |
| 15–25 min | Students generate and run GenAI-assisted Python code |
| 25-40 min | Students explore near-ideal and noisy data |
| 40-55 min | Groups analyze assigned flawed substrate-concentration designs |
| 55–70 min | Class debrief and post-activity survey |
| 70-75 min | Post-activity survey |

### Shortened implementation

A **50-minute version** may be feasible with additional instructor scaffolding:

- omitting formal pre/post surveys, or administering them outside of class if assessment data are desired
- providing an instructor-generated backup notebook
- assigning each group only one flawed substrate-concentration design
- limiting the debrief to a focused comparison of design failures
- using a short exit question instead of a full post-activity survey

## Repository contents

```text
notebooks/
  student_activity.ipynb
  instructor_solution.ipynb

prompts/
  genai_prompt.md

instructor_notes/
  instructor_notes.md

example_output/
  example_output_and_fitted_parameters.md

figures/
  figure_generation_code.py

si_files/
  Supporting Information files corresponding to the manuscript

requirements.txt

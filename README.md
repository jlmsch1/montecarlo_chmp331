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
```

## Software requirements

The activity can be run in Google Colab or in a local Python environment.

Core Python packages:

- numpy
- scipy
- pandas
- matplotlib

Optional packages may be useful for notebook display or figure generation, but the activity is designed to rely on a minimal scientific Python stack.

To install the required packages locally:

`pip install -r requirements.txt`

## Running the activity in Google Colab

- Open Google Colab.
- Upload or open `notebooks/student_activity.ipynb`.
- Run the notebook cells from top to bottom.
- Modify the substrate-concentration arrays, noise level, number of Monte Carlo trials, or fitting methods as directed by the instructor.
- Compare fitted \(K_{M}\) and \(V_{max}\) values across methods and sampling designs.

Instructors may wish to provide `notebooks/instructor_solution.ipynb` as a backup notebook if students have difficulty generating working code during class.

## GenAI prompt

The GenAI prompt used in the activity is available in `prompts/genai_prompt.md`. The prompt asks a GenAI tool to generate well-commented Python code for Monte Carlo simulation of Michaelis-Menten kinetics and comparison of nonlinear and linearized fitting methods.

### Important note on GenAI variability

GenAI outputs may vary across tools, model versions, sessions, prompts, and users. Even when students use the same prompt, generated code may differ in structure, assumptions, parameter values, plotting choices, or error handling.

Instructors and students should verify that generated code:

- uses the intended \(K_{M}\) and \(V_{max}\) values
- uses the intended substrate-concentration design
- applies the intended noise level
- performs the intended fitting methods
- reports physically meaningful fitted parameters
- does not silently modify user-specified simulation conditions

This variability is not only a limitation; it is also a useful part of the activity. It gives students an opportunity to evaluate computational output rather than treating code, plots, or fitted parameters as automatically authoritative.

## Random seeds

The activity does not require fixed random seeds. Variation among student outputs can support discussion of stochastic simulation and Monte Carlo variability.

Instructors who want all students to obtain identical outputs may set a fixed random seed, for example:

```python
import numpy as np
rng = np.random.default_rng(123)
```

If a fixed seed is used, students should understand that the result is one reproducible realization of the simulation, not a unique or definitive result.

## Numerical precision

Some example outputs may display more decimal places than are chemically or statistically meaningful because they are copied directly from computational output. These values are intended to illustrate trends in accuracy, precision, bias, and variability, not to imply that all reported digits are significant.

## Recommended citation

Until the article is published, cite this repository as:

Mills, J. L. GenAI-Assisted Monte Carlo Simulation for Enzyme Kinetics. GitHub repository, 2026.

After publication, please cite the associated Journal of Chemical Education article:

Mills, J. L. A GenAI-Assisted Classroom Activity for Exploring Enzyme Kinetics, Fitting Methods, and Experimental Design with Monte Carlo Simulation. Journal of Chemical Education, year, volume, pages, DOI.

## License

Code and notebooks in this repository are licensed under the MIT License.

Prompts, instructor notes, activity descriptions, handouts, and other teaching materials are licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0), unless otherwise noted.

See:

`LICENSE`
`LICENSE-CC-BY-4.0.md`

## Contact

Jeffrey L. Mills
Rochester Institute of Technology

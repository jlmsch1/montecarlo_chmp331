# Instructor Notes

## Activity title

GenAI-Assisted Monte Carlo Simulation for Enzyme Kinetics

## Purpose

This activity helps students connect enzyme-kinetics fitting results to experimental design, measurement noise, and parameter uncertainty. Students use GenAI-assisted Python code to simulate Michaelis-Menten initial-rate data and compare nonlinear regression with Lineweaver-Burk, Eadie-Hofstee, and Hanes-Woolf analyses.

A secondary purpose is to help students evaluate GenAI-generated code critically. Students are asked to check whether the code implements the intended model, parameters, noise level, fitting methods, and substrate-concentration design.

## Intended audience

The activity was designed for an upper-division Physical Chemistry for the Life Sciences course. It may also be adapted for biochemistry, analytical chemistry, physical chemistry, or courses involving scientific computing and data analysis.

## Prerequisite knowledge

Students should have prior exposure to:

- Michaelis-Menten kinetics
- \(K_M\) and \(V_{\max}\)
- initial-rate data
- Lineweaver-Burk plots
- basic interpretation of fitted parameters
- basic graph reading

Students do not need any Python experience.

## Learning goals

After completing the activity, students should be able to:

1. Describe Monte Carlo simulation as repeated random sampling from a model.
2. Explain how experimental noise affects fitted enzyme-kinetics parameters.
3. Compare nonlinear Michaelis-Menten regression with linearized fitting methods.
4. Identify how substrate-concentration design affects recovery of \(K_M\) and \(V_{\max}\).
5. Recognize that a numerical fit is not necessarily a reliable parameter estimate.
6. Evaluate whether GenAI-generated code implements the intended simulation.

## Materials

Recommended materials:

- computer or tablet capable of running Google Colab
- access to a GenAI tool such as Google Gemini, ChatGPT, Claude, or similar
- activity prompt
- instructor backup notebook
- projector or shared display for class debrief

## Recommended implementation

### 75-minute version

| Time | Activity |
|---:|---|
| 0–5 min | Pre-activity survey |
| 5–15 min | Instructor introduction: Monte Carlo simulation, noise, and repeated sampling |
| 15–30 min | Students generate and run GenAI-assisted code |
| 30–45 min | Students explore near-ideal and noisy data |
| 45–60 min | Groups analyze assigned flawed substrate-concentration designs |
| 60–75 min | Class debrief and post-activity survey |

### 50-minute version

A shortened version may be feasible by:

- assigning the pre-activity survey before class
- providing a backup notebook
- assigning each group only one flawed substrate-concentration design
- limiting the debrief to comparison of design failures
- assigning reflection questions after class

## Suggested flawed substrate-concentration designs

Possible group assignments:

1. Missing low-substrate concentrations
2. Missing high-substrate concentrations
3. Substrate concentrations clustered near \(K_M\)
4. Too few total data points
5. Poorly distributed concentrations across the Michaelis-Menten curve

## Debrief questions

Suggested discussion questions:

1. Which fitting method produced the most consistent \(K_M\) values?
2. Which fitting method produced the most consistent \(V_{\max}\) values?
3. What happened when low-substrate data were missing?
4. What happened when high-substrate data were missing?
5. Did any method return numerical values that looked acceptable but were not reliable?
6. What design changes would improve parameter recovery?
7. Did the GenAI-generated code follow the prompt exactly?
8. What did you check before trusting the output?
9. Which method would you prefer for future enzyme-kinetics analysis, and what metric supports your choice?

## Common implementation issues

Possible issues include:

- GenAI-generated code silently changes the requested noise level.
- Code uses different parameter values than specified.
- Linearized fits produce nonphysical parameter estimates.
- Different students receive different code from the same prompt.
- Random-number generation leads to different outputs across students.
- Fitting routines fail or return unstable results for poorly sampled data.
- Plots may look reasonable even when parameter estimates are biased or imprecise.

These issues can be productive if they are incorporated into the debrief.

## Random seeds

The activity does not require fixed random seeds. Variation among student outputs can help illustrate Monte Carlo variability.

Instructors who want reproducible output can set a fixed random seed. For example:

```python
import numpy as np
rng = np.random.default_rng(123)
```

If a fixed seed is used, students should understand that the result is one reproducible realization of the simulation, not a unique or definitive answer.

## Notes on numerical precision

Simulation output may include more decimal places than are chemically or statistically meaningful. Instructors may wish to use this as a discussion point about significant figures, fitted parameters, and numerical output from computational tools.

## Suggested adaptations

Possible adaptations include:

providing instructor-written code instead of GenAI-generated code
asking students to compare weighted and unweighted fitting
adding confidence intervals or bootstrap analysis
increasing the number of Monte Carlo trials
using different noise models
connecting the activity to an experimental enzyme assay
adapting the simulation to binding curves or calibration curves

## Instructor recommendation

The most important part of the activity is the debrief. Students should leave with the idea that experimental design and model assumptions determine whether fitted parameters are meaningful. Changing plotting methods does not rescue data that fail to constrain the kinetic parameters of interest.

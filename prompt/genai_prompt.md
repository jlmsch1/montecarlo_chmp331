Write Python code for a Monte Carlo simulation of Michaelis-Menten enzyme kinetics. The code should:

1. Define true parameters:
   Vmax_true = 10.0
   Km_true = 50.0
2. Define a substrate concentration array:
   S_array = [2, 5, 10, 20, 40, 60, 80, 120, 200]
3. Define a variable:
   noise_level = 1e-6
4. Generate synthetic velocity data using:
   v_true = (Vmax_true * S_array) / (Km_true + S_array)
5. Add Gaussian noise to each velocity value:
   noise standard deviation = noise_level * v_true
6. Run a Monte Carlo simulation with at least 250 trials:
   - In each trial, generate noisy data
   - Fit using:
       a) nonlinear Michaelis-Menten (scipy.optimize.curve_fit)
       b) Lineweaver-Burk (scipy.stats.linregress)
       c) Eadie-Hofstee (scipy.stats.linregress)
       d) Hanes-Woolf (scipy.stats.linregress)
7. Store fitted Km and Vmax for each method
8. Plot:
   - For each method (MM, LB, HW, and EH), plot one data set with fitted parameters.
   - Each plot should be in its native format – nonlinear for the MM, linear for the LB, HW, and EH
9. Print the mean, standard deviation, and 95% confidence interval for Km and Vmax.
10. Use clear variable names:
   S_array for substrate
   v_true for true velocities
   v_noisy for noisy data
   noise_level for noise

Use numpy, matplotlib, and scipy.optimize.curve_fit.
Write clean, well-commented code.

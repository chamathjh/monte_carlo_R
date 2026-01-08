Here’s a **clean, professional `README.md`** you can drop straight into your GitHub repo. It explains the idea, the code, and how to run it—exactly what interviewers and reviewers expect.

---

# 🎯 Monte Carlo Simulation to Estimate π (Pi)

This repository contains an R script that uses a **Monte Carlo simulation** to estimate the value of π by randomly throwing points (“darts”) into a square and counting how many land inside a unit circle.

---

## 📌 Idea Behind the Simulation

* Generate random points uniformly in the square ([-1, 1] \times [-1, 1])
* A point lies inside the unit circle if:

[
x^2 + y^2 \leq 1
]

* The ratio of points inside the circle to total points approximates:

[
\frac{\pi r^2}{(2r)^2} = \frac{\pi}{4}
]

So:
[
\pi \approx 4 \times \frac{\text{points inside circle}}{\text{total points}}
]

---

## 🧮 What the Code Does

1. **Generates random points**

   * Uses `runif()` to draw random (x) and (y) values
2. **Counts points inside the unit circle**

   * Computes (x^2 + y^2)
3. **Estimates π**

   * Uses the Monte Carlo ratio
4. **Visualizes convergence**

   * Animates how points accumulate inside the square

---

## 📂 Code Overview

```r
num_darts <- 10000
num_darts_in_circle <- 0

x <- runif(n = num_darts, min = -1, max = 1)
y <- runif(n = num_darts, min = -1, max = 1)

sum_squares <- x^2 + y^2
indexes_darts_in_circle <- which(sum_squares <= 1)
num_darts_in_circle <- length(indexes_darts_in_circle)

print(4 * num_darts_in_circle / num_darts)
```

### Animation of the Simulation

```r
for (i in 1:100) {
  plot(x[1:i], y[1:i], xlim = c(-1,1), ylim = c(-1,1))
  points(x[i], y[i], col = "green")
  Sys.sleep(0.5)
}
```

---

## ▶️ How to Run

1. Clone the repository
2. Open the script in R or RStudio
3. Run the script line-by-line or source the file

```r
source("monte_carlo_pi.R")
```

---

## 📈 Example Output

```
[1] 3.1416
```

(The value improves as `num_darts` increases.)

---

## 🔧 Customization

You can:

* Increase `num_darts` for higher accuracy
* Reduce `Sys.sleep()` for faster animation
* Plot only points inside the circle
* Convert the animation to `ggplot2`

---

## 🧠 Concepts Demonstrated

* Monte Carlo methods
* Vectorized computation in R
* Random number generation
* Basic data visualization
* Numerical approximation

---

## 📜 License

This project is for educational purposes.
Feel free to use, modify, and share.

 and tests
 

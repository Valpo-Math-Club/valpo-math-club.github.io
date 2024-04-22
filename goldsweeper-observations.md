:stem: latexmath

# Goldsweeper Observations

## First Move

**It is never optimal to pick an edge/corner space.**

This is the main strategy for the first move, and we aim to prove it in this section:

### Natural Frequency of first move

Suppose we have eight neighbors; i.e. we're not picking an edge or corner space. Also assume the board is 64 squares and there are 12 bombs/thieves.
Then the probability of picking a green square is the same as the probability of picking a square whose neighbors are all good. In other words:
$$
P (\text{green}) = \dfrac{\binom{40}{8}}{\binom{64}{8}} \approx 1.74\%
$$

In general, suppose a square has $n_n$ neighbors, and there are $n_b$ bad squares and $n$ squares in total. Then the probability that there are $k$ bad neighbors nearby is:
$$
P (k\text{ bad neighbors}) = \dfrac{\binom{n-n_b}{n_n - k}\cdot \binom{n_b}{k}}{\binom{n}{n_n}}
$$
$\binom{n-n_b}{n_n - k}\cdot \binom{n_b}{k}$ is the number of ways to select $k$ good neighbors out of the $n_n$ neighbors you have, i.e. the number of ways to select our good neighbors. $\binom{n-n_b}{n_n - k}$ is the number of ways you can select the good squares, and $\binom{n_b}{k}$ is the number of ways you can select the bad squares. $\binom{n}{n_n}$ is the number of possible outcomes.
In our case, $n_b = 24$ and $n = 64$, we see that more bad neighbors are more likely when you don't pick an edge or corner square.

## Second Move

**It is always optimal to pick next to a green square.** The reason is obvious and is left as an exercise to the reader.

**It is always optimal to pick next to a thief.**

Open Question: **When is it optimal to pick an adjacent square?**